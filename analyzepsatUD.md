

# An illustrated script to using analyzepsat for utilization distribution #

Here is some R code to get started
Add your content here.
```

# load libraries
library(analyzepsat)
library(trackit)

# load data
data(big.241)
data(gmt3)

# get bathymetry
bath = get.bath.data(-180,-150,-10,50)

# add dummy columns
big.241$sst = 10
big.241$maxz=-10

# run the Kalman filter routine
fit1 = kftrack(big.241[,1:5])

# plot it
.plot3(fit1, map=F, ci=T, points=F, pred=F)
points(fit1$most.prob.track, typ='o', col=4, pch=19, cex=.7)
polygon(gmt3, col = 'black')
title('big.241 most probable track')
 
```

![http://geolocation.googlecode.com/svn/wiki/images/big241-MPT.jpeg](http://geolocation.googlecode.com/svn/wiki/images/big241-MPT.jpeg)

```

# prepare for bathymetric correction
ftrack1 = prepb(fit1, big.241)

# make sure longitude is -180 to 180. We here use the summy column for maxz
ftrack1$Lon_E = ftrack1$Lon_E-360

# Do the bathymetric correction
btrack1 = make.btrack(ftrack1, bath)

# plot it
par(mfrow=c(1,2))
par(mar=c(4,4,6,4))

plot(gmt3, xlim = c(-160, -140)+360, ylim = c(10,25), typ='l', axes=F)
rect(par("usr")[1],par("usr")[3],par("usr")[2],par("usr")[4],col = "lightblue")
plot.btrack(btrack1, offset=360, add=T)
polygon(gmt3, col = 'black')
degAxis(1)
degAxis(2)
.add.month.scale()

plot(gmt3, xlim = c(-160, -140)+360, ylim = c(10,25), typ='l', axes=F)
rect(par("usr")[1],par("usr")[3],par("usr")[2],par("usr")[4],col = "lightblue")
plot.btrack(btrack1, offset=360, add=T, ci=T)
polygon(gmt3, col = 'black')
degAxis(1)
degAxis(2)

```

![http://geolocation.googlecode.com/svn/wiki/images/big241-btrack.jpeg](http://geolocation.googlecode.com/svn/wiki/images/big241-btrack.jpeg)

```

# get the utilization distribution
btrack1[,8] = btrack1[,8]+360  # add 360 back to longitude so the gmt polygons match

kd1 = track2KD(btrack1,  xsize= .1,  ysize= .1,  range.x=c(-160, -140)+360, range.y= c(0,30))
ud1 = kern2UD(kd1)

# plot it 
x11()
ilabs = c(.1, .3, .5,.75, .95)*100
axis.args=list( at=ilabs, labels=paste(round(ilabs), '%') )

image(ud1, zlim = c(0,.99),  xlim = c(-160, -140)+360, ylim = c(10,25),
 col = gray.colors(100,start = 0, end = 1), xlab='', ylab='',add=F, axes=F)
rect(par("usr")[1],par("usr")[3],par("usr")[2],par("usr")[4],col = "lightblue")
image(ud1, zlim = c(0,.99),  xlim = c(-160, -140)+360, ylim = c(10,25),
 col = gray.colors(100,start = 0, end = 1), xlab='', ylab='',add=T, axes=F)
	degAxis(1); 
	degAxis(2);
	polygon(gmt3, col = 'green')
	box()
	
image.plot(matrix(c(0,100)), col =  gray.colors(100,start = 0, end = 1),
 smallplot = c(.65,.70,.25,.85) , legend.only=T, axis.args=axis.args)
```
![http://geolocation.googlecode.com/svn/wiki/images/big241-UD.jpeg](http://geolocation.googlecode.com/svn/wiki/images/big241-UD.jpeg)
```

# add the track
data(ATL)
data(myramps)
plot.btrack(btrack1, offset=0, add=T, ci=F)

```
![http://geolocation.googlecode.com/svn/wiki/images/big241-UD-track.jpeg](http://geolocation.googlecode.com/svn/wiki/images/big241-UD-track.jpeg)

```
# now use the fixed kernel density
fkern = kernelUD(btrack1[,8:9])
ukern = getvolumeUD(fkern)

```
![http://geolocation.googlecode.com/svn/wiki/images/big241-fixedKD.jpeg](http://geolocation.googlecode.com/svn/wiki/images/big241-fixedKD.jpeg)

**Side-by-side comprison shows that fixed kernel methods overestimate the utilization
![http://geolocation.googlecode.com/svn/wiki/images/big241-fixedKD-vs-track2KD.jpeg](http://geolocation.googlecode.com/svn/wiki/images/big241-fixedKD-vs-track2KD.jpeg)**

# Summary #
The track2KD and kern2UD functions in analyzepsat utilize the error structure estimated through the KF methods on these pages to directly estimate the utilization (Galuardi et. al, in prep).


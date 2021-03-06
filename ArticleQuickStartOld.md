

# Installation of R and geolocation packages #

**[R](http://www.r-project.org/)** is being very rapidly developed and geolocation packages may sometimes lag in catching up with fundamental changes made in **[R](http://www.r-project.org/)** that renders some older routines non-functional. To take a conservative approach, we recommend the following installation:

  * R-2.8.1

> http://cran.r-project.org/bin/windows/base/old/2.8.1/

  * Geolocation packages

> http://tagbase.googlecode.com/files/library.zip

Move the extracted package folders into the R library folder. To find out where your R library folder is located, type in R:

> `library()`

And look for something like this:

> `Packages in library 'C:/R/R-2.8.1/library':`

# It is best to... #

  * Inform yourself with an overview of the geolocation methods:

> http://www.soest.hawaii.edu/PFRP/nov07mtg/nielsen.pdf

  * Refer to **[PFRP Trackit Workshop materials](http://docs.google.com/leaf?id=0BwcYza_M2AiqZmVjNDBhYzgtMzBlZi00OTQ1LWE3NDAtNzRiYjhmYmJiOTEw&hl=en)** for more detailed tutorials


# Conducting an example run of different geolocation packages #

  * Start up R, copy-and-paste lines or block of code to run the commands

  * Kftrack

```
# Note: delete the hash sign (#) at the beginning to uncomment a line

library(kftrack)

data(big.241) # load packaged example data

track <- big.241
#track<-read.table("datafile.dat", header=TRUE) # change file name and path for your own file

fit1 <-kftrack(track)
fit1 # inspect model parameters

plot(fit1, map=FALSE, ci=TRUE)
save(fit1, file="kf-example.Rdata")
```

  * Ukfsst or Kfsst

```
# Note: delete the hash sign (#) at the beginning to uncomment a line

library(ukfsst)
#library(kfsst)

data(blue.shark) # load packaged example data
#track<-read.table("datafile.dat", header=TRUE) # change file name and path for your own file

sst.path<-get.sst.from.server(track)
#sst.file<-write.sst.field(sst.path) # only used in kfsst

fit2<-kfsst(track)
fit2 # inspect model parameters

plot(fit2, map=FALSE, ci=TRUE)
save(fit2, file="kf-example.Rdata")
```

  * Trackit

```
# Note: delete the hash sign (#) at the beginning to uncomment a line

library(trackit)  
data(drifter) # load packaged example data
#track<-read.table("datafile.dat", header=TRUE) # change file name and path for your own file
prep.track<-prepit(drifter, fix.first=c(360-161.45,22.85,2002,9,10,0,0,0), 
                   fix.last=c(360-159.87,21.95,2003,5,21,0,0,0), scan=FALSE)
 
fit3<-trackit(prep.track, D.ph=2)
fit3 # inspect model parameters

plot(fit3)
fitmap(fit3, ci=T)
points(fit3$most.prob.track, pch=20)
save(fit3, file="kf-example.Rdata")
```


# Exporting results from R #

Assume we have run our tracks successfully, and everything is in an active R session, we can output the tracks for other programs.

  * Download the export script for R, [fit2csv](http://geolocation.googlecode.com/svn/trunk/updates/fit2csv.R) (Right-click to "save link/ file as")

  * Make sure you note where you save the downloaded file. Drag-and-drop the file into the main R window, or use the function, `source`

```
# Note: delete the hash sign (#) to uncomment a line

# Preparation; define working directory:
setwd("C:/Test")

# Main code:

source("fit2csv.R")
fit2csv(fit1)
fit2csv(fit2)
```

  * A set of output files (e.g `fit1a.csv`, `fit1b.csv`, `fit1c.csv`) will be generated for each tag
> The output files are:
  * `-a.csv` - track points
  * `-b.csv` - model parameters
  * `-c.csv` - initialization values to model

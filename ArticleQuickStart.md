

# Installation of R and geolocation packages #

  * First, download **[R](http://www.r-project.org/)**. To download the latest version, visit **[here](http://cran.rstudio.com/)**, or http://cran.rstudio.com/

  * Please understand that R is being very rapidly developed and geolocation packages may sometimes lag in catching up with the fundamental changes made in R.

  * Our currently tested version is R-3.2.0.

### Easy installation of geolocation packages ###

  * To make installation a bit easier, a script has been prepared to set up all required packages. To run it, fire up **[R](http://www.r-project.org/)** and type (or paste) the following line:

```


  source('http://geolocation.googlecode.com/svn/trunk/install.r')
  
```

  * if you are running R 3.0, use this script

```

  source('http://geolocation.googlecode.com/svn/trunk/install-3.0.r')
 
```

### Manual installation of geolocation packages (for R-2.15 or older) ###

  * Go to our **[Downloads](http://code.google.com/p/geolocation/downloads/list)** to download the package files, according to your operating system (OS). Notice different OS will have different file extensions.

  * If you are unsure what to download, always download the **32-bit** versions.

  * Start up R and install the packages by the R user-interface and browse to the downloaded file

![http://geolocation.googlecode.com/svn/wiki/images/Rlocalpackage.jpg](http://geolocation.googlecode.com/svn/wiki/images/Rlocalpackage.jpg)

  * Or copy and pasting one or all of the following lines as commands in R

  * Make sure, you **REMOVE** "-x64" from the filename of your downloaded 64-bit package

  * For example, for a Mac OSX:

```
### Make sure you know the file directory where 
### you have downloaded the files and file extensions
### First argument below is the file path, enclosed in quotes

install.packages("~/Desktop/mac/kftrack.tgz", repos=NULL)

install.packages("~/Desktop/mac/ukfsst.tgz", repos=NULL)

install.packages("~/Desktop/mac/trackit.tgz", repos=NULL) 

```

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

# For users with R-3.1 and over, please run the following line as well:
source('http://geolocation.googlecode.com/svn/trunk/support/ukfsst/func_ukfsst.r')

data(blue.shark) # load packaged example data
#track<-read.table("datafile.dat", header=TRUE) # change file name and path for your own file

sst.path<-get.sst.from.server(track)
#sst.file<-write.sst.field(sst.path) # only used in kfsst

track <- blue.shark # delete this line when you use your own data
fit2<- kfsst(track, bx.a=F, bsst.a=F)
fit2 # inspect model parameters

plot(fit2, map=FALSE, ci=TRUE)
save(fit2, file="kf-example.Rdata")
```

  * Trackit

```
# Note: delete the hash sign (#) at the beginning to uncomment a line

library(trackit)

# For users with R-3.1 and over, please run the following lines as well:
data(gmt3); data(deltat); deltat$JDE = with(deltat,JDE(year,month,day))
source('http://geolocation.googlecode.com/svn/trunk/support/trackit/func_prepit.r')
source('http://geolocation.googlecode.com/svn/trunk/support/trackit/func_trackit.r')
  
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

# Preparation; find out/ define your working directory:

getwd()
# setwd("C:/Test") # give path to your desired output directory

# Main code:

source("fit2csv.R") # make sure R knows where the file is located,
                    # or move fit2csv.R to the working directory, as shown above
fit2csv(fit1)
fit2csv(fit2)
```

  * A set of output files (e.g `fit1a.csv`, `fit1b.csv`, `fit1c.csv`) will be generated for each tag
> The output files are:
  * `-a.csv` - track points
  * `-b.csv` - model parameters
  * `-c.csv` - initialization values to model
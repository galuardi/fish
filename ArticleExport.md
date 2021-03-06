

# Basic export #

R can easily write an object to a text file via the function, `write.table`:

```
   write.table(mydata, "C:/mydata.txt", sep="\t")
```

Type `?write.table` for examples and options

# Exporting geolocation results from KF packages found on this site #

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

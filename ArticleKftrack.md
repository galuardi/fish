

# Overview #

Kftrack is an add-on package for the statistical environment **R** to estimate movement parameters and predict "the most probable track" from any given position pairs (longitude, latitude). Its basic use is to fit and plot the model described in Sibert et al. 2003.

The model is one of the most simple yet versatile tools for geolocation. It is recommended to use this model on any continuous tracking data, including GPS/ Argos satellite tags. Using Kftrack allows a complete description of errors and estimation of movement parameters. Kftrack runs very fast and can handle tough/ messy data situation when other more advanced models may not provide a good fit.

# Publications #

[Kftrack](http://www.soest.hawaii.edu/PFRP/reprints/sibert_horizontal.pdf) - Sibert, J.R., Musyl, M.K., Brill, R.W., 2003. Horizontal movements of bigeye tuna (Thunnus obesus) near Hawaii determined by Kalman filter analysis of archival tagging data. Fisheries Oceanography, 12(3):141-151

[Extending Kftrack](http://www.soest.hawaii.edu/PFRP/reprints/Sibert_Lutcavage_etal_2006.pdf) - Sibert, John R., Molly E. Lutcavage, Anders Nielsen, Richard W. Brill, and Steven G. Wilson, 2006. Interannual variation in large-scale movement of Atlantic bluefin tuna (Thunnus thynnus) determined from pop-up satellite archival tags. Canadian Journal of Fisheries and Aquatic Sciences 63: 2154-2166. Also, [Supplementary material](http://www.soest.hawaii.edu/PFRP/reprints/Sibert_Lutcavage_etal_2006_supplement.pdf)

# Cheatsheet of Kftrack #

![http://geolocation.googlecode.com/svn/wiki/images/kftrack.jpg](http://geolocation.googlecode.com/svn/wiki/images/kftrack.jpg)

# Input data format #
```
> track
  day month year    lon  lat
  21     1 1999 201.750 18.65
  22     1 1999 204.520 20.00
  23     1 1999 206.086 22.00
  24     1 1999 204.399 23.50
  25     1 1999 205.209 21.50
  26     1 1999 204.016 19.50
```

# Basic Workflow #

```
# Note: delete the hash sign (#) at the beginning to uncomment a line

library(kftrack)  
track<-read.table("datafile.dat", header=TRUE) # change file name and path for your own file
fit<-kftrack(track)
plot(fit)
```

  1. Load packages
  1. Read in data files
  1. Run the model
    1. Start and end positions are assumed to known and "without any errors"
    1. Set `fix.last=FALSE` if you are unsure about your end position
    1. You can also set `fix.first=FALSE` for the start position
  1. Plot the results
    1. Use `ci=TRUE` to show the confidence regions
    1. Use `map=TRUE` if you have **[GMT](http://gmt.soest.hawaii.edu/)** installed
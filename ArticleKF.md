

# What are KF geolocation packages? #

KF geolocation packages include various state-space models: [Kftrack](ArticleKftrack.md), [Kfsst](ArticleKfsst.md), [Ukfsst](ArticleUkfsst.md) and [Trackit](ArticleTrackit.md), and KF is simply a shorthand for Kalman filter that all these packages utilize. State-space models are a generic statistical modeling technique when a model describing the observations/ measurements is coupled to a model describing the hidden process that cannot be directly measured. Refer to Patterson et al. 2008 in [Publications](ArticleRefs.md) for a review of state-space models.

# Similarities among KF packages #

  * Underlying movement model
    * Assume the same random walk model
    * Includes drift and diffusion
  * At any given position the observation model
    * Predicts the observation
    * Describes the observation error
  * All model parameters are maximum likelihood estimated
  * Any point on the most probable track is a weighted average of:
    * What is learned from the current observation
    * What is learned from the entire track
  * No land avoidance is used so positions may end up on land (high on the todo list in our future developed)

# Differences among KF packages #

  * What they take as data
    * Raw geolocations (lon,lat) used by kftrack
    * Raw geolocations and SST (lon,lat,SST) used by kfsst and ukfsst
    * Light readings and SST used by trackit
  * Technical details in handling non-linearities
    * Extended Kalman filter used by kftrack and kfsst
    * Unscented Kalman filter used by ukfsst and trackit

![http://geolocation.googlecode.com/svn/wiki/images/intro-tablediff.jpg](http://geolocation.googlecode.com/svn/wiki/images/intro-tablediff.jpg)

# General tips on usage #

  * Longitude values should be between 0 - 360 degrees (degree East)
  * If possible, running more than one KF package on the same data can often be very instructive
  * Model convergence should be obtained
  * Ways to help the optimizer if a track is problematic
    * Simplify model (especially for short tracks)
```
    fit<-kftrack(track, bx.a=FALSE, by.a=FALSE) 
```
    * Supply better initial values
```
    fit<-kftrack(track, D.i=500) 
```
    * Remove extreme outliers
```
    track<-track[abs(track$lat)<90,] 
```
    * A combination of the above
    * Also check input data or inspect via visual plots
  * Use SST products of different resolutions and compare different runs. Check documentation in R.
```
  ?get.sst.from.server
	  or
  ?get.blended.sst
```

![http://geolocation.googlecode.com/svn/wiki/images/convergence.jpg](http://geolocation.googlecode.com/svn/wiki/images/convergence.jpg)
![http://geolocation.googlecode.com/svn/wiki/images/intro-ex.jpg](http://geolocation.googlecode.com/svn/wiki/images/intro-ex.jpg)
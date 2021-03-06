

# Overview #
Analyzepsat is an add-on package for kftrack, ukfsst and trackit. It is used for import, analysis and display of pop-up and archival tag data. It is primarily focused on data returned by Microwave Telemetry fish tags but many of the functions may be used on any tag data conforming to the proper format.

The main driver behind the packages creation is a bathymetric correction scheme for light based geolocation data. Functionality exists for interpolation for missing days as well as alternate import workflows for Tagbase integration.


# Publications #
Papers using analyzepsat

**http://dx.plos.org/10.1371/journal.pone.0071883 Hueter RE, Tyminski JP, de la Parra R (2013) Horizontal Movements, Migration Patterns, and Population Structure of Whale Sharks in the Gulf of Mexico and Northwestern Caribbean Sea. PLoS ONE 8: e71883. doi:10.1371/journal.pone.0071883.**

**http://dx.doi.org/10.1371/journal.pone.0056588 Howey-Jordan LA, Brooks EJ, Abercrombie DL, Jordan LKB, Brooks A, et al. (2013) Complex Movements, Philopatry and Expanded Depth Range of a Severely Threatened Pelagic Shark, the Oceanic Whitetip (Carcharhinus longimanus) in the Western North Atlantic. PLoS ONE 8: e56588. doi:10.1371/journal.pone.0056588.**

**http://www.plosone.org/article/info:doi/10.1371/journal.pone.0037829 Galuardi B, Lutcavage M (2012) Dispersal Routes and Habitat Utilization of Juvenile Atlantic Bluefin Tuna, Thunnus thynnus, Tracked with Mini PSAT and Archival Tags. PLoS ONE 7: e37829. doi:10.1371/journal.pone.0037829.**

**http://www.nrcresearchpress.com/doi/abs/10.1139/f10-033 Galuardi, B.; Royer, F.; Golet, W.; Logan, J.; Nielson, J. & Lutcavage, M. Complex Migration Routes of Atlantic Bluefin Tuna Question Current Population Structure Paradigm. Canadian Journal of Fisheries and Aquatic Sciences, 2010, Vol. 67(1), 966-976**

other papers using bathymetric correction schemes

  * Richardson DE, Llopiz JK, Leaman KD, Vertes PS, Muller-Karger FE, Cowen RK (2009) Sailfish (Istiophorus platypterus) spawning and larval environment in a Florida Current frontal eddy. Progress In Oceanography 82:252–264

  * Royer F, Lutcavage M (2009) Positioning pelagic fish from sunrise and sunset times: complex observation errors call for constrained, robust modeling. In: Second International Symposium on Tagging and Tracking Marine Fish With Electronic Devices. Springer, p 323–341

  * Teo, S., Boustany, A., and Block, B. 2007. Oceanographic preferences of Atlantic bluefin tuna, Thunnus thynnus, on their Gulf
of Mexico breeding grounds. Mar. Biol. (Berl.), 152(5): 1105–
1119. doi:10.1007/s00227-007-0758-1.

  * Hoolihan, J. 2005. Horizontal and vertical movements of sailfish (Istiophorus platypterus) in the Arabian Gulf, determined by ultrasonic
and pop-up satellite tagging. Mar. Biol. (Berl.), 146(5):
1015–1029. doi:10.1007/s00227-004-1488-2.


# Details #

to install analyzepsat and all dependencies start R and type the following:
```
source('http://geolocation.googlecode.com/svn/trunk/install_analyzepsat.r')
```

Major functions of analyzepsat include:
  * Import of MTI fish reports via ODBC/gdata (for Windows/Linux respectively) into a standard list format. This includes some functionality for recovered MTI tags
  * Import tags stored in Tagbase (Access)
  * Display temperature/depth data nicely
  * Download bathymetric data and correct fitted tracks
  * Produce publication quality maps with fitted tracks
  * [Produce utilization distributions (UD) based on covariance of fitted tracks](analyzepsatUD.md) **_NEW!_**
  * Produce vertical habitat envelopes (currently, MTI tags only)
  * Display SST data downloaded during ukfsst/trackit analysis
  * Export tracks, confidence intervals and UD to shapefiles and .asc files (for ArcGIS and others)



We can't cover all the details here but the help files are decent and always improving!
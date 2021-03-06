

# Parameters of Trackit #

| **Parameter** | **Usage** | **Initial value** | **Unit** |
|:--------------|:----------|:------------------|:---------|
| u             | "advection" component of movement; northward component of directed movement | 0                 | nm/day   |
| v             | "advection" component of movement; eastward component of directed movement | 0                 | nm/day   |
| D             | "diffusion" component of movement. A measure of the variability in movement  | 100               | nm^2/day |
| ss1           | light covariance parameter 1 - two light measurements taken near the same solar event are more similar (correlated) than two taken at separate solar events | 1                 | N/A      |
| ss2           | light covariance parameter 2 - correlation between two light measurements near the same solar event decreases as the time between them increases | 5                 | N/A      |
| ss3           | independent measurement errors in light | 1                 | N/A      |
| rho           | light covariance parameter used in combination with ss1 & ss2, see Nielsen & Sibert 2007 for equations| 0.01              | N/A      |
| bsst          | systematic error (or bias) in the estimation of sea-surface temperature, SST | 1                 | degree Celsius |
| sssst         | random error in the estimation of sea-surface temperature, SST | 0.1               | degree Celsius |
| rad           | smoothing radius of SST data; radius centered from a given point within which satellite SST data are used | 200               | nm       |
| phi           | a collection of points (n = a2lpoints, default at 15) used to model a light curve with a cubic spine | See ?trackit      | N/A      |

# Other options #

| **Option** | **Usage** | **Initial value** | **Unit** |
|:-----------|:----------|:------------------|:---------|
|a2lpoints   | No. of points used to model light curve, see phi | 15                | N/A      |
|blue.light.only | Not implemented right now | FALSE             | N/A      |
| dep1       | Not implemented right now | 0                 | N/A      |
| dep2       | Not implemented right now | 0                 | N/A      |
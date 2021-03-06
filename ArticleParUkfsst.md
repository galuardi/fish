

# Parameters of Ukfsst #

| **Parameter** | **Usage** | **Initial value** | **Unit** |
|:--------------|:----------|:------------------|:---------|
| u             | "advection" component of movement; northward component of directed movement | 0                 | nm/day   |
| v             | "advection" component of movement; eastward component of directed movement | 0                 | nm/day   |
| D             | "diffusion" component of movement. A measure of the variability in movement  | 100               | nm^2/day |
| bx            | systematic error (or bias) in the estimation of position (longitude) | 0                 | degree   |
| by            | systematic error (or bias) in the estimation of position (latitude) | 0                 | degree   |
| bsst          | systematic error (or bias) in the estimation of sea-surface temperature, SST | 0                 | degree Celsius |
| sx            | random error in the estimation of position (longitude) | 0.5               | degree   |
| sy            | random error in the estimation of position (latitude) | 1                 | degree   |
| ssst          | random error in the estimation of sea-surface temperature, SST | 0.1               | degree Celsius |
| a0            | upper bound for latitude variance (keep the tagged animal in this planet). Used in "solstice" variance structure, related to how the latitude estimation error varies around the equinox. | 0.0001            | degree   |
| b0            | the number of days prior to the equinox where the latitude error is maximal. Used in "solstice" variance structure, related to how the latitude estimation error varies around the equinox. | 0                 | day      |
| r             | smoothing radius of SST data; radius centered from a given point within which satellite SST data are used | 200               | nm       |

# Other options #

| **Option** | **Usage** | **Initial value** | **Unit** |
|:-----------|:----------|:------------------|:---------|
|var.struct  | 3 different assumptions about variability in the latitude estimation error over time: 'uniform','solstice','daily' | See R help, ?kftrack in kftrack library | N/A      |


# For new users of electronic tagging ... #

Electronic tags, also referred to as data storage tags or biologgers, are miniaturized data loggers that provide measurement capabilities. Sizes of these tags have been dramatically reduced from the early days, when a tag resembled a backpack to nowadays where an implantable tag can be as tiny as a vitamin pill. The electronic components include a clock, a pressure (depth) sensor, a temperature sensor, and often a light level sensor. Salinity, fluorescence, pH and sonic measurements are available in some specialized studies ([Laidre et al. 2010](http://www.informaworld.com/smpp/content~content=a924373410~db=all); [Papastamatiou et al. 2007](http://journals.cambridge.org/abstract_S099074400800003X); [Meyers et al. 2010](http://www.springerlink.com/content/a524378202138363/abstract/)). Additional sensors like accelerometer ([Houghton et al. 2009](http://www.springerlink.com/content/h0m753m7581u113x/)) and magnetometer ([Sturlaugsson et al. 2009](http://www.star-oddi.com/resources/Files/Sturlaugsson-et-al-ICES-09_revised.pdf)) can further expand a tag's measuring capacity.

![http://tagbase.googlecode.com/svn/trunk/images/TagTypes.png](http://tagbase.googlecode.com/svn/trunk/images/TagTypes.png)

> _Tags used in studying marine animals. Clockwise from the top left: (a) conventional tags of various forms. The elongated plastic tags are often referred as spaghetti tags;(b) a pop-up satellite archival tags (PSAT or PAT) attached on a striped marlin (red arrow); (c) a Lotek Wireless LAT-series archival tag; (d) surgical implanting of an archival tag in an albacore tuna. Note the sensor stalk protuding out from the fish on the top right; (e) a resting Southern elephant seal carrying a Argos satellite telemetry tag; and (f) an advanced archival tag package with accelerometer and digital camera mounted on the dorsal fin of a tiger shark. Photo credits: Pfleger Institute of Environmental Research (a,b); Lotek Wireless Inc. (c); National Marine Fisheries Service (d); Chris Oosthuizen (e); and Hawaii Institute of Marine Biology, Shark & Reef Fish Research (f)._

Measurements are logged on solid-state memory on RAM with capacity of 16 to 128 MB, or on Flash cards with capacity over 1GB ([Wilson et al. 2008](http://www.int-res.com/articles/esr2007/3/n003pp12.pdf)). Data can be sampled every second or fraction of second in high-frequency tags (e.g. daily diary tags; [Wilson et al. 2008](http://www.int-res.com/articles/esr2007/3/n003pp12.pdf)). Realistically speaking, writing data at a frequency of 1 Hz or higher only allows for short-term deployments (< 1 month) and is geared towards studying detailed 3-dimensional movements such as body orientation during diving ([Gleiss et al. 2009](http://www.springerlink.com/content/x3310qvq5257610h/); [2010](http://onlinelibrary.wiley.com/doi/10.1111/j.1365-2435.2010.01801.x/abstract); [Whitney et al. 2010](http://www.int-res.com/abstracts/esr/v10/p71-82/)). For most pelagic fish species, data are usually logged every 30 seconds or 1-2 minutes, and any tag that samples at this rate will need to be physically recovered for complete data retrieval.

Standard button-size lithium batteries are usually used to power most tags for up to a designed 6 years of deployment, depending on sampling scheme. Solar panels are also added to some newer tags that theoretically can power a tag indefinitely, but practically serve as an option to extend battery life. The remaining design differences dichotomize into deployment platform, data recovery or transmission and tag retrieval mechanism

# Popular platforms #

#### GPS or Argos satellite radio-linked telemetry tags (SRLT) ####

Radio transmitters are the best way to track an animal via positioning satellites like GPS and [Argos](http://www.argos-system.org/). SRLT can provide accurate positions and are mostly used for birds, air-breathing animals and fish species that often expose their fins out of the water (Fig. e). These tags are deployed by gluing the device at the back (e.g. turtles, birds) or on top of the head (e.g. pinnipeds, cetaceans), or by attaching with support jackets (e.g. onto the caudal fin of a billfish), or by drilling holes and anchoring with bolts or ties (e.g. on the dorsal fin of a shark).

#### Archival tags ####

Archival tags, weighing from 0.5 to 45 grams in air, offer a much wider range of measured parameters (Fig. c), including visceral conditions such as body temperature ([Block et al. 2001](http://www.sciencemag.org/content/293/5533/1310.abstract)) and heart rates ([Clark et al. 2010](http://www.springerlink.com/content/g31237h57x056h34/abstract/)) when implanted (Fig. d). Since tags must be recovered to retrieve the collected data, archival tags are mainly deployed on species that are associated with a major commercial fishery. An archival tag can be attached by wiring it to a fish, as is usually done on cod and other groundfish. Alternatively, a tag can be surgically implanted inside the peritoneal cavity of large fish species like tunas, with a sensor stalk (light and temperature sensors) protruding out from the body cavity (Fig. d). More recently, the availability of miniature tags (< 2 grams) allows the implantation to be carried out in very small fish, for example salmon smolts. A tagged animal can carry the tags for months to years before recovery. Archival tags cannot record geographical positions and positions can only be inferred from measurement data.

#### Popup satellite archival tags (PSAT or PAT) ####
Pop-up satellite archival tags offer a fishery-independent solution to tagging animals. These tags are large versions of archival tags (~ 40 grams) that are combined with Argos transmitters, allowing collected data to be reported without physically recovering the tag. An animal is usually brought close to the boat, sometimes guided onto a cradle or brought on board, so that a tag can be harpooned near the base of the dorsal fin (Fig. b). A surgical nylon or metal alloy dart anchors the tag in place, and the tag can be towed along by the animal. At a pre-programmed time, an electric current is passed through the metal lead that connects the tag to the anchor, causing the connector to erode away within hours to a few days, depending on the ambient water temperature. An alternate release mechanism utilizes explosive pyrotechnics. The tag itself has floatation on the top, and will float onto the sea surface once detached from the animal. As soon as it appears on the surface, it can communicate with any over-passing Argos satellites, and transmit packets of collected data to the satellite system. Overall successful transmissions depend on geographical locations (e.g. noisy radio space in the South East China Sea). The final pop-off location is calculated through Doppler shift of transmitted radio frequency during the transmission uplinks with a satellite. Limited by the bandwidth of satellite transmissions and the battery life to power transmissions, only a subset or a summarized form of collected data can be transmitted and eventually available for download by the end-users. If a tag is physically recovered, as in the cases of being washed ashore or recaptured by a fisher, the same detailed time series as an archival tag provides can be retrieved. Pop-up tags have been applied to a wide variety of marine predators, including tunas, billfishes, sharks, rays, turtles, giant squids and sunfish.

#### Acoustic tags ####

Acoustic transmitters or pingers are archival tags that can be implanted in the peritoneal cavity of an animal such as salmon, or attached externally with epoxy or wires, e.g. on a lobster. Listening arrays or individual hydrophones can be used to receive data from the transmitters. Active tracking will involve following a tagged fish with a hydrophone, while data packets are received continuously at a receiver in a listening array whenever a fish is within the range of a receiver. At the end of a study, the receivers in the array are then retrieved and the complete data archive can be downloaded. Acoustic tags usually only measure depth and or temperature. They can be particularly useful in studying schooling fish, such as tunas around purse-seine fisheries using fish aggregating devices (FADs). Surface acoustic systems have also been developed, which are connected to Argos satellites for data transfer, allowing the monitoring of remote areas for an extended period of time for up to a year ([Dagorn et al. 2007](http://www.springerlink.com/content/h0q30607183x8005/abstract/)).

# Tag manufacturers #
_This list is not meant to be comprehensive. Please suggest more as comments_

  * Cefas Technology Limited (CTL): http://www.cefastechnology.co.uk
  * Desert Star Systems LLC: Underwater and Defense Systems : http://www.desertstar.com
  * Lotek Wireless Inc.: Fish and wildlife monitoring systems: http://www.lotek.com
  * Microwave Telemetry Inc.: Bird and Fish Tracking Transmitters: http://www.microwavetelemetry.com
  * Sea Mammal Research Unit: http://www.smru.st-and.ac.uk
  * Sirtrack: Wildlife tracking solutions: http://www.sirtrack.com
  * Sonotronics: Underwater Ultrasonic Tracking Equipment: http://www.sonotronics.com
  * Star-Oddi: Data loggers & sensors for fish research and other industries: http://www.star-oddi.com
  * Vemco: Acoustic telemetry for fish monitoring transmitters and receivers: http://www.vemco.com
  * Wildlife Computers: Electronic tags for wildlife research: http://www.wildlifecomputers.com

#### Overview of tag platforms available for animals submerged underwater ####
| **Tag manufacturer** | **Acoustic** | **Archival** | **Popup** | **Radio-linked telemetry** | **Signals used for geolocation**|
|:---------------------|:-------------|:-------------|:----------|:---------------------------|:--------------------------------|
| [Cefas](http://www.cefastechnology.co.uk) | -            | _Yes_        | -         | _Yes_                      | Light, Radio                    |
| [Desert Star](http://www.desertstar.com) | -            | _Yes_        | _Yes_     | -                          | Magnetic                        |
| [Lotek](http://www.lotek.com) | _Yes_        | _Yes_        | _Yes_     | _Yes_ (limited choices)    | Light, Radio                    |
| [Microwave Telemetry](http://www.microwavetelemetry.com) | -            | -            | _Yes_     | _Yes_ (birds only)         | Light                           |
| [Sea Mammal Research Unit](http://www.smru.st-and.ac.uk) | -            | _Yes_        | -         | _Yes_                      | Radio                           |
| [Sirtrack](http://www.sirtrack.com) | -            | -            | -         | _Yes_                      | Radio                           |
| [Sonotronics](http://www.sonotronics.com) | _Yes_        | _Yes_        | -         | -                          | Acoustic                        |
| [Star-Oddi](http://www.star-oddi.com) | -            | _Yes_        | -         | -                          | Magnetic                        |
| [Vemco](http://www.vemco.com) | _Yes_        | _Yes_        | -         | -                          | Acoustic                        |
| [Wildlife Computers](http://www.wildlifecomputers.com) | -            | _Yes_        | _Yes_     | _Yes_                      | Light, Radio                    |


# Other resources #

  * [Ocean Tracks - visualization by CSIRO's tagging research](http://www.oceantracks.csiro.au/thetags.html)
  * [Census of Marine Life - Tagging basics](http://www.coml.org/comlfiles/scor/SCOR-tagging.pdf)
  * Arnold, G., and Dewar, H. 2001. Electronic tags in marine fisheries research: a 30-year perspective. In **Electronic Tagging and Tracking in Marine Fisheries Reviews: Methods and Technologies in Fish Biology and Fisheries**. Kluwer Academic Press, Dordrecht. pp. 7-64.
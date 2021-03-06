

# Introduction #

This page shares some of our experiences in working with the software suite of [Wildlife Computers](http://www.wildlifecomputers.com/downloads.aspx), and namely DAP and GPE. This only serves as an practical guide to using their software, so you should refer to their documentation or customer service for detailed operations. You should also understand that manufacturers like Wildlife Computers has a rapid update/ release cycle on their software, and it is likely we lag behind in catching up with all their changes. We encourage you leaving us wiki comments at this page to help improve our collective experience in working with the software. Lastly, we are not advocating for any tag manufacturers, but rather we have yet to explore the many other options/ software, most of which are not free or easily accessible over the web.

# Details #

## Mixed processing of tags/ decoding of Argos messages ##

  * DAP allows simple drag-and-drop operation of any number of Argos messages (DS files in the form of .txt), Wildlife Computer binary files (.wch), and tag setup files (.htm) from Windows Explorer.

  * One approach to data processing involves saving all available Argos messages and setup files into 1 folder, and dragging that entire folder to DAP.

  * If you want to apply a filter, via specific PTT IDs (Argos platform transmitter IDs), you will need to click on "Filter" and fill out a form **before** you drag-and-drop.

![http://tagbase.googlecode.com/svn/trunk/images/WcDap1.jpg](http://tagbase.googlecode.com/svn/trunk/images/WcDap1.jpg)

  * "Export Decoded Data" in the "File" menu will allow you to export all the data from multiple tag into a single set of .csv files. This set will be used as inputs for import into Tagbase. Note at this stage, no geolocations are available.

![http://tagbase.googlecode.com/svn/trunk/images/WcDap2.jpg](http://tagbase.googlecode.com/svn/trunk/images/WcDap2.jpg)

  * If you open any one of the many .csv files, you will find "DeployID" and it is essentially the PTT IDs. In the absence of a PTT ID for an archival tag, the tag serial number is used for both "DeployID" and "PTT" data columns.

```
Tips -
For MiniPATs, make sure you output the setup file in the format of .wch,
so that you can drag-and-drop into DAP when you process the Argos messages.
Tagbase currently does not support the .rtf (rich text format) setup output
from the host software, MiniPAThost.
```

## Obtaining manufacturer light-based geolocation estimates via GPE ##

There are 2 ways to invoke GPE:

#### 1. Within DAP ####

  * Through the menu bar of DAP Processor ("Tag" > "Light Level Global Position Estimator")

![http://tagbase.googlecode.com/svn/trunk/images/WcDap3.jpg](http://tagbase.googlecode.com/svn/trunk/images/WcDap3.jpg)

  * From the list, select a tag to process or choose "All" for automatic processing. Wait until processing is completed. Make any "expert" adjustments in discarding light curves or changing processing parameters where appropriate (you will have to consult Wildlife Computers documentation/ customer service for assistance).

  * Return to DAP by saving the results of GPE via "File" > "Save Changes and Close"

  * In order to keep your estimated positions, you should save the entire workspace in DAP via "File" > "Save Workspace", a file with the extension ".wcdap" will be generated.

  * The geolocation estimates (including those using the Kalman filter interface) will be saved to the .csv files when you choose "File" > "Export Decoded Data" > "Popular Formats (`*`.`*`)"

#### 2. Standalone ####

  * Start "Global Position Estimator" from your Windows Start menu (under Wildlife Computers), drag-and-drop a "`LightLoc.csv`" file (that you have generated from DAP) or a previously processed GPE file (.wcg2) from your file explorer/ browser.

  * If your "`LightLoc.csv`" file has data for more than one tag, choose from the list which one to process:

![http://tagbase.googlecode.com/svn/trunk/images/WcGpe1.jpg](http://tagbase.googlecode.com/svn/trunk/images/WcGpe1.jpg)

  * Save the results, "File" > "Save" as a .wcg2 file to your preferred location for later use

  * Export the results back to a "`LightLoc.csv`" via "File" > "Export results in CSV format". This will overwrite your existing "`LightLoc.csv`"

![http://tagbase.googlecode.com/svn/trunk/images/WcGpe2.jpg](http://tagbase.googlecode.com/svn/trunk/images/WcGpe2.jpg)


## Utilizing Kalman filter/ Trackit interfaces in GPE ##

  * If you want to use **Kalman filter interface** or **Trackit interface**, proceed to do so via the "File" menu. Save & export after estimation is completed.

  * Choosing **Kalman filter interface** with start another window where **Kftrack** or **Ukfsst** can be run within the program.
  * Parameters can be changed, saved and reuse through the options in the dialog

  * Choosing **Trackit interface** exposes the options to generate data files for running light only or light+SST in R.
    * Start up R to run the script and copy-and-paste lines of code
    * Make sure you double-check the information listed in `fix.first` and `fix.last` as they might not correct
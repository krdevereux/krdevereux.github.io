# Environmental Scientist and GIS Analyst
My background is primarily in environmental sciences, especially marine and estuarine sciences, with a focus on GIS. I aim to combine my scientific background with my skills in geospatial analysis. This webpage provides further information on my background and examples of some of the outcomes of the work I have done in GIS.

## Education
- M.S., Marine Science | University of North Carolina Wilmington (_May 2024_)
- B.A., Environmental Geoscience | The College of Wooster (_May 2021_)

## Technical Skills
ArcGIS Pro, ArcGIS Online, ArcGIS StoryMaps, R, Python and ArcPy, LiDAR and point cloud processing, drone mission planning, Pix4D, Global Mapper

## Projects

### Heat Risk Index

   I calculated a heat risk index for the zip codes associated with Baltimore, MD to illustrate which parts of the city face the most risk associated with high temperatures. The initial index included only average high temperature, percent tree cover, and population density, but I am working to also incorporate demographic factors, such as percent of population over 65, as additional factors that contribute to higher risk from heat.
![Heat Risk Index](/assets/hri_baltimore.jpg)

### Waste Water Treatment Plants near Oneida Lake, NY

   Oneida Lake in upstate New York frequently experiences blooms of harmful cyanobacteria that can result in beach and recreation closures. While naturally eutrophic due to its large watershed and surrounding geology of nutrient rich soils, additional contributions of nutrients from waste water treatment plants (WWTPs) can cause harmful algal blooms to become more common. New York is currently working on creating numeric nutrient criteria for their freshwater lakes and reservoirs that would help ensure dischargers are not contributing an excessive amount of nutrients to important waterbodies. However, the current narrative nutrient criteria in place in NY requires that site-specific numeric nutrient criteria are calculated by permit writers when authorizing discharges from facilities such as WWTPs. The first step for determmining these numeric criteria is to identify all upstream dischargers contributing nutrient loads to the waterbody of interest. This was the goal for this map - to identify all WWTPs discharging to waters upstream of Oneida Lake. I chose Oneida Lake as an example case study for assessing a method for translating narrative nutrient criteria into numeric criteria.

   To create this map, I first downloaded the relevant NHDPlus dataset, which includes flowlines and waterbodies (https://www.epa.gov/waterdata/nhdplus-great-lakes-data-vector-processing-unit-04). I then used the nhdplusTools package in R to identify all stream reaches upstream of Oneida Lake. I then intersected these streams with the boundaries of a HUC12 watershed layer, and then dissolved the watershed boundaries to produce a border for the Oneida Lake watershed. I created 5, 10, and 15 mile buffers around Oneida Lake and then used spatial joins with these buffers and the upstream watershed polygon to select the WWTPs discharging into streams that flow into Oneida Lake. The final map is below, and a copy of my R code using the nhdplusTools package is pasted below that.

   ![OneidaLakeMap](/assets/OneidaLakeMap.jpg)

   I decided to use a dark theme for this map in order to highlight the points of interest and the target waterbody. The upstream reaches identified by the nhdplusTools process in R are included as gray lines, emphasizing the size of the watershed. I additionally created an vingette effect around the Oneida Lake watershed so that other WWTPs in the area were visible but wouldn't distract from the WWTPs within the 15-mile distance zone around Oneida Lake. The inclusion of these stream reaches also demonstrates that although there are several other WWTPs within 15 miles of Oneida Lake, they do not discharge into the Oneida Lake watershed and therefore do not need to be included for this exercise. 

R code:


### Storm Surge Inundation in Pamlico County, NC

   For this project, I was interested in the impacts of hurricanes on coastal North Carolina. I used the Sea Lake and Overland Surges from Hurricanes (SLOSH) model display program from NOAA to obtain flooding scenarios for different storm categories. I overlaid the results with Pamlico County data for building footprints to illustrate which structures would likely be inundated during different storm surge scenarios.

   ![Pamlico Storm Surge](/assets/pamlico_ss.jpg)

### Master's Thesis StoryMap

   In my master's thesis project, I used dendrochronology (the study of tree rings) to evaluate the impact of saltwater intrusion on bald cypress growth. To expand upon this research, I compared my sample locations to various remote sensing data and presented these findings in a [StoryMap](https://arcg.is/CLifK).

### Undergraduate Thesis Analysis of Precipitation Across the Continental US

   As a senior undergraduate student of environmental geosciences, I completed a year-long GIS thesis project in which I calculated different components of the water budget (precipitation, runoff, and evapotranspiration) in order to estimate groundwater recharge rates across the continental US (CONUS). Below is an example of one of these water budget components - precipitation. To calculation precipitation rates across the CONUS, I used data from the PRISM Climate Group at Oregon State University, which provides precipitation estimates at an 800m resolution for the 1981-2020 30-year normal. The precipitation component also included irrigation because, in certain parts of the CONUS, especially the drier West, irrigation contributes significantly to the water available for evapotranspiration, runoff, and recharge. Irrigation data by county came from the 2010 USGS Water Use data set (Maupin et al., 2014).

   ![Effective Precipitation](/assets/effective_precip.jpg)
   
### Analysis of Chesapeake Bay Water Quality in Relation to Oyster Sanctuaries

   For an undergraduate GIS course final project, I was interested in exploring the spatial patterns of water quality in the Chesapeake Bay. I am highly interested in the restoration of the Bay and believe strongly in the importance of oysters in contributing to improved water quality. I therefore wanted to analyze water quality patterns as they relate to oyster sanctuary locations. My final poster demonstrated that the location of oyster sanctuaries did not have an impact on water quality trends, but that water quality across the Bay did improve over the study period. I combined the use of ArcGIS and R for these analyses.

   ![Oyster Poster](/assets/gis_oyster_poster.jpg)

### NDVI and Thermal Imagery Map Produced with Drone-Collected Data

   In a graduate level class I took on drone applications, we traveled to the EV-Henwood Nature Preserve in North Carolina and flew a DUET-T Thermal camera aboard the eBeeX RTK drone. This drone and sensor collected both multispectral and thermal images, and I used these data to describe some site characteristics. I first calculated a normalized difference vegetation index (NDVI) for the sample area:
   
   ![NDVI of EV-Henwood Nature Preserve](/assets/ndvi_ev-henwood.jpg)

   I then used the thermal imagery collected by the drone to produce a map of the temperature range across the sample area:

   ![Thermal Range of EV-Henwood Nature Preserve (F)](/assets/thermal_ev-henwood.jpg)
   


# Pittsburgh-Municipality-Refund-Regression-Analysis

---
class:  Programming in R for Analytics, Fall 2017, Section B2
title:  Project
---

#### 1. Premise (some language from Blackhurst 2017)

The Pittsburgh region is served by a combined sewer, which collects, conveys, and partially treats both stormwater and wastewater in the same infrastructure system. During periods of heavy rainfall, stormwater can exceed the capacity of combined sewers, which causes overflow into nearby rivers and streams. While these combined sewer overflows or CSO's mitigate upstream flooding, they release untreated wastewater into receiving water bodies. CSO's are regulated by state and federal authorities, thus cost effective strategies to manage CSO's are important for local municipalities. 

Improvements to âgrayâ infrastructure - pipes, pumps, storage, and treatment facilities - can increase the capacity of the collection system to accommodate more severe wet weather events. Conversely, âgreenâ infrastructure includes features that reduce the stormwater entering the collection system by temporarily retaining or diverting stormwater. Types of green infrastructure vary from completely natural systems, such as converting a parking lot to a park, to single purpose engineered systems, such as pervious paving.

While gray infrastructure strategies involve modifying public property, many green infrastructure strategies involve modifying private property. In particular, both rain gardens and trees involve retrofitting exterior space on private property. There are advantages and disadvantages to these three uses of outdoor space: open space ("grassy yard"), trees, and raingardens. For each of these uses of outdoor spaces, property owners will value differently effects on aesthetics, environmental impacts, maintenance, and outdoor uses (e.g., recreation is feasible on open space but not on a rain garden). Thus, it is importatnt to understand how property owners value these amenities before considering rain gardens and trees as a stormwater management strategy.  

Say a Pittsburgh municipality was considering initiating a rebate program for residential property owners to install rain gardens and/or plant trees for the purposes of stormwater management. The municipality reaches out to you with assistance with the following questions:

(1) How much do residential property owners value - if at all - exterior open space?
(2) How much do residential property owners value - if at all - trees?
(3) What is the mean rebate per square foot of rain garden and per tree the municipality should offer property owners to incentivize their installation? See Section 3 for additional assumptions. 
(4) On the basis of rebate per overflow reduced, what five areas of the city (sewersheds) are the most cost effective at reducing combined sewer overflows? 

#### 2. Description of information provided

You collect the following information posted on the Amazon server for the course. 

(1) Sales prices for residential properties in Allegheny County (sales_county.csv);  
(2) Descriptions of residential properties in the City of Pittsburgh (assessments_city.csv);
(3) Land use data for parcels in the City (land_use_city.csv);
(4) Sewershed locations for parcels in the City (sewersheds.csv).

Similar to a watershed, a sewershed is an area of land that drains to the same collection sewer. A map of Pittsburgh sewersheds is at http://www.pgh2o.com/Find-Your-Sewershed. The sewershed data also include the ratio of combined sewer overflow reduced (at the river) for every gallon of runoff reduced upstream on the surface. This ratio is described as "CSOperInfl."

An abbreviated data dictionary is also provided on the Amazon server (data_dictionary.xls). 

While you are not likely to need them, references for these data sets are included below and linked in the data dictionary. (Note that the raw data have been extensively curated to simplify the project.) 

#### 3. Estimating the rebate amount

The rebate will be calculated as compensation for the use of private property plus installation costs. 

##### 3.b. Compensation for the use of private property

The municipality is considering offering compensation to property owners for converting their private assets into a partly public amenity. However, it all depends on your answers to questions 1 and 2, which will indicate a positive valuation, a negative one, or be undetermined. The results will apply differently for trees and rain gardens. 

For rain gardens, the municipality will compensate property owners for the open space occupied by rain gardens ONLY if owners value open space per your results from question 1. Otherwise, no compensation for use of private property will be provided. 

For trees, no compensation to occupy open space will be offered. Municipalities plan to compensate owners for planting a tree ONLY if property owners negatively value trees. If you estimate a positive or underdetermined value for trees, assume no compensation is required for tree planting. Otherwise, use your results from  question 2 to estimate compensation. 

##### 3.b. Installation costs and stormwater performance 

Assume the following mean installation costs and stormwater performance data.

|  Amenity     | Diameter | Installation cost      | Stormwater performance                       | 
|--------------|----------|------------------------|----------------------------------------------|
| Trees        | 25 ft    | $20 per tree           | 1000 gallons of runoff reduced per tree      |
| Rain gardens | NA       | $6 per square foot     | 3.5 gallons of runoff reduced per square foot|



####  REFERENCES

Blackhurst. MF. (2017). "Parcel Scale Green Infrastructure Siting and Cost Effectiveness Analysis." http://sb.ucsur.pitt.edu/green-infrastructure/

Allegheny County. âAllegheny County Urban Tree Canopy.â Division of Computer Services Geographic Information Systems Group, 2010. http://www.pasda.psu.edu/uci/MetadataDisplay.aspx?entry=PASDA&file=AlleghenyCountyUrbanTreeCanopy2010.xml&dataset=1203.

âââ. âAllegheny County Wooded Areas.â Division of Computer Services Geographic Information Systems Group, 2011. http://www.pasda.psu.edu/uci/MetadataDisplay.aspx?entry=PASDA&file=AlleghenyCounty_WoodedAreas2011.xml&dataset=1228.

âââ. "Allegheny County Property Assessments." https://data.wprdc.org/dataset/property-assessments

âââ. "Allegheny County Property Sale Transactions." https://data.wprdc.org/dataset/real-estate-sales

City of Pittsburgh. âParcels.â Geographic Data, 2015. http://pittsburghpa.gov/dcp/gis/gis-data-new.
âââ. âStreet Curbs.â Geographic Data, 2015. http://pittsburghpa.gov/dcp/gis/gis-data-new.

PWSA (Pittsburgh Water and Sewer Authority). 2016. Sewershed Overview Map. http://www.arcgis.com/home/webmap/viewer.html?webmap=f96943c1e46e48dcad9abe5282bc58a8&extent=-80.2691,40.3363,-79.7621,40.5663

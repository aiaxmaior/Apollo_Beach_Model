# Case Study: Apollo Beach’s Commercial Pier
Evaluation and Selection of Marine Restoration Installations through ML Models
The aim of this project is to utilize standard Data Science practices and utilize machine learning to inform decisions about human-induced ecosystem degradation and ecosystem restoration installations that can mitigate or mollify that damage.
This project follows an ongoing project to build a commercial dock in Apollo Beach, Florida – a coastal community that sits in ‘Middle Tampa Bay’. Coastal construction of any kind has a large impact on the health of the local ecosystems. Disruption, dredging of the sea floor can permanently destroy entire ecosystems. 


### Objectives and Goals:
The construction of a new dock will cause inevitable damage to the local habitats, impacting species diversity and reducing resilience of the ecosystem. In an effort to combat this, this study aims to employ data science techniques, including the design of an ML model, that can determine the most efficient and feasible restoration installations that can reduce the overall impact of the construction. As a case study, this project aims to serve as an example of how realistic efforts can help create a healthy medium between the burgeoning demands of humanity and the health of our natural resource and ecosystems. 

### Current Status:
The project is in the early stages of development. Presently, additional data sources are being consolidated. We have begun the process of cleaning incoming data and conducting preliminary EDA on the data. Due to the size and scale of the study, these first steps are being conducted on a subset of data, specifically benthic environments, placing an emphasis on species diversity, richness and the development of a baseline model that can serve as a template for further implementation among the other data sources.

### Description of Data:
Data has been acquired from a variety of sources in multiple formats. Each data set contains multiple tables that describe individual habitats and ecosystems found in Tampa Bay – or describe the anthropogenic negative pressures on these ecosystems. At present, the latter consist of coastal construction data and marine transit and recreational activity.
Ecological data describes: benthic, pelagic, mangrove, oyster reef and seagrass ecosystems.
Anthropogenic data describes: coastal construction, maritime activity and artificial nitrogen loading from local agriculture, residential communities and commercial sites. 
There are limitations on the data due to availability of historic data regarding damaging human activity. While efforts are ongoing to amas additional data, the current set describe human activity from 2019-2024. Biological data is more available with relative consistency from 1993 to the present day.
There is the possibility of bias to be found in the data given their disparate sources. Anthropogenic data have a tendency to omit details that describe incidents. Additionally, since some of the data has been sourced from private entities from local industry, it is always possible that the authors of that data will skew it in favor of the competing interests behind the damaging factors involved in the study. Best efforts are being made to control this – either by dismissing this data or inferring missing information through supplementary data acquired through other means. This does involve manually researching key events or large construction projects that would invariably have a negative impact on the local ecosystems.
A list of the current data sets can be found with the references at the end of this document.

### Description of Work:
The project is still in the pre-processing stage. Data that describe environmental degradation are harder to acquire and require manual research. Data concerning ecosystem health is more readily available either through local regulatory agencies and academic institutions.
Preliminary Analysis Methodologies:
There has been no attempt to perform any type of significant regression on the processed data yet. Given the differences in scale of independent variables, using normalized regression methods is required to determine an accurate representation of continuous data. Reduction of features in the data, implementation of dummy variables and examination of collinearity and multicollinearity is ongoing. It is clear that it is present in the data and that’s to be expected. Measurements, such as temperature at the top vs the sea floor can have relatively little variation; however, this can still be important. Estuarine systems comprise a portion of the data – these systems are highly stratified by salinity and temperature which necessitates its inclusion in the EDA and should not be removed from the data set yet. This will be especially relevant when the data starts to account for sampling in overlapping environments – such as seagrass beds – which requires segmentation of those data.
Target Features: Indices and supplementary data of interest
Shannon-Weiner Diversity Index: A proxy measurement of overall ecosystem health and complexity
Calculation of this index is calculated as:
s
H’ = - Σ pi ln pi
i =1
where H’ is the Species Diversity Index (SDI), s is the number of species, p¬I is the proportion of individuals of each species belonging to the ith species of the total number of individuals.¬2 (Nolan,K. Callahan, J. 2006)
Tampa Bay Benthic Index (TBBI)
TBBI is a ecosystem specific index formulated by Tampa Bay Estuary Program  to describe ecosystem health.  This value is calculated by a series of transformations of environmental and biological values including linear regression, linear discriminant analysis, normalization. The description of this transformation can be found in the referenced literature at the end of this document. 3
11.01.2024. EDA Summary (detailed analysis can be found in the Jupyter notebooks):
EDA has described some key aspects about the data:
-	The frequency of benthic sampling is not consistent over time. There is a heavy skew towards data collected in the early 2000s. 
-	Measurements of Species Richness and the derived calculated value Shannon Diversity index describe a decrease in ecosystem health in the early 2000s. The trend of these values are similar to those found in the frequency of sample. While it can be inferred that these are linked, additional statistical analysis is needed to prove any type of significance.
-	Species Richness and SDI has become weaker in recent years. Richness has trended upwards while Diversity has decreased since 2015.
-	Line plots of SDI over time have sharp  drops in values – some nearly hitting zero. This requires investigation – whether there are flaws in the data not identified during cleaning, zero sample events or other causes. It did raise the question, however, of looking at catastrophic events in the region – such as hurricanes and tornados  - analogous in relative scale to events like COVID. 

### Detailed Description of EDA Analysis:
So far, a subset of benthic ecosystem data has been cleaned and used for a preliminary EDA. This subset focuses on the geographic region surrounding the case study construction site. The raw data describes sediment toxicology, standard practice sampling information (GPS, temperature, salinity, dates), and species collection. 
As this dataset was explored, the need for a standardized measurement of ecosystem health is needed. Due to its wide applicability in any given environment, It was determined that the Shannon-Weiner Diversity Index (SDI) has the potential to represent a normalized value. This would allow for measurements, comparisons among ecosystems. Ultimately, with supplementary data, it can be used to create a composite, weighted index to represent the overall health of Tampa Bay.
Plotting of the overall data sets demonstrates sampling in a variety of habitats throughout the bay and nearby coastal systems. The overall dataset is comprehensive and will be sufficient, in complement with other data sets, for the overall goals of this study.
In a healthy ecosystem, SDI is expected to have a close relationship with Species Richness. It is surprising that the correlation between the two isn’t as strong over time as expected in the data. This could be due distribution of sampling over time. It can also indicate stress on the ecosystem from outside pressures. In this case, species richness has trended upwards while diversity has returned to original levels from when the data collection began. 



### Visuals (to be inserted)

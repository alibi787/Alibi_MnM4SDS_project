# Measuring the urban similarity between Washington, DC and Boston, MA through bikeshare moblity signatures

•	Potential sources of data:

 I am planning to use the historical DC Capital Bikeshare trip data that is collected from AWS data archives. The data was collected since 2010 and prior to 2017, it was updated quarterly. From 2018, datasets are collected with a monthly frequency. Each monthly dataset has on average 300,000 observations. The data will be further enriched by the Capital Bikeshare real time GBFS feed data collected through APIs if necessary. The data is provided in the csv format and contains the following information: 

-	Unique ride ID
-	Bike type: classic/electric/docked
-	Start time
-	End time
-	Start location address, ID, longitude and latitude coordinates
-	End location address and ID, longitude and latitude coordinates
-	User status: member/casual

 Since one of the analysis objectives is to infer the regional similarity between different US cities, I am also going to work with the historical Boston Bluebikes trip data that was found on AWS data archives. Upon initial look, this data was collected from 2015 on monthly basis and contains the information similar to Capital Bikeshare data. The data is provided in csv format and has over 400,000 observations for each month. The real-time GBFS feed data is also available and can be used based on the analysis needs. The common limitation of data is that it does not provide more detailed information on the users such as sociodemographic characteristics. However, this data should be enough to analyze the mobility patterns of service users.

•	Study area- where and why 

 The study focus will be to examine the regional similarity within and between different US cities, namely, Washington DC and Boston, MA through the analysis of the spatiotemporal mobility patterns of citizens using the bikeshare use data for both cities. The mobility patterns of urban residents were rarely used as the way to measure urban similarity as it is typically done by relying on the comparison of the sociodemographic composition and urban morphology of the city. Only a single study by McKenzie and Romm (2021) attempted to differentiate regions within a city and between multiple cities in Europe based on mobility signatures of micro-mobility service users (i.e., free-floating e-scooter service). However, this study will focus on comparing two cities in the US and instead use the bikeshare service use data. The bikeshare service has operated for more than a decade in DC and Boston and might reveal a more accurate representation of mobility patterns of residents of both cities as opposed to relatively recent micro-mobility options such as dockless e-scooters. Both DC and Boston are east-coast cities that have active and seasoned bikeshare service and, at first glance, share similar population and infrastructure characteristics. This makes two cities good candidates for the regional similarity analysis. 


•	Question or task 

 The primary outcome of the analysis will be to create the composite similarity index comparing different regions within each individual city and between cities. Similar to McKenzie and Romm (2021), this index will likely be based on so-called mobility signatures measured through the volume trips by distance traveled, number of unique trip origin/destination regions by distance traveled, and aggregate temporal signature by distance traveled. The mobility signatures of bikeshare users might further be distinguished based on the membership status of users. Next, the aggregation of trip volumes, trip origin and destinations into regions will be done by using hexagon tessellation, as proposed by McKenzie and Romm (2021), or, alternatively, using the appropriate clustering technique or relying on existing administrative boundaries (e.g. census blocks). After trips are split into origin and destination regions, they will also be grouped into separate time intervals relative to trip start and end times. An important methodological challenge to consider would be in regards to measuring the similarity between regions. In McKenzie and Romm (2021), the common cosine similarity measure is used that varies between 0 (complete dissimilarity) and 1 (identical). However, this study will attempt to find an alternative similarity measure. 

 Additionally, similar to McKenzie and Romm (2021), this study will try to come up with a prototypical region that best represents the city as a whole and compare these regions between two cities. Moreover, this study might look at how mobility signatures in each city changed during the COVID-19 pandemic and emphasis will be made on observing whether the pre-pandemic regional similarity within and between cities changed during different phases of the pandemic (stay-at-home order, reopening, winter-flu season, and vaccination phase). 

•	Python tools:

 This study would require to write the custom code but it will also rely on the python modules such as those that would allow to conduct the network analysis and build OD cost matrices. The python modules used for hexagon tessellation and clustering techniques such as k-means clustering will be applied. If selected as the similarity measure, the python module to compute the cosine similarity such as the scikit-learn will also be used. 

•	Envisioned challenges:

 The main challenge will be to develop the aggregation method of origin and destination regions which will be appropriate for observed mobility signatures in two cities simultaneously. Both DC and Boston might display quite distinct mobility signatures in terms of the spatial extent that will make the process of aggregation complicated. Another challenge will be to measure the similarity temporally as it would require to compare each pair of regions temporally at each distance.  
 

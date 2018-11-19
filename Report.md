### Capstote week 4


### Introduction/Business Problem

Its very challenging to find a house in London, UK. There are many websites out there that try to help you out with searching your house like zoopla, rightmove. But even then narrowing down area to look for is a manual task that these websites do not automate/provide. Narrowing down area can be very tedious and time consuming process.

This project attempts to help you with identifying or narrowing down the search for the house according to your prefernces about the neighbourhood. 
For example, one might want to look at all areas which has proximity to pubs, cafes, public transport etc. This project attempts cluster areas based on your provided preferences/categories. We then print those clusters on the map to distinguish between areas. That should make it easy to choose a certain areas to look for and narrow down your search.

**Stakeholders/Target Audience**: People who are looking to find house in London, especially the people who are starting their house search and has a certain prefrences in the mind.

Note that this project attempts to solve the first step of your house search only, not everything. Websites mentioned above are still relevant and should be seen as complimentary to this project.


### Data

I plan to use two datasets:

  1. London Lewisham council postcodes data downloaded from [Doogle](https://www.doogal.co.uk/AdministrativeAreasCSV.ashx?district=E09000023): We narrow down to lewisham council (and mainly focus on forest hill ward) to minimize the calls to FS apis. This dataset contains all postcodes present in the lewisham council in London. Example data look like:

```
Postcode	In Use?	Latitude	Longitude	Easting	Northing	Grid Ref	Ward	Parish	Introduced	Terminated	Altitude	Country	Last Updated	Quality
BR1 4BY	Yes	51.417289	-0.001741	539050	170591	TQ390705	Downham	Lewisham, unparished area	1980-01-01		35	England	2018-11-15	Within the building of the matched address closest to the postcode mean
  ```
Lewisham council postcodes data has many columns but out of those only Postcode, Longitude, Latitude and Ward of the postcode are of our interest. We can then use these postcodes to look up in the FourSquare API to get results about categories which are in the proximity. We then use that data to create and analyse clusters of areas.

  2. Foursquare venues data with categories


**Assumptions**: Data is downloaded from Doogle and it comprises of postcodes in Lewisham council In London, UK. Assuming that this data is limited and doesn't represent actual availability of the house. But that should be easy as we could just focus on the area here. I am going to focus on only Forest Hill part of the Lewisham as FourSquare api has aggressive rate limit for explore api of 500 calls/day.

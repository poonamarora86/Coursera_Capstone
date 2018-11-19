### Capstote week 4 Report


### Introduction/Business Problem

Its very challenging to find a house in London, UK. There are many websites out there that try to help you out with searching your house.
But even then which area to look for is a manual task that these websites do not automate.

This program attempts to help you with identifying the areas of houses according to your prefernces about the neighbourhood. For example, 
one might want to look at all areas which has proximity to pubs, cafes, public transport etc. This program creates various clusters based on 
areas with proximity to a certain amenities. By looking at cluster it attempts to narrow down your search area to your preferred areas.

### Data

We use two datasets:

  1. London Lewisham council postcodes data - we narrow down to lewisham, forest hill to minimize the calls to FS apis. This dataset contains all postcodes present in the lewisham council in London. Example data look like:

```
Postcode	In Use?	Latitude	Longitude	Easting	Northing	Grid Ref	Ward	Parish	Introduced	Terminated	Altitude	Country	Last Updated	Quality
BR1 4BY	Yes	51.417289	-0.001741	539050	170591	TQ390705	Downham	Lewisham, unparished area	1980-01-01		35	England	2018-11-15	Within the building of the matched address closest to the postcode mean
  ```
Lewisham council postcodes data has columns like Postcode, Longitude, Latitude and Ward of the postcode.

  2. Foursquare venues data with categories



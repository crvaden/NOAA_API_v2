# Description
A Python module for the NOAA Web Services v2 API

http://www.ncdc.noaa.gov/cdo-web/api/v2/

## Requires
* Python 3.5
* Requests
* API Token - http://www.ncdc.noaa.gov/cdo-web/token

## Usage
```
from noaa_api_v2 import NOAAData
api_token = "your token here"

data = NOAAData(api_token)

categories = data.data_categories(locationid='FIPS:37', sortfield='name')

for i in categories:
    print(i)
```
## Additional Information
Available methods are:
* datasets
* data_categories
* data_types
* location_categories
* locations
* stations
* dataset_spec
* fetch_data

Parameters can be passed as arguments within the method call:
```
weather_data = data.fetch_data(datasetid='GHCND', locationid='ZIP:28801', startdate='2010-05-01', enddate='2010-05-02', limit=1000
```
Calling a method without the minimum required parameters will result in a 400 error. Read the API docs to determine what, if any parameters are required by each specific method.

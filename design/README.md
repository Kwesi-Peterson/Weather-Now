# Architecture

The architechture for the ETL pipeline is as below:

![Markdown Logo](https://github.com/Kwesi-Peterson/Weather-Now/blob/main/design/weatherNowArchitecture.jpg)

Describing the steps:
1) Use the [One Call API](https://openweathermap.org/api/one-call-api) from the Open Weather API to get access to current and forecast weather data.
2) Store the data initially in a Bronze delta lake
3) Regularly filter, clean and augment the data and store in a Silver data lake
4) Copy the data into Azure Storage for long-term storage
5) Create curated data for specific insights.

# Open Weather API Details
The docs for the One Call API can be found [here](https://openweathermap.org/api/one-call-api). In particular, the data returned is in a complex nested Json Schema format.

Pricing Model and SLAs can be found [here](https://openweathermap.org/full-price#current). In particular, on the Free plan, we can only do 1,000 calls per day.

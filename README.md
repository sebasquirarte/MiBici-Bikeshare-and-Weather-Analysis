![Bikeshare_cover](https://github.com/user-attachments/assets/61ce6b49-d8dc-4d4e-9142-315b06d4c5cc)

## Overview
[MiBici](https://www.mibici.net/) (translated as *MyBike* in english) is a public bike service used in my home city of [Guadalajara](https://en.wikipedia.org/wiki/Guadalajara) (GDL), Jalisco, Mexico. This service is used in Guadalajara's Metropolitan Area, which has a population of 5,268,642 (as of 2020) distributed in eight main municipalities and a total area of 2,543.13 squared km (981.91 squared mi).

This service has established stations where users can take and return a public bike, all they need is to sign up through MiBici's platform and pay a charge for 1, 3, 7 days, or annual use. After signing up, users get a transport card that can be used at any station in Guadalajara's Metropolitan Area.

MiBici makes their data public and has published it every month since December 2014.

This repository includes R scripts to merge, transform, and clean data from 4,496,890 bike trips registered in 2024 and hourly weather data obtained through the [Open-meteo API](https://open-meteo.com/), as well as the combined bikeshare + weather data available as csv file. 

## Data

Data was obtained directly from [MiBici's public data website](https://www.mibici.net/es/datos-abiertos/). In this site, data is published in CSV files corresponding to individuals month from December 2014 to Febuary 2025. Data from 2024 was downloaded, cleaned, and transformed into a hourly format, as well as merged with hourly weather data.

### bikeshare_weather_GDL_2024.csv variables:

| *variable*           | *description*                                                                            | *units*  |
| -------------------- | ---------------------------------------------------------------------------------------- | -------- |
| date                 | date in yyyy-mm-dd format (i.e. '2024-01-01')                                            | date     |
| month                | month of year (1 = jan, 2 = feb, ... , 12 = dec)                                         | month    |
| day                  | day of month                                                                             | day      |
| hour                 | hour of the day in 24 h format starting at 0                                             | hour     |
| trip_count           | count of hourly bike trips                                                               | count    |
| is_weekend           | is the day a weekend? i.e. saturday/sunday (1 = yes, 0 = no)                             | binary   |
| is_holiday           | is the day a federal holiday in Mexico? (1 = yes, 0 = no)                                | binary   |
| apparent_temperature | perceived temperature combining wind chill factor, relative humidity and solar radiation | °C       |
| wind_speed           | wind speed at 10 meters above ground                                                     | km/h     |
| is_day               | 1 if the current time has daylight, 0 at night                                           | binary   |
| temperature          | air temperature at 2 meters above ground                                                 | °C       |
| relative_humidity    | relative humidity at 2 meters above ground                                               | %        |
| precipitation        | total precipitation (rain, showers, snow) sum of the preceding hour                      | mm       |
| weather_code         | weather condition as a numeric code. Follow WMO weather interpretation codes (see below) | WMO code |
| season               | season of the year (winter, spring, summer, fall)                                        | category |

## WMO Weather interpretation codes (WW)

| *code* | *description*                 | 
| -------| ----------------------------- |
| 0	     | clear sky                     |
| 1      | mainly clear                  |
| 2	     | partly cloudy                 |
| 3	     | overcast                      |
| 45     | fog                           |
| 61     | rain: slight                  |
| 63     | rain: moderate                |
| 80     | rain showers: slight          |
| 81     | rain showers: moderate        |
| 95     |	thunderstorm                 | 
| 96     | thunderstorm with slight hail |

## Datasets available in Kaggle

2024 Guadalajara bikeshare and weather datasets available through [Kaggle](https://www.kaggle.com/datasets/sebastianquirarte/mibici-bikeshare-weather-data-2024). 

I have also cleaned, transformed, and combined all bikeshare data from Dec 2014 to Mar 2024 and published the final dataset (2.51 GB) in [Kaggle](https://www.kaggle.com/datasets/sebastianquirarte/over-9-years-of-real-public-bike-use-data-mibici).

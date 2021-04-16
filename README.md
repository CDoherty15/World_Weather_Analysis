# World_Weather_Analysis
Module 6 - Mapping Weather Data with google APIs
## Overview
All of the code in this repository leads to mapping out a travel route between four hotels in one country based on the user's minimum and maximum weather preferences
- Step 1: creating latitudes and longitudes and finding cities
  - I generated 2000 random number combos that will be then converted latitude and longitude combos. Next was to use the `citipy` module to find the city names for the coordinates, over 700 (725) cities were found with the coordinates provided
  - Then I use my OpenWeather API and parse through the data to see how many cities we can find current weather data on, we are now left with a little under 700 (675) cities. These cities were then put in a dataframe with the city name, country code, latitude,	longitude, maximum temperature, humidity, cloudiness, wind speed, and weather description. This was then exported into the Weather_Database.csv file
- Step 2: user weather preference
  - Next, was to take the user's weather preference based on temperature by asking what their minimum and maximum weather temperature preferences are. For this example, min = 70 & max = 80 were used, and a new dataframe is created based on the preferences and any rows with misssing data are dropped. 
  - Now, it is time to find hotels in the preferred cities by using google apis. Not all cities were returned and again, drop the rows without a hotel name, and now we have a dataframe with the preferred temperatures and all cities have hotels. 
  - The final task in this step was to create a marker map of all the cities in the cleaned data set and can be seen below:
![WeatherPy_Vacation_map](https://user-images.githubusercontent.com/79118630/115087477-38ed4680-9edc-11eb-994d-8b153c85a594.png)
  - All of this data was saved into the WeatherPy_Vacation.csv file. The code that was written alows the csv file to change and be rewritten every time new temperatures are entered.

- Step 3: Creating an itinerary
  - For the final step, I created a travel identity between 4 cities in a country, it is slightly cut off in this picture, but for this example I choose South Africa.
  - There were 4 cities that were marked in South Africa that were spread out, allowing for this traveler to see a good amount of the country. With the images below, we can see that there is a map route between the four cities. On the directions map, Saldhana is the starting location, even though it says E, Google automatically marks it as E because it is also the end location. 
  - As we can see by the two photos, the directions are mapped out and each marker contains the following information: hotel name, city, country (code), and weather description.
![WeatherPy_travel_map](https://user-images.githubusercontent.com/79118630/115087811-ec563b00-9edc-11eb-822b-9ad38bd2cbe2.png)
![WeatherPy_travel_map_markers](https://user-images.githubusercontent.com/79118630/115087826-f37d4900-9edc-11eb-9c37-d63f9451f556.png)

The code provided works with more than just South Africa as we can see from the first picture, the marker map will change based on the user's minimum and maximum temperature input. 

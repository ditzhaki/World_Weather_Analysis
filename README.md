# World Weather Analysis

## Overview

Planmytrip is a top travel technology company that specializes in internet related services in the hotel and lodging industry. They have asked for help in collecting and presenting data for customers via a search page, which they will then filter based on their preferred travel criteria in order to find their ideal hotel anywhere. Specifically, we focused on:

* Retrieving Weather Data
* Creating a Customer Travel Destinations Map
* Creating a Travel Itinerary Map

The results of our analysis can be viewed below.

## Results

### I. Retrieving Weather Data

The first step in retrieving weather data was to create a set of 2000 random latitude and longitude combinations which was achieved through the following code:

```
lats = np.random.uniform(low = -90.0, high = 90.0, size = 2000)
lngs = np.random.uniform(low = -180.0, high = 180.0, size = 2000)
lat_lngs = zip(lats, lngs)
lat_lngs
```

We then created a for-loop that functioned by looping through the cities in our list and running an API request for each city. The information obtained for each city was the latitude, longitude, max temperature, humidity, cloudiness, wind speed, country, and current weather description. Converting our results into a DataFrame gave us the following output:

![Screen Shot 2022-05-22 at 10 56 46 AM](https://user-images.githubusercontent.com/101564349/169701601-57136096-5463-4cbd-8136-11e6cdcb4b77.png)

### II. Customer Travel Destinations Map

Our second deliverable include creating a customer travel destinations map. This was done by filtering through our DataFrame based on maximum and minimum temperature inputs. After setting our parameters to search for hotels within 5000 meters, we obtained the following DataFrame, listing the city, country, max temperature, weather description, latitude, longitude, and hotel name.

![Screen Shot 2022-05-22 at 11 03 04 AM](https://user-images.githubusercontent.com/101564349/169701856-9ce76100-05f2-4669-b36d-92ee2dc6e0b7.png)

We were then able to plot our results onto a marker layer map seen below.

<img width="987" alt="WeatherPy_vacation_map" src="https://user-images.githubusercontent.com/101564349/169702009-9190b8e2-057b-4ad5-9f84-4fd173f46ebe.png">

### III. Travel Itinerary Map

Lastly, we created a travel itinerary map that shows the route between four cities chosen from the customer’s possible travel destinations. This was done by creating latitude-longitude pairs for each city and plotting on a direction layer map. The following map was plotted, showcasing directions between 4 cities in Mexico:

![WeatherPy_travel_map](https://user-images.githubusercontent.com/101564349/169702141-2731018e-f922-46e3-88d4-e48aa4dd4731.png)

Once this was done, we were able to also add a marker layer for each of those four cities. Our output was as follows:

![WeatherPy_travel_map_markers](https://user-images.githubusercontent.com/101564349/169702175-f854bd6c-c74e-461a-a3aa-48a7478a4cb5.png)


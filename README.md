# Coursera_Capstone: Final_Report
Final project for final course for IBM data science certificate 

##  **Introduction**
##### 1. _A description of the problem and a discussion of the background_ 

Seattle is a bustling, sprawling metropolitan city with engineers and developers and start up founders in hordes starting their morning with coffee. After all, Seattle is the birthplace of one of the most ubiquitous coffee shops in the US: Starbucks. Does it have room for one more coffee shop? With a population of over three-quarters of a million, I certainly think so, and so do mobs of caffeine-deprived workers and Starbucks alike. Imagine you are on the planning committee for the placement of the next Starbucks: Where should it be built? Where is the market saturated? Where is there a need for another coffee shop? 


## **Data**
##### 2. _A description of the data and how it will be used to solve the problem._

I will use Foursquare Venue Data to identify where the market is most saturated with coffee shops and where there might be room for another coffee shop. Areas with fewer than 10 venues will be excluded from the analysis (as on inspection, these are often areas that are largely parks or low population areas). I will also rank the venues in each neighborhood by most popular venues. For example, a neighborhood where the three most popular venues are a restaurant, yoga studio and book store very likely has room for another coffee shop. A neighborhood where the most popular venues are coffee shops, bistros and cafes may not. It is with these criteria that I will determine the best neighborhood to establish a new coffee shop.

## **Methodology**
![image](https://user-images.githubusercontent.com/33702789/125815839-82a03afc-a264-4bbf-aec7-79e635347b9d.png)

![image](https://user-images.githubusercontent.com/33702789/125815877-c833152d-8dc5-44d5-a9f0-75a3cced18ed.png)

![image](https://user-images.githubusercontent.com/33702789/125815908-04f422a8-af20-4abb-8272-0604e1f42d6e.png)

![image](https://user-images.githubusercontent.com/33702789/125815924-6cff0879-8c9b-4854-bc94-28a814e9ae8a.png)

I began by importing the necessary packages to load, process, analyze and visualize the data. Next, I downloaded the dataset (an open source excel spreadsheet), detailing the neighborhoods present in Seattle as well as their longitudes and latitudes. I used Geolocator to get exact GPS coordinates of the city of Seattle.  Next, using the folium package, I created a map of the city of Seattle and its surrounding suburbs. Each of the listed neighborhoods are indicated by blue dots. Following the creation of the map, I then used my Foursquare credentials to access Foursquare's database. Next, using Foursquare's database, I confirmed the longitudes and latitudes of each Seattle neighborhood then made a call to the database to get a list of venues for each neighborhood. I processed the output and created a table for each neighborhood indicating venue name, category it belonged to (Pizza place versus art gallery versus breakfast spot), as well as the longitude and latitude coordinates. Armed with this information, I explored the neighborhoods with this dataset. I made a very large table that had all the neighborhood names, GSP coordinates of neighborhoods,  venue names, GPS coordinates of the venue, and venue category. I also created a table that indicated the number of venues per neighborhood. Next, I assigned 0s and 1s (one hot encoding) to my table. Then I grouped rows by neighborhood and took the mean of the frequency of occurrence of each category.  I identified the top 5 common venues in each neighborhood then placed those values into a pandas dataframe and wrote a function to sort the venues in descending order. Then, I made a new dataframe and displayed the top 10 venues for each neighborhood. I dropped neighborhoods with less than 10 venues. And then finally, I ran K-means clustering. I ran several different trials and settled on 10 being the best number of clusters. Using folium again, I labeled each cluster in several clusters on a map of the city of Seattle. And lastly, examined each cluster. 

## **Results**
Using a combination of k- means clustering and researching the type of venues each neighborhood had, I was able to make recommendations on which neighborhood would be best suited for a new coffee shop. Research indicates: cluster 1, 2, 3, or 4 or the following neighborhoods: Beacon Hill, Central Seattle, Harrison/Denny, Seward Park or Windermere. None of these neighborhoods have coffee shops as one of their top 10 venues.

![image](https://user-images.githubusercontent.com/33702789/129116563-3b5be5b5-f256-4033-9350-26208d805c35.png)

## **Discussion**

 I explored the neighborhoods with this dataset and also created a table that indicated the number of venues per neighborhood. Then, I made a new dataframe and displayed the top 10 venues for each neighborhood. I dropped neighborhoods with less than 10 venues. And then finally, I ran K-means clustering. I ran several different trials (from 3 to 10 clusters) and settled on 5 being the best number of clusters because it indicated the best coverage.

## **Conclusion**
Imagine you are on the planning committee for the placement of the next Starbucks: Where should it be built? Where is the market saturated? Where is there a need for another coffee shop? I would recommend the following neighborhoods: Beacon Hill, Central Seattle, Harrison/Denny, Seward Park or Windermere. None of these neighborhoods have coffee shops as one of their top 10 venues; thus indicating that their markets are not saturated and could do with more coffee shops.




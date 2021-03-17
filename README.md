# NOAA-NDBC-Web-Scraper
A web scraper that reads NOAA's NDBC's realtime buoy data and graphs a scatterplot of ocean temperature, solar radiation, and depth measurements.

**Overview**

For this assignment, I made a web scraper that would be useful for noticing patterns in ocean temperature and solar radiation data from NOAA over the last 45 days. NOAA’s National Data Buoy Center’s data repository provides many free files for use. I was specifically interested in their realtime data folder, which is updated every weekday and contains measurements from the past 45 days. These measurements pertain to oceanographic, solar radiation, standard meteorological, and spectral wave data, all collected from individual buoys sitting in the ocean. I ended up creating a web scraper that would sort through all the realtime files available, combine the necessary data, and plot it on a graph.

I went this direction because I wanted to see if there was a noticeable correlation between depth, solar radiation, and ocean temperature. Ultimately, I found that there could be a significant relationship between the depth at which the measurements are taken and the measured ocean temperature, but there is not a relationship between ocean temperature and level of solar radiation.

**Approach**

My approach stemmed from my interest in ocean mapping and the work done by NOAA. I was sifting through their public data and decided to try and see if there was a correlation between solar radiation, depth, and the measured ocean temperature, through the data provided. To do this, I first scraped their repository for all “.ocean” and “.srad” file extensions. After creating a two lists of all available files with those extensions, I then went one by one into each file through their URLs to copy the data into an array. This allowed me to concatenate all the files I was interested in into two arrays, one for ocean data and the other for solar data. From there I converted the arrays to dataframes, created datetime columns, cleaned out unwanted data, and averaged the values by every hour. My final product was a single dataframe, a cleaned-up combination of the first two, which I used to create the scatterplot of temperature against depth. I also used the level of solar radiation to determine the size of the points.

**Data/Sources**

•	How to Webscrape: https://first-web-scraper.readthedocs.io/en/latest/#act-3-web-scraping
•	National Data Buoy Center’s Realtime Data: https://www.ndbc.noaa.gov/data/realtime2/

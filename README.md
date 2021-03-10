# GliderDATA
#My fledgling attempts to write R scripts to manipulate and view ocean glider data

#This is a practice script using glider data downloaded from OOI
#It uses Glider #583 downloaded as *.csv file
#Glider583.csv was first opened and assigned name Glider

library(tidyverse)
glider1 <- read_csv("G583.csv")

#Scatterplot created of the path of the glider
#scatterplot assigned x-axis as lon_uv and y-axis as lat_uv, and main title "Glider 583", x-axis title is "Longitude" and y-axis title as "Latitude"
# data are ploted as both points and lines (both, "b")

x <- glider1$lon_uv
y <- glider1$lat_uv
plot(x, y, "b", main = "Glider 583", xlab = "Longitude", ylab = "Latitude")

#Filter out all data except for the first 30,000 rows comprising a single cross-shelf transect;
#Assign this dataset new name, glider2 and plot the glider movement on a map.

glider2 <- filter(glider, distance <30000)
x <- glider2$lon_uv
y <- glider2$lat_uv
plot(x,y, "b",main = "Glider583", xlab = "Longitude", ylab = "Latitude")

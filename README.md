The Interactive Hottest St Louis Housing Map project uses data from https://econdata.s3-us-west-2.amazonaws.com/Reports/Hotness/RDC_Inventory_Hotness_Metrics_Zip_History.csv.
You can choose to download it like I did, or use:
```(Python)
url =  "https://econdata.s3-us-west-2.amazonaws.com/Reports/Hotness/RDC_Inventory_Hotness_Metrics_Zip_History.csv"
df = pd.read_csv(url)
```
To create the map, I wanted to use the lower granualarity of zipcodes. Unfortunately, trying to design a color scheme on that level was too difficult. And because the data
did not contain county information, I used the zipcodes module to discover both county and coordinates for the map. To use counties, I had to calculate an averge of hotness
ranks, sort by average, and then assign the colors in order.

Also, I could not install leafmap which would have been useful in creating the map legend.
Instead, I chose to use simple HTML to create the legend.

# Here is the assignment: critique the data visualization
## critique the data visualization
> The visualization I selected is the report from https://www.nacsmagazine.com/issues/march-2019/2019-us-convenience-store-count. This is a report for convenience stores in the US published by NACS magazine.  It  tries to depict the status quo and developing trend of convenience stores. 
What works well:
1) The overall narrative is designed in a logical way.  It uses sketchy icons to make abstract at the top. Then it uses three visualizations to illustrate channel count, growth trend and regional distribution. 2)The diversity of visualization tools. It employs table, bar chats, line plot to tell the story. 
What doesn't:
1)For channel count part, the table is too plain to make contrast and explain the trend(perceptibility);  2). for state distribution part, it use big icons to show the last 3 states, which is misleading(perceptibility); 3) for state distribution part, the colors are illogical and misleading(perceptibility);  4) for state distribution part, the colors are  ugly (aesthetics).
I will: 
1)change the visualization tools for part#3; 2)change the color for part#3; 3) move the notes aside.

## wireframe experience:
>please see this part by the link below:
[Clik here](/wireframe.jpg)

## My solution:
>Based on the feedback on ABtest, I decided to use data map to redesign the visualization. I used R to make it. Here is the code:

```{r setup, include=FALSE}
require(rgdal)
require(leaflet)
require(leaflet.extras)
require(dplyr)
require(readxl)
require(stringr)
```
```{r}
hk.house<-read_xlsx("/Users/tiangeyang/Desktop/Book2.xlsx")
str(hk.house)
``````{r}
pal<-colorNumeric(palette = "Blues",domain = hk.house$cvs)
#Map
leaflet() %>%
  addProviderTiles("CartoDB.Positron", group = "osm.H") %>%
#add a layer of points
  addCircleMarkers(data = hk.house, 
                   lng = ~longi, 
                   lat = ~lati, 
                   fillOpacity = .8,
                   radius = 10,
                   color = ~pal(cvs),
                   group='cvs') %>%
#add legend
  addLegend(position = "topleft", 
            pal = pal, 
            values = hk.house$cvs, 
            title = "cvs",
            group='cvs') %>%

  
#add layers control
  addLayersControl(
   overlayGroups = c("cvs"),
   options = layersControlOptions(collapsed = FALSE)
  )
```

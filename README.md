# Norwegian Immigration & Foreign Policy Contradictions
Lab 2 submission
<h3>Map can be accessed at: <a href="https://shennum.github.io/shennum-web/deportations/deportations-from-norway-2021.html" target="_blank">https://shennum.github.io/shennum-web/deportations/deportations-from-norway-2021.html</a></h3> 

![alt text](https://github.com/UBC-GEOS472-Spring2022/shennum-exploratory-lab2/blob/main/Screenshot_lab2.png "Screenshot of deportations map")


I am grateful for the feedback and input provided by Sarah Kelly and Emily Clark. They interacted with a draft of the map and provided very useful comments on how they interacted with it, what worked, and what could be improved. Emily pointed out how the popups for the lines were obstructing the view of the lines themselves and pointed me to a resource explaining how to offset the popups. Sarah offered a method to make it easier to access popups when hovering above them by creating a copy of the geojson layer that has greater radii but is not visible. I unfortunately was not able to implement this, and the points remain difficult to interact with. While looking at and interacting with their maps, I took notes on what worked well, questions I had, and what could potentially be improved (e.g., color choice, zoom). I also tried to point towards resources that could help answer specific questions they had regarding interactivity. One of the most helpful parts of a peer map critique is understanding how a user interacts with and interprets a map.  

In terms of coding resources I relied extensively on the documentation provided by Leaflet, Turf, and Mozilla, discussions on forums such as Stackexchange, and on Arslan (2018). Examples on how to perform certain tasks (such as working with dropdown menus) were studied and modified to the context of this maop.

This map is the result of years of frustration with the strict asylum and immigration policies of the Norwegian government. Norway has for years <a href="https://www.theguardian.com/global-development/2015/feb/26/norway-crackdown-asylum-seekers-afganistan-immigration" target="_blank">deported children and adults to Afghanistan</a> and to <a href="https://www.aljazeera.com/features/2015/3/23/yemeni-family-struggles-to-stay-in-norway" target="_blank">Yemen</a>. While critic-worthy in its own right, these policies, I believe, are even more problematic as Norway issues travel advisories to some of the very same countries it deports people to. Afghanistan, for instance, is deemed so unsafe for Norwegian citizens that the government advise all citizens to leave. In the same breath, the government deemed only parts of Afghanistan to be unsafe for asylum seekers, and in 2016, Norway accounted for 65 % of all forced returns from Europe to Afghanistan (<a href="https://www.noas.no/wp-content/uploads/2018/04/Strengestiklassen_170x240_web.pdf" target="_blank">NOAS, 2018</a>).

Thus, I had the idea to visualize these contradictions and unequal perceptions of safety across space – the formation of my goal (Roth, 2017). My intention is that the map effectively guides the reader to explore some of these relations themselves. By allowing the reader to choose what lines to appear on the map, they can explore the dataset country-by-country or display them all at once by reexpressing (Roth, 2017) the map. The decision to not display all lines at once when opening the map was a deliberate one, as it may overwhelm the user when seeing all the lines clustered together. The choice to not contrast red lines with green ones was also deliberate – in addition to avoiding presenting the user with ‘cartographic pepper’ (Muehlenhaus, 2014, p. 90), I did not want to imply that deporting non-asylum seekers was an opposite to deporting asylum seekers – it is still a disruptive event in someone’s life and is best visualized by a color other than green. I thus chose a split complementary color scheme (Muehlenhaus, 2014).

It is also absurdly difficult to apply for asylum in Norway – one can only do so if one is already within or at the country’s borders (i.e., one has to fly there, arrive by boat, or travel through a country that is not covered by the Dublin Regulation (Russia)). Hence, wherever the user double-clicks (the execution of an action, following Roth (2017)), only one point will appear. I hope that the text above the map and the text in the marker provides enough feedback to the user in order to perceive the changed system state (Roth, 2017).

The world and this subject matter are, of course, more complex than what this map allows for, but I tried to add some nuance by distinguishing between countries that have travel advisories to parts of and the entire country, and thus differentiated these by using an analogous color relationship. Following Muehlenhaus (2014, p. 89), this may be effective for placing these lower on the visual hierarchy and for displaying subtle differences. I hope all these elements allows the user to see patterns between foreign policy and immigration questions that I did not intend for, and with enough information to evaluate the outcome (Roth, 2017) of the map.

The map is not very easy to navigate. One cannot double-click to zoom (as I disabled this to allow for turfjs interaction), and the points that appear below polygons are not accessible when hovering above them. While the lines provide the same information, this is something that can be improved. 2021 may also not be a representative year for deportations, and other years could be included. I had to compromise (or did not do enough work on) the aesthetic design elements for the purposes of included a not insubstantial series of datasets. Conveying information was the primary goal, but I could have, for instance, used Mapbox to create a basemap better suited for conveying this information in a more visually appealing way. I also wish that the user could make use of more direct manipulation of the data (e.g., draw the lines as great circles given that many deportations happen by (sometimes chartered!) airplanes). 



Some notes on the data:

The map provides a snapshot in time (2021, only). I accessed a publicly available <a href="https://www.politiet.no/globalassets/04-aktuelt-tall-og-fakta/uttransporteringer/arsstatistikker-2012-21/uttransporteringer-2021.pdf" target="_blank">pdf file</a> from the Norwegian Police’s National Police Immigration Service (NPIS). I created excel spreadsheet containing the number of the different types of deportations (Dublin Convention, asylum seekers, and total number of people). I then downloaded a shapfile of national administrative boundaries from <a href="https://www.naturalearthdata.com/downloads/10m-cultural-vectors/" target="_blank">Natural Earth Data</a>, and uploaded these to ESRI ArcGIS Pro, where I found the centroids of each nation that Norway deported people to using ArcPy. The coordinates for these centroids were used to create lines between Norway and deportation destinations (some centroids, like the United States, were moved for aesthetic purposes). These shapefiles were uploaded in QGIS and converted to a geoJSON file that was updated with deportation attributes using geojson.io. 

Current travel advisories was accessed and translated from Norwegian to English from the websites of <a href="https://www.regjeringen.no/no/tema/utenrikssaker/reiseinformasjon/reiserad_land/id2589040/" target="_blank">The Ministry of Foreign Affairs</a>, and were added to geoJSON files as attributes using the above method. 

I wanted to include more points for Turfjs’s nearest point function but did not have the time to compile up-to-date information on all police stations in Norway. OSM does not provide an up-to-date overview of police stations as a few have been shut down as a result of recent government reforms. I thus had to resort to providing this information in the popup of the main location where asylum seekers can apply for asylum. 


<h3>References:</h3>
<ul>
 <li> Arslan, E. (2018). Learn JavaScript with p5.js: coding for visual learners. APress</li>      


  <li> Muehlenhaus, I. (2013). Web cartography: Map design for interactive and mobile devices. CRC Press. https://doi.org/10.1201/b16229</li>      

<li> Norsk organisasjon for asylsøkere. Strengest i Klassen? En Kartlegging av Afghanistan-Praksis i Vesteuropeiske Land. Oslo: NOAS, 2018. https://www.noas.no/wp-content/uploads/2018/04/Strengestiklassen_170x240_web.pdfs [Translated title: The Strictest in the Room? A Mapping of Afghanistan-Practice in Western European Countries.] </li>  

  <li> Roth, R. E. (2017). User Interface and User Experience (UI/UX) Design. The Geographic Information Science & Technology Body of Knowledge (2nd Quarter 2017 Edition), John P. Wilson (ed.). DOI: 10.22224/gistbok/2017.2.5. </li> 


  </ul>

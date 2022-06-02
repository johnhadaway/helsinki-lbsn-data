# LBSN data concerning Finland's Capital Region

### Introduction
The datasets here were proccessed and analysed as part of the University of Tampere's *Muuttuva käsitys lähiöstä tiivistyvässä kaupungissa (Changing perceptions of the suburbs in a condensing city)* project, which is part of the Ministry of the Environment's Suburb Programme 2020–2022 and funded by the Housing Finance and Development Centre of Finland (ARA).


### Methods
The datasets are derived from cumulative observations of venue activity, as of 01/01/2022, retrieved via the Foursquare Places API. The bounding box for these observations is defined by the following points (WGS84): SW (60.059, 24.485), NE (60.585, 25.226). 

The observations were elaborated using the Urban Activity Wheel methodology for categorisation described in "Optional and necessary activities: Operationalising Jan Gehl’s analysis of urban space with Foursquare data," written by Damiano Cerrone, Jesús López Baeza, and Panu Lehtovuori (Cerrone et al. 2020). Using the Urban Activity Wheel methodology, Foursquare venues were categorised into 10 groups, each mapping to an urban activity. The categories, together, are an approximation of "all activities capable of being performed in the city," combining Jan Gehl's categorisation with more recent research (Cerrone et al. 2020). The categories are as follows: *Taking care*, *Income*, *Nutrition*, *Mobility*, *Education*, *Civic*, *Leisure*, *Social*, *Consumption*, and *Personal care*. A description of each of these buckets can be found in the table below (Cerrone et al. 2020). 

&nbsp;
|Category | Description|
|---|---|
|Taking Care| To maintain or improve the condition of health (i.e., hospital, doctor, dentist, health centre)|
|Income| To receive a payment for a good or service (i.e., office spaces, or any other working activity)|
|Nutrition| To consume food with no other purpose (i.e., food that is ready to be eaten)||
|Mobility| Horizontal physical displacement by a means of transport (i.e., transportation nodes or stations, commuting, travelling)|
|Education| To learn by being taught (i.e., schools, kindergarten, university, people studying)|
|Civic| To pertain to citizenship (i.e., rallies, parades, public events and commemorations, volunteering, going to church, all activities that are part of the civic life of one community)|
|Leisure|To recreate by making use of the freedom from demands of work or duty (i.e., picnic, playing, reading, exhibition, sunbathing, walking the dog)|
|Social| To be in companionship with others (i.e., bar, nightclub, café, home party, dinner)|
|Consumption| To make use of a good or service (i.e., stores, boutiques, retail, supermarket)|
|Personal Care| To maintain or improve the condition of comfort, wellbeing, fitness (i.e., sports, spa, nail care, make up)|

&nbsp;

After cleaning the data, the venue-level observations (Foursquare visits, Foursquare users) were subsequently aggregated, by category, into useful scales of analysis: postal codes (for which we have Paavo postal code area statistics, produced by Statistics Finland) and H3 cells, at both resolution 9 (0.1053325 km<sup>2</sup> on average, and 4,842,432,842 unique indexes globally) and 8 (0.7373276 km<sup>2</sup> on average, and 691,776,122 unique indexes globally). At each of these scales, additional metrics were calculated: the number of visits per user, the number of visits per inhabitant, the percentage of visits that can be attributed to each activity category, the percentage of users that can be attributed to each activity category, the entropy of activities based on the distribution of these categories, and so on. See a psuedo-replication of the columns of the datasets in the table below. 

&nbsp;
|ID | Category_CHECKINS | Category_PERCENTAGE_TOTAL_VISITS | Category_PERCENTAGE_TOTAL_USERS | Category_PERCENTAGE_TOTAL_VENUES | Category_USERS | Category_VENUES | Category_VISITS | Category_VISITS_PER_INHABITANT | Category_VISITS_PER_USER | Category_VISITS_PER_VENUE | WHEEL_CATEGORIES_ENTROPY | OPNEC_ENTROPY |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
|Any ID columns. In the case of H3 grid cells, the index. In the case of Finnish postal codes, "postinumeroalue" and "nimi" | The total number of checkins in the geographical unit that can be attributed to the respective activity category | The percentage of visits in the geographical unit that can be attributed to the respective activity category | The percentage of users in the geographical unit that can be attributed to the respective activity category | The percentage of venues in the geographical unit that can be attributed to the respective activity category | The total number of users in the geographical unit that can be attributed to the respective activity category | The total number of venues in the geographical unit that can be attributed to the respective activity category | The total number of visits in the geographical unit that can be attributed to the respective activity category | The ratio between the total number of visits in the geographical unit that can be attributed to the respective activity category and the total number of inhabitants | The ratio between the total number of visits and users in the geographical unit that can be attributed to the respective activity category | The ratio between the total number of visits and venues in the geographical unit that can be attributed to the respective activity category | The entropy based on the distribution of activities according to the 10 categories above | The entropy based on the distribution of activities according to a higher-level optional-necessary categorisation of the 10 categories (Cerrone et al. 2020) |

*For the postal data, you can find a description, in English, of the additional columns taken from Statistics Finland [here](https://tilastokeskus.fi/static/media/uploads/tup/paavo/paavo2022_pitkakuvaus_en.pdf)*

&nbsp;

### Visualisations
<a href="https://datawrapper.dwcdn.net/IZ1gY/7/" target="_blank"><img width="1440" alt="COMPOSITION OF VISITS BY POSTAL CODE" src="https://user-images.githubusercontent.com/24534722/171662753-73a5f871-66d5-45a8-b1b2-7cd06e44399c.png"></a>
*The distribution of visits by Urban Activity Wheel category (Cerrone et al. 2020) in each postal code. Click [here](https://datawrapper.dwcdn.net/IZ1gY/7/) for the interactive visualisation, made with DataWrapper.*










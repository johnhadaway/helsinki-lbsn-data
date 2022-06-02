# LBSN data concerning Finland's Capital Region

### Introduction
The datasets here were proccessed and analysed as part of the University of Tampere's *Muuttuva käsitys lähiöstä tiivistyvässä kaupungissa (Changing perceptions of the suburbs in a condensing city)* project, which is part of the Ministry of the Environment's Suburb Programme 2020–2022 and funded by the Housing Finance and Development Centre of Finland (ARA). The datasets are derived from cumulative observations of venue activity, as of 01/01/2022, retrieved via the Foursquare Places API. The bounding box for these observations are as follows (WGS84): SW (60.059, 24.485), NE (60.585, 25.226). 


### Methods
The observations were elaborated using a methodology for categorisation described in "Optional and necessary activities: Operationalising Jan Gehl’s analysis of urban space with Foursquare data," written by Damiano Cerrone, Jesús López Baeza, and Panu Lehtovuori (Cerrone et al. 2020). Using its methodology, Foursquare venues were categorised into 10 buckets, each mapping to an urban activity. The buckets, together, are an approximation of "all activities capable of being performed in the city," combining Jan Gehl's categorisation with more recent research (Cerrone et al. 2020). The buckets are as follows: *Taking care*, *Income*, *Nutrition*, *Mobility*, *Education*, *Civic*, *Leisure*, *Social*, *Consumption*, and *Personal care*. A description of each of these buckets can be found in the table below (Cerrone et al. 2020). 

&nbsp;
|Bucket | Description|
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

After cleaning the data, the venue-level observations (Foursquare visits, Foursquare users) were subsequently aggregated, by bucket, into useful scales of analysis: postal codes (for which we have Paavo postal code area statistics, produced by Statistics Finland) and H3 cells, at both resolution 9 (0.1053325 km<sup>2</sup> on average, and 4,842,432,842 unique indexes globally) and 8 (0.7373276 km<sup>2</sup> on average, and 691,776,122 unique indexes globally). At each of these scales, additional metrics were calculated: the number of visits per user, the number of visits per inhabitant, the percentage of visits that can be attributed to each activity bucket, the percentage of users that can be attributed to each activity bucket, the diversity of activities based on these categorisations, and so on. A meta-level description of a row in each of the datasets can be found below. 

&nbsp;
|ID | Bucket_CHECKINS | Bucket_PERCENTAGE_TOTAL_VISITS | Bucket_PERCENTAGE_TOTAL_USERS | Bucket_PERCENTAGE_TOTAL_VENUES | Bucket_USERS | Bucket_VENUES | Bucket_VISITS | Bucket_VISITS_PER_INHABITANT | Bucket_VISITS_PER_USER | Bucket_VISITS_PER_VENUE | WHEEL_CATEGORIES_ENTROPY | OPNEC_ENTROPY |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
|Any ID columns. In the case of H3 grid cells, the index. In the case of Finnish postal codes, "postinumeroalue" and "nimi" | The total number of checkins in the geographical unit that can be attributed to the respective activity bucket | The percentage of visits in the geographical unit that can be attributed to the respective activity bucket | The percentage of users in the geographical unit that can be attributed to the respective activity bucket | The percentage of venues in the geographical unit that can be attributed to the respective activity bucket | The total number of users in the geographical unit that can be attributed to the respective activity bucket | The total number of venues in the geographical unit that can be attributed to the respective activity bucket | The total number of visits in the geographical unit that can be attributed to the respective activity bucket | The ratio between the total number of visits in the geographical unit that can be attributed to the respective activity bucket and the total number of inhabitants | The ratio between the total number of visits and users in the geographical unit that can be attributed to the respective activity bucket | The ratio between the total number of visits and venues in the geographical unit that can be attributed to the respective activity bucket | The entropy based on the distribution of activities according to the 10 buckets above, base 10 | The entropy based on the distribution of activities according to an optional-necessary classification, base 2 |









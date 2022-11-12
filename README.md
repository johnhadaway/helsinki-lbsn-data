<div align="center" style="margin-top: 5px; margin-bottom: 10px;">
  <h1>Greater Helsinki LBSN data</h1>
</div>

## `01_01_2022_FS_UrbanActivityWheel`

#### Introduction
The datasets in `01_01_2022_FS_UrbanActivityWheel` were proccessed and analysed as part of the University of Tampere's Muuttuva käsitys lähiöstä tiivistyvässä kaupungissa (Changing perceptions of the suburbs in a condensing city) project, which is part of the Ministry of the Environment's Suburb Programme 2020–2022 and funded by the Housing Finance and Development Centre of Finland (ARA).

#### Guide
The folder `01_01_2022_FS_UrbanActivityWheel` contains 4 sub-folders: H3_RES8, H3_RES9, POSTAL_CODES, and kepler.gl. The first three, each representing a different spatial resolution, contain cleaned, processed data, in both a GeoJSON and GeoPackage format. The fourth, to facilitate more exploratory use, contains saved map data and config as JSON files, which can be uploaded directly to (kepler.gl's web interface)[https://kepler.gl/]. 

#### Methods
The datasets are derived from cumulative observations of venue activity, as of 01/01/2022, retrieved via the Foursquare Places API. The bounding box for these observations is defined by the following points (WGS84): SW (60.059, 24.485), NE (60.585, 25.226). The observations were elaborated using the Urban Activity Wheel methodology for categorisation described in "Optional and necessary activities: Operationalising Jan Gehl’s analysis of urban space with Foursquare data," written by Damiano Cerrone, Jesús López Baeza, and Panu Lehtovuori (Cerrone et al. 2020). Using the Urban Activity Wheel methodology, Foursquare venues were categorised into 10 groups, each mapping to an urban activity. The categories, together, are an approximation of "all activities capable of being performed in the city," combining Jan Gehl's categorisation with more recent research (Cerrone et al. 2020). The categories are as follows: Taking care, Income, Nutrition, Mobility, Education, Civic, Leisure, Social, Consumption, and Personal care. A description of each of these categories (Cerrone et al. 2020): 

- Taking Care. To maintain or improve the condition of health (i.e., hospital, doctor, dentist, health centre)
- Income. To receive a payment for a good or service (i.e., office spaces, or any other working activity)
- Nutrition. To consume food with no other purpose (i.e., food that is ready to be eaten)
- Mobility. Horizontal physical displacement by a means of transport (i.e., transportation nodes or stations, commuting, travelling)
- Education. To learn by being taught (i.e., schools, kindergarten, university, people studying)
- Civic. To pertain to citizenship (i.e., rallies, parades, public events and commemorations, volunteering, going to church, all activities that are part of the civic life of one community)
- Leisure. To recreate by making use of the freedom from demands of work or duty (i.e., picnic, playing, reading, exhibition, sunbathing, walking the dog)
- Social. To be in companionship with others (i.e., bar, nightclub, café, home party, dinner)
- Consumption. To make use of a good or service (i.e., stores, boutiques, retail, supermarket)
- Personal Care. To maintain or improve the condition of comfort, wellbeing, fitness (i.e., sports, spa, nail care, make up)

After cleaning the data, the venue-level observations (Foursquare visits, Foursquare users) were subsequently aggregated, by category and in total, into useful scales of analysis: postal codes (for which we have Paavo postal code area statistics, produced by Statistics Finland) and H3 cells, at both resolution 9 (0.1053325 km<sup>2</sup> on average, and 4,842,432,842 unique indexes globally) and 8 (0.7373276 km<sup>2</sup> on average, and 691,776,122 unique indexes globally). At each of these scales, additional metrics were calculated: the number of visits per user, the number of visits per inhabitant, the percentage of visits that can be attributed to each activity category, the percentage of users that can be attributed to each activity category, the entropy of activities based on the distribution of these categories, and so on. 

#### Visualisations

<a href="https://datawrapper.dwcdn.net/XCiYB/3/" target="_blank"><img width="50%" alt="Relative Frequency of Visits by Cat" src="https://user-images.githubusercontent.com/24534722/173084140-928616b4-7662-4801-8234-90776ef538c5.png"></a><br>
The distribution of visits by Urban Activity Wheel category (Cerrone et al. 2020) in each postal code. Click [here](https://datawrapper.dwcdn.net/XCiYB/3/) for the interactive visualisation, made with Data Wrapper.</p>

<a href="https://datawrapper.dwcdn.net/rgRdH/2/" target="_blank"><img width="50%" alt="Relative Frequency of Users by Cat" src="https://user-images.githubusercontent.com/24534722/173084690-e7b0ccfb-4ad0-4428-8b4a-85cb67dc2ced.png"></a><br>
The distribution of users by Urban Activity Wheel category (Cerrone et al. 2020) in each postal code. Click [here]([https://datawrapper.dwcdn.net/yonUm/1/) for the interactive visualisation, made with Data Wrapper.

<img width="50%" alt="h3-9" src="https://user-images.githubusercontent.com/24534722/171683681-8ee6bd79-d625-485b-9a90-9418af7ab3d6.png"><br>
Saved map data and config for this data aggregated up into H3 cells (resolution 9). See 01_01_2022_FS_UrbanActivityWheel/kepler.gl for the JSON.

<img width="50%" alt="postal" src="https://user-images.githubusercontent.com/24534722/171683600-08e43e20-d162-4613-a986-b57c2bf7ebe5.png"><br>
Saved map data and config for this data aggregated up into postal codes. See 01_01_2022_FS_UrbanActivityWheel/kepler.gl for the JSON.








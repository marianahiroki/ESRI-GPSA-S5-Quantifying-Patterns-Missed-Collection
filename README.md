# ESRI-GPSA-S5-Quantifying-Patterns-Missed-Collection
Spatial analysis in ArcGIS detects patterns in 311 requests for municipal services, aiding resource prioritization. Demonstrates GIS usage for trend analysis.

## Section 5 ##
**Exercise 1: Quantifying Patterns: Missed Trash and Recycling Collection**
- The Department of Public Works in Washington, DC, collects residential trash and recycling from single-family homes and small apartment buildings.
- Residents report missed collections via 311.
- Analyst tasked with improving trash and recycling collection.
- Initial focus: missed collection locations in eight wards.
- Goal: Identify patterns of missed trash and recycling collection.
- Analysis question: ***Where are missed collections most frequent?***

1. Exercise Steps
   
   **Data Exploration and Preparation:**
   - The geodata provided are ward boundaries and missed collection locations for trash and recycling.
   - The dataset of missed trash and recycling collection locations in this map contains more than 6,000 points.
   - The points represent reports of missed trash and recycling collection in Washington, DC, over a three-month period.
   - Based on points alone, you cannot necessarily tell where there are higher numbers of missed collections.
     <img width="935" alt="Screenshot 2024-02-21 172042" src="https://github.com/marianahiroki/ESRI-GPSA-S5-Quantifying-Patterns-Missed-Collection/assets/110165879/0da19276-808d-423b-b8bf-1a25cf66d048">

  **Data Analysis and Modeling:**
   - Separating the points of missing collection per ward can help to easily quantify.
     <img width="935" alt="Screenshot 2024-02-21 172303" src="https://github.com/marianahiroki/ESRI-GPSA-S5-Quantifying-Patterns-Missed-Collection/assets/110165879/c55da040-579a-41bd-af49-34dab1d237aa">
     
   - The way the data was represented before, might show some inaccuracies, for example, multiple points (calls from the same apartment building) can be overlapped and considered as one missed collection.
   - Therefore, ***heat map*** symbology aids in analyzing large dense-point datasets by visually representing point distribution and density using a colour gradient from cool to hot.
     <img width="935" alt="Screenshot 2024-02-21 174958" src="https://github.com/marianahiroki/ESRI-GPSA-S5-Quantifying-Patterns-Missed-Collection/assets/110165879/ea7671b9-7086-4ced-82ff-63bad586f437">
     
   - The data remains unchanged; only the heat map visualization is modified. The visualization of the data can impact how data patterns are perceived, and ultimately the map narrative.
   - ***Density Analysis***: The difference in ward sizes could be a factor in the variation in spatial distribution. You can derive little information from the pattern of points because it is difficult to tell whether the points are more concentrated in one area.
     <img width="935" alt="Screenshot 2024-02-21 183129" src="https://github.com/marianahiroki/ESRI-GPSA-S5-Quantifying-Patterns-Missed-Collection/assets/110165879/2b3e4245-447b-4222-b7b9-2aff607d030f">

   - Both the ***heat map*** and ***density analysis*** utilize the kernel density algorithm to estimate spatial patterns of data density, exemplified in a map showing the distribution of missed trash collection reports across the city, with darker shades indicating higher densities, particularly evident in Wards 1 and 5.
   - Both heat map and density analysis offer valuable insights, yet the visualization can present multiple data narratives. Spatial statistics, like ***hot spot analysis***, quantify spatial patterns objectively, enhancing decision-making confidence by determining the statistical significance of point clusters.
     <img width="935" alt="Screenshot 2024-02-21 183428" src="https://github.com/marianahiroki/ESRI-GPSA-S5-Quantifying-Patterns-Missed-Collection/assets/110165879/e046dd00-70dc-4830-81f7-d75c8162b734">

  - The result of your analysis is a layer displaying ***hot spots*** in three shades of red and cold spots in three shades of blue. The varying shades correspond to three confidence intervals, indicating how confident you can be that these patterns are not the result of random chance.
  - Generally, the shared border of Ward 1, 2, and 5 have statistically significant high missed collection locations, as well as the centre of Ward 6. The northern area of Ward 3 has statistically significant low missed collection locations.
  - ***Hot spots*** may appear in areas with few or no missed collection locations due to neighbouring cells' influence, causing red cells to indicate density based on proximity rather than actual point presence.
    <img width="935" alt="Screenshot 2024-02-21 184819" src="https://github.com/marianahiroki/ESRI-GPSA-S5-Quantifying-Patterns-Missed-Collection/assets/110165879/a2c459bb-42a6-44f6-93d1-6ab429c481c3">

  - ***Outlier analysis*** was conducted to identify areas with statistically significant high and low values compared to neighbours, validating hot spot analysis and offering further spatial pattern insights.
  - The analysis tool uses the Anselin Local Moran's I statistic to identify statistically significant clusters of high and low values and to detect spatial outliers, or features with values that are significantly dissimilar from their neighbours.
    <img width="934" alt="Screenshot 2024-02-21 185230" src="https://github.com/marianahiroki/ESRI-GPSA-S5-Quantifying-Patterns-Missed-Collection/assets/110165879/b2ca09b8-26ed-4f07-9261-3aba71538066">

  - The dark blue cells indicate a low number of missed collections, surrounded primarily by cells with a high number of reports of missed collections.
    
  **Interpret results**
  - Different patterns observed; Ward 5 has the most missed collections, but other areas are also significant.
  - The shared border of Ward 1, 2, and 5 shows high missed collection locations, as does the centre of Ward 6.

  **Repeat or modify**
  - Utilize diverse techniques for detecting and analyzing patterns within missed collection data.
  - Identify influencing factors and incorporate new data for further spatial analysis.

  **Present results**
  - Inform resource prioritization for trash and recycling collection improvement.
  - Present identified locations with high missed collection rates to the Department of Public Works.

  **Make decisions**
  - Guide Department of Public Works in allocating resources effectively based on observed trends or further analysis.

# TableauGroupProject4610

## Group Members - Group 4
- [Tobias Allers](https://github.com/tka29934/MIST-4610-project-2)
- [Luke Mabry](https://github.com/Luke111033/TableauGroupProject4610/blob/main/README.md)
- [Alicia Lim](https://github.com/alicianlim/Project-2-4610)
- [Chris Sierra](https://github.com/Chrissi3rraa/4610-Project-2)
- [Pranav Rohit](https://github.com/pra984-star/Group-Project-2/blob/main/README.md)

## Data Set: Walkability Index
Link: https://catalog.data.gov/dataset/walkability-index8

Description: 
Our project utilizes data from the Smart Location Database (SLD), developed by the U.S. Environmental Protection Agency (EPA). The SLD provides a nationwide, standardized dataset at the Census block group level, offering an array of variables that describe characteristics of the built environment, transportation systems, and demographics. This dataset is particularly well-suited for exploring how urban form and accessibility influence transportation behavior.

Source: Smart Location Database (Version 2.0, EPA)
Level of Detail : Census Block Group Level (~220,000 block groups across the U.S.)
Dimensions: Approximately 220,000 rows (one per block group), 100+ columns (variables)

## 2 questions:
## Project 2 – Group Question 1
"How does the distribution of vehicle ownership differ between Eastern and Western U.S. regions in medium-to-high density neighborhoods, and what does this reveal about regional differences in urban planning and transportation access?"

This question examines how vehicle ownership patterns vary across regions even when population density is held constant. By comparing medium- and high-density block groups between the East and West, we can explore how infrastructure, public transit availability, and walkability contribute to car dependence or independence. While high-density areas typically reduce the need for cars, this may not hold equally across all regions due to planning and transit differences. The visualization helps highlight how geography influences transportation behavior beyond just density.

Why it matters: Regional gaps in vehicle access reflect broader differences in transit investment and planning priorities. Understanding these patterns supports better policymaking for equitable mobility and infrastructure development.

Data used:

D1B: Gross population density (people per acre)

Pct_AO0: Percent of households with zero vehicles

Statefp: Used to assign East or West region labels

Planned analysis: Boxplot of Pct_AO0 (percent of households with zero vehicles) by East vs. West regions in medium–high density areas to compare distributions.

Calculated fields:
Region_EastWest: Categorizes each row as “East” or “West” based on State FIPS codes.
IF [Statefp] IN (9, 23, 25, 33, 34, 36, 42, 44, 50, 1, 10, 11, 12, 13, 24, 37, 45, 47, 51, 54)
THEN "East"
ELSE "West"
END
Density Category: Groups population density into Low, Medium, and High.
IF [D1B] < 100 THEN "Low"
ELSEIF [D1B] < 300 THEN "Medium"
ELSE "High"
END

Expected visualization: Boxplot in Tableau.

![image](https://github.com/user-attachments/assets/e8bde08c-6994-4ba9-860e-4c6b118295a3)

### Analysis

The boxplot above displays the distribution of households without access to a vehicle across medium–high density neighborhoods in the Eastern and Western United States. Each point represents a Census block group, with the y-axis indicating the percent of households that report owning zero vehicles. The visualization highlights a notable regional disparity in vehicle access, even within similarly dense urban areas. From the graph, we can see that the East region has a significantly higher median percentage of households without a vehicle compared to the West. The interquartile range (IQR) is also higher for the East, suggesting greater variation in vehicle access across block groups in that region. In contrast, the West region exhibits a lower median and a tighter concentration of values, indicating more consistent and widespread vehicle ownership, even in denser areas. This contrast likely stems from differences in urban planning and public transportation infrastructure. Eastern cities, which are generally older and more compact, tend to have more walkable environments and established public transit networks, reducing the need for personal vehicle ownership. Western cities, which developed later and are typically more spread out, tend to prioritize road infrastructure and car travel, making vehicle ownership more necessary even in denser areas. This analysis reveals that density alone does not determine car dependence; instead, regional planning and transit investment play a big role. By being able to understand these patterns we are better able to develop equitable transportation policies, particularly in promoting mobility for non-drivers and reducing reliance on private cars in urban areas.

## Project 2 – Group Question 2
Do areas with more diverse land use tend to have lower vehicle miles traveled per capita?

This question looks at how the mix of land uses (e.g. jobs, services, housing) within an area affects travel behavior. Denser and more mixed-use areas are theorized to support shorter trips and more walking or transit usage.

Why it matters: Mixed-use areas where jobs, services, and housing, are can reduce the need for long vehicle trips, encouraging walking, biking, or transit use. Reducing VMT is also vital for cutting greenhouse gas emissions and combating climate change. This analysis can support sustainable planning by identifying how mixed-use development might reduce car dependence and emissions.

Data used:

D2B_E5MIX: Land use diversity index (employment-based)

D3BPO4: Vehicle miles traveled (VMT) per capita

Planned analysis: Scatter plot of D2B_E5MIX vs. D3BPO4 to identify trends or correlations.

Expected visualization: Scatter plot in Tableau.

calculations performed = to create the seperations between rural, suburban, and urban, an if function was used. Any city with a population over 100 thousand was deemed urban, between 100 thousand and 10 thousand suburban, and rural lying under 10 thousand.

![Final Tableau 2](https://github.com/user-attachments/assets/7d0bdf8e-fee6-4cdc-809c-0bae4e285a2a)


### Analysis

The graph above displays the relationship between employment mix (the variety of job type found within a set segmentation of a city) and the average vehicle distance traveled for individuals within that same city segment. The points of data are further characterized by population density, with color corresponding to the density of the segment. From this graph we can gather that suburban and rural areas have low employment mix and varying levels of vehicle distance traveled (it is important to note that there are more than one points of data for the rural data type, it is just covered in the same area of suburban). Suburban areas cluster around a somewhat lower mean of vehicle distance traveled than rural areas. Urban areas, however, show a gradual dispersion trending towards more distance traveled by vehicle the more varied the area’s employment mix becomes. Urban areas, being more dense and populous than suburban or rural areas, would make sense to have a higher variety in job type; There are more people with differing skills, with this variety seeing a decline in the progressively less dense areas. The increase in vehicle distance travelled in these urban areas could be explained through two potential reasons: either the increase in people simply increases the number of vehicles needed to get from point to point, or the variety of employment opportunities increases visitation from outside sources, inflating distance travelled past the numbers given solely from natives to the area. Either way, urban areas showcase a positive relationship between employment mix and distance traveled, in spite of the supposed availability of public transit.




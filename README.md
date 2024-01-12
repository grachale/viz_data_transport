# Network Analysis of Prague Integrated Transport (PID)

## Data
Utilizing open data from Prague Integrated Transport (PID), this project focuses on GTFS-formatted timetable data for consecutive transportation stops.

**Note:** For this assignment, a prepared dataset (`d.csv`) in CSV format has been provided, assembled from timetable data. Refer to the GTFS format documentation for details on file attributes.

## Task
Use markdown cells for clear documentation and commentary, as points will be awarded for clarity. Individuals are responsible for the assignment.

### ✨ Dataset
Load data from the file `d.csv`, containing records for every two consecutive stops of a transportation route. The structure is as follows:

| stop_from | stop_from_name | stop_to | stop_to_name | depart_from | arrive_to | route_type | is_night | mon | tue | wed | thu | fri | sat | sun |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| U699Z3P | Stadion Strahov | U981Z1P | Koleje Strahov | 7:24:00 | 7:25:00 | 3 | 0 | 1 | 1 | 1 | 1 | 1 | 0 | 0 |

The unique stop identifier is the stop name. Take note of identical stop names for different modes of transportation—consider them as the same station.

### ⚙️ Data Preprocessing
Adjust the `depart_from` and `arrive_to` attributes, which contain time values exceeding 24 hours (approximately 1.5% of records). Handle cases with times starting with values greater than 24 using modulo 24.

### ?️ Basic Network Analysis
Conduct a network analysis of PID stops, treating stops as nodes and consecutive stops as directed edges. The edge weight is the number of transportation modes passing through the route in one week.

1. Choose a network analysis package (e.g., NetworkX).
2. Create a suitable data representation for visualization.
3. Visualize the network (4 points).
4. Analyze the importance of stops using at least three centrality measures (6 points).
5. Visualize at least one centrality measure (2 points).

### ❓ Custom Questions 
Create three custom questions and answer them with appropriate visualizations based on dataset filtration.

### ? Additional Data
In the `stops.txt` file, geographical coordinates for each stop are provided. These data can enhance your analysis and assist with graph layout. Be cautious of stops with slightly different locations but similar names for different transportation modes. Propose and justify a solution for handling this (e.g., first location, average, centroid of a polygon, etc.).

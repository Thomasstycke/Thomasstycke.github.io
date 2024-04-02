---
layout: code
title: Code
slug: /code
---

<style>
  .code-block-container {
    text-align: center; /* Center the box */
    margin-left: -25%; /* Offset the box to the left */
    margin-right: -25%; /* Offset the box to the right */
  }

  .code-block {
    position: relative; /* Added to allow absolute positioning of the text */
  }

  .code-block figure {
    border: 2px solid black; /* Black border */
    border-radius: 5px;
    width: 100%; /* Make the box 150% wider */
    position: relative; /* Added to allow absolute positioning of line numbers */
  }

  .code-block pre {
    margin: 0;
    padding-left: 35px; /* Adjusted to reduce space between line numbers and code */
    position: relative; /* Added for absolute positioning of line numbers */
    white-space: pre-wrap; /* Allow long lines to break and wrap */
    text-align: left; /* Align code text to the left */
  }

  .code-block code {
    display: block;
    padding: 10px;
    border-radius: 5px;
    color: black; /* Text color */
    background-color: transparent; /* No background */
    font-size: 12px; /* Adjust font size to match line index size */
    line-height: 1.2; /* Adjust line height */
  }

  .code-line {
    position: absolute;
    left: 5px; /* Adjusted to reduce distance from the edge */
    width: 30px; /* Adjust width as needed */
    text-align: right;
    color: gray; /* Line number color */
    font-size: 12px; /* Adjust font size to match code size */
    padding-right: 5px; /* Adjusted to reduce distance from code */
    pointer-events: none; /* Ensures line numbers do not interfere with text selection */
  }

  .code-block figcaption {
    display: none; /* Hide the caption */
  }

  .code-description {
    text-align: left; /* Align left */
    margin-bottom: 10px; /* Add margin below the description */
  }

  .code-text {
    position: relative;
    text-align: left;
    margin-left: -25%; /* Offset to the left */
  }
  .code-heading {
    font-weight: bold; /* Makes text bold */
    position: relative; /* Allows for positioning relative to its normal position */
    left: -25%; /* Moves the element 25% to the left of its starting point */
    text-align: left; /* Aligns the text to the left */
  }
</style>

<p class="code-description">Here is our code for all our figures:</p>

<h2 class="code-heading">Figure 1:</h2>

<div class="code-block-container">
  <div class="code-block">
    <figure>
      <pre><code class="python">
<span class="code-line">1</span> import pandas as pd
<span class="code-line">2</span> import calplot
<span class="code-line">3</span> import matplotlib.pyplot as plt
<span class="code-line">4</span> from matplotlib.colors import LinearSegmentedColormap
<span class="code-line">5</span> 
<span class="code-line">6</span> # Load the dataset
<span class="code-line">7</span> path = '/Users/thomasstycke/Desktop/DTU/SocialData/Police_Department_Incident_Reports__Historical_2003_to_May_2018_20240130.csv'
<span class="code-line">8</span> data = pd.read_csv(path)
<span class="code-line">9</span> data = data[~data['Date'].str.contains('2018')]  # Exclude incidents from 2018
<span class="code-line">10</span> 
<span class="code-line">11</span> # Filter for 'ASSAULT' category incidents
<span class="code-line">12</span> assault_data = data[data["Category"] == 'ASSAULT']
<span class="code-line">13</span> assault_data['Date'] = pd.to_datetime(assault_data['Date'], format='%m/%d/%Y')  # Convert 'Date' to datetime format
<span class="code-line">14</span> 
<span class="code-line">15</span> # Create a series of events indexed by date
<span class="code-line">16</span> events = pd.Series(1, index=assault_data['Date'])
<span class="code-line">17</span> 
<span class="code-line">18</span> # Custom colormap from green to red
<span class="code-line">19</span> colors = [(0.2, 0.8, 0.2), (1.0, 1.0, 0.6), (0.8, 0.2, 0.2)]
<span class="code-line">20</span> cm = LinearSegmentedColormap.from_list('my_custom_green_red', colors, N=100)
<span class="code-line">21</span> 
<span class="code-line">22</span> # Plot the calendar heatmap
<span class="code-line">23</span> calplot.calplot(events, cmap=cm, colorbar=True, edgecolor='black', linewidth=1)
<span class="code-line">24</span> plt.show()
      </code></pre>
    </figure>
  </div>
</div>

<h2 class="code-heading">Figure 2:</h2>

<div class="code-block-container">
  <div class="code-block">
    <figure>
      <pre><code class="python">
<span class="code-line">1</span> import pandas as pd
<span class="code-line">2</span> import matplotlib.pyplot as plt
<span class="code-line">3</span> import numpy as np
<span class="code-line">4</span> import folium
<span class="code-line">5</span> import plotly.express as px
<span class="code-line">6</span> from urllib.request import urlopen
<span class="code-line">7</span> import json
<span class="code-line">8</span> import plotly.graph_objects as go
<span class="code-line">9</span> 
<span class="code-line">10</span> # Load the incident data
<span class="code-line">11</span> path = '/Users/thomasstycke/Desktop/DTU/SocialData/Police_Department_Incident_Reports__Historical_2003_to_May_2018_20240130.csv'
<span class="code-line">12</span> df = pd.read_csv(path)
<span class="code-line">13</span> 
<span class="code-line">14</span> # Remove data from the year 2018
<span class="code-line">15</span> df = df[df['Date'].str.contains('2018') == False]
<span class="code-line">16</span> df = assault_incidents = df[df['Category'] == 'ASSAULT']
<span class="code-line">17</span> 
<span class="code-line">18</span> january_first_incidents = df[df['Date'].str.startswith('01/01')]
<span class="code-line">19</span> 
<span class="code-line">20</span> # Dataframe of New Year's Eve fireworks in San Francisco: top 7 locations and SF Central Police Station
<span class="code-line">21</span> places_data = {
<span class="code-line">22</span>     'Name': ['Embarcadero', 'Twin Peaks', 'Treasure Island', 'KronOn', 'Golden Gate Park', 'SF Central Police Station'],
<span class="code-line">23</span>     'Latitude': [37.7955, 37.7544, 37.8200, 37.7749, 37.7694, 37.79874],
<span class="code-line">24</span>     'Longitude': [-122.3937, -122.4477, -122.3708, -122.4194, -122.4862, -122.40993]
<span class="code-line">25</span> }
<span class="code-line">26</span> 
<span class="code-line">27</span> places_df = pd.DataFrame(places_data)
<span class="code-line">28</span> 
<span class="code-line">29</span> # Load the GeoJSON for San Francisco Police Districts
<span class="code-line">30</span> with urlopen('https://raw.githubusercontent.com/suneman/socialdata2022/main/files/sfpd.geojson') as response:
<span class="code-line">31</span>     counties = json.load(response)
<span class="code-line">32</span> 
<span class="code-line">33</span> # Prepare your data frame for the choropleth map
<span class="code-line">34</span> january_first_incidents_by_district = january_first_incidents.groupby('PdDistrict').size().reset_index(name='Count')
<span class="code-line">35</span> 
<span class="code-line">36</span> # Total population data
<span class="code-line">37</span> populations = [74191,69961, 138002, 81913, 104067, 63359, 87890, 65166, 155029, 35902]
<span class="code-line">38</span> 
<span class="code-line">39</span> january_first_incidents_by_district['Total Population'] = populations
<span class="code-line">40</span> january_first_incidents_by_district['Incidents per 10.000 Residents'] = (january_first_incidents_by_district['Count'] / january_first_incidents_by_district['Total Population']) * 10000
<span class="code-line">41</span> 
<span class="code-line">42</span> # Create the choropleth mapbox
<span class="code-line">43</span> fig = px.choropleth_mapbox(january_first_incidents_by_district, 
<span class="code-line">44</span>                            geojson=counties, 
<span class="code-line">45</span>                            locations='PdDistrict', 
<span class="code-line">46</span>                            color='Incidents per 10.000 Residents',
<span class="code-line">47</span>                            color_continuous_scale=["green", "yellow", "red"],
<span class="code-line">48</span>                            range_color=(0,january_first_incidents_by_district['Incidents per 10.000 Residents'].max()),  
<span class="code-line">49</span>                            mapbox_style="carto-positron",
<span class="code-line">50</span>                            zoom=10.6, 
<span class="code-line">51</span>                            center={"lat": 37.77919, "lon": -122.41914},
<span class="code-line">52</span>                            opacity=0.5,
<span class="code-line">53</span>                            labels={'Incidents per 10.000 Residents':'Incidents per 10.000 Residents'},
<span class="code-line">54</span>                            hover_data={'Count': True})  
<span class="code-line">55</span> 
<span class="code-line">56</span> # Update the hover template and layout
<span class="code-line">57</span> fig.update_traces(hovertemplate='<b>%{location}</b> Total Count: %{customdata[0]} Incidents per 10.000 Residents: %{z}')
<span class="code-line">58</span> fig.update_layout(hoverlabel=dict(bgcolor="white", font_size=16, font_family="Rockwell"))
<span class="code-line">59</span> fig.update_layout(
<span class="code-line">60</span>     coloraxis_colorbar=dict(
<span class="code-line">61</span>         title_text='Incidents per 10,000 Residents',
<span class="code-line">62</span>         title_side='right'
<span class="code-line">63</span>     )
<span class="code-line">64</span> )
<span class="code-line">65</span> 
<span class="code-line">66</span> fig.add_trace(go.Scattermapbox(
<span class="code-line">67</span>     lat=january_first_incidents['Y'], 
<span class="code-line">68</span>     lon=january_first_incidents['X'],  
<span class="code-line">69</span>     mode='markers',  
<span class="code-line">70</span>     marker=go.scattermapbox.Marker(
<span class="code-line">71</span>         size=3, 
<span class="code-line">72</span>         color='grey', 
<span class="code-line">73</span>         opacity=0.85
<span class="code-line">74</span>     ),
<span class="code-line">75</span>     hoverinfo='text',
<span class="code-line">76</span>     showlegend=False  
<span class="code-line">77</span> ))
<span class="code-line">78</span> 
<span class="code-line">79</span> # Customize markers to be more visible and pin-like
<span class="code-line">80</span> for index, row in places_df.iterrows():
<span class="code-line">81</span>     if row['Name'] == 'SF Central Police Station':
<span class="code-line">82</span>         marker_color = 'blue'
<span class="code-line">83</span>     else:
<span class="code-line">84</span>         marker_color = 'red'
<span class="code-line">85</span>     
<span class="code-line">86</span>     fig.add_trace(go.Scattermapbox(
<span class="code-line">87</span>         lat=[row['Latitude']],
<span class="code-line">88</span>         lon=[row['Longitude']],
<span class="code-line">89</span>         mode='markers',  
<span class="code-line">90</span>         marker=go.scattermapbox.Marker(
<span class="code-line">91</span>             size=12, 
<span class="code-line">92</span>             color=marker_color,  
<span class="code-line">93</span>             opacity=0.85
<span class="code-line">94</span>         ),
<span class="code-line">95</span>         hoverinfo='text',
<span class="code-line">96</span>         hovertext=[row['Name']], 
<span class="code-line">97</span>         showlegend=False  
<span class="code-line">98</span>     ))
<span class="code-line">99</span> 
<span class="code-line">100</span> # Update the layout to show the legend
<span class="code-line">101</span> legend_entries = [
<span class="code-line">102</span>     {"name": "SF Central Police Station", "color": "blue", "size": 24},
<span class="code-line">103</span>     {"name": "Firework Locations", "color": "red", "size": 24},
<span class="code-line">104</span>     {"name": "Assault Incidents", "color": "grey", "size": 12}  
<span class="code-line">105</span> ]
<span class="code-line">106</span> 
<span class="code-line">107</span> annotations = []
<span class="code-line">108</span> vertical_position = 0.95
<span class="code-line">109</span> spacing = 0.05  
<span class="code-line">110</span> 
<span class="code-line">111</span> for i, entry in enumerate(legend_entries):
<span class="code-line">112</span>     # Adjust vertical position based on the index
<span class="code-line">113</span>     current_y = vertical_position - (i * spacing)
<span class="code-line">114</span>     # Adjust horizontal position based on the size of the marker
<span class="code-line">115</span>     if entry['size'] == 12:
<span class="code-line">116</span>         current_x = 0.0432
<span class="code-line">117</span>     else:
<span class="code-line">118</span>         current_x = 0.05
<span class="code-line">119</span> 
<span class="code-line">120</span>     # Annotation for the dot
<span class="code-line">121</span>     annotations.append(go.layout.Annotation(
<span class="code-line">122</span>         x=current_x, 
<span class="code-line">123</span>         y=current_y,
<span class="code-line">124</span>         xref="paper",
<span class="code-line">125</span>         yref="paper",
<span class="code-line">126</span>         text=f"<span style='font-size:{entry['size']}px; color:{entry['color']};'>●</span>",
<span class="code-line">127</span>         showarrow=False,
<span class="code-line">128</span>         font=dict(size=12),
<span class="code-line">129</span>         align="left",
<span class="code-line">130</span>         xanchor="right", 
<span class="code-line">131</span>         yanchor="middle" 
<span class="code-line">132</span>     ))
<span class="code-line">133</span> 
<span class="code-line">134</span>     # Annotation for the text
<span class="code-line">135</span>     annotations.append(go.layout.Annotation(
<span class="code-line">136</span>         x=0.06, 
<span class="code-line">137</span>         y=current_y,
<span class="code-line">138</span>         xref="paper",
<span class="code-line">139</span>         yref="paper",
<span class="code-line">140</span>         text=entry['name'],
<span class="code-line">141</span>         showarrow=False,
<span class="code-line">142</span>         font=dict(size=12),
<span class="code-line">143</span>         align="left",
<span class="code-line">144</span>         xanchor="left",  
<span class="code-line">145</span>         yanchor="middle"  
<span class="code-line">146</span>     ))
<span class="code-line">147</span> 
<span class="code-line">148</span> # Apply annotations to the figure layout
<span class="code-line">149</span> fig.update_layout(annotations=annotations)
<span class="code-line">150</span> fig.update_layout(margin={"r":0,"t":0,"l":0,"b":0})
<span class="code-line">151</span> fig.show()
      </code></pre>
    </figure>
  </div>
</div>

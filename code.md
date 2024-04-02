---
layout: code
title: Code
slug: /code
---

<div class="code-block" style="border: 2px solid black; border-radius: 5px; margin-bottom: 20px; position: relative;">
  <figure>
    <figcaption style="display: none;">Figure 1: Python Code</figcaption>
    <pre style="margin: 0; padding: 10px; overflow: auto; word-wrap: break-word; position: relative;">
<code class="python" style="display: block; border-radius: 5px; color: black; background-color: transparent; font-size: 12px; line-height: 1.2;">
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">1</span> import pandas as pd
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">2</span> import calplot
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">3</span> 
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">4</span> # Read the dataset
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">5</span> path = '/Users/thomasstycke/Desktop/DTU/SocialData/Police_Department_Incident_Reports__Historical_2003_to_May_2018_20240130.csv'
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">6</span> data = pd.read_csv(path)
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">7</span> data = data[~data['Date'].str.contains('2018')]
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">8</span> 
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">9</span> # Filter the data for the 'ASSAULT' category
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">10</span> assault_data = data[data["Category"] == 'ASSAULT']
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">11</span> 
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">12</span> # Convert the 'Date' column to datetime format
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">13</span> assault_data['Date'] = pd.to_datetime(assault_data['Date'], format='%m/%d/%Y')
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">14</span> 
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">15</span> all_days = pd.date_range(assault_data['Date'].min(), assault_data['Date'].max(), freq='D')
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">16</span> days = len(all_days)
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">17</span> events = pd.Series(1, index=assault_data['Date'])
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">18</span> 
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">19</span> import matplotlib.pyplot as plt
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">20</span> from matplotlib.colors import LinearSegmentedColormap
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">21</span> 
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">22</span> # Define the colors for the custom colormap (green to red)
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">23</span> colors = [(0.2, 0.8, 0.2),  # A cooler green
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">24</span>           (1.0, 1.0, 0.6),  # A cooler yellow
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">25</span>           (0.8, 0.2, 0.2)]  # A cooler red
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">26</span> 
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">27</span> n_bins = 100  
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">28</span> 
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">29</span> # Create the colormap
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">30</span> cmap_name = 'my_custom_green_red'
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">31</span> cm = LinearSegmentedColormap.from_list(cmap_name, colors, N=n_bins)
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">32</span> 
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">33</span> calplot.calplot(events, cmap=cm, colorbar=True, edgecolor='black', linewidth=1)
<span class="code-line" style="position: absolute; left: 5px; width: 30px; text-align: right; color: gray; font-size: 12px; padding-right: 5px; pointer-events: none;">34</span> plt.show()
    </code></pre>
  </figure>
</div>

---
layout: code
title: Code
slug: /code
---

<style>
  .code-block figure {
    border: 2px solid black; /* Black border */
    border-radius: 5px;
    margin-bottom: 20px;
    position: relative; /* Added to allow absolute positioning of line numbers */
  }

  .code-block figcaption {
    display: none; /* Hide the caption */
  }

  .code-block pre {
    margin: 0;
    padding-left: 35px; /* Adjusted to reduce space between line numbers and code */
    position: relative; /* Added for absolute positioning of line numbers */
  }

  .code-block code {
    display: block;
    padding: 10px;
    border-radius: 5px;
    color: black; /* Text color */
    background-color: transparent; /* No background */
    font-size: 12px; /* Adjust font size to match line index size */
    line-height: 1.2; /* Adjust line height */
    overflow-wrap: break-word; /* Break long lines */
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
</style>

<div class="code-block">
  <figure>
    <figcaption>Figure 1: Python Code</figcaption>
    <pre><code class="python">
<span class="code-line">1</span> import pandas as pd
<span class="code-line">2</span> import calplot
<span class="code-line">3</span> 
<span class="code-line">4</span> # Read the dataset
<span class="code-line">5</span> path = '/Users/thomasstycke/Desktop/DTU/SocialData/Police_Department_Incident_Reports__Historical_2003_to_May_2018_20240130.csv'
<span class="code-line">6</span> data = pd.read_csv(path)
<span class="code-line">7</span> data = data[~data['Date'].str.contains('2018')]
<span class="code-line">8</span> 
<span class="code-line">9</span> # Filter the data for the 'ASSAULT' category
<span class="code-line">10</span> assault_data = data[data["Category"] == 'ASSAULT']
<span class="code-line">11</span> 
<span class="code-line">12</span> # Convert the 'Date' column to datetime format
<span class="code-line">13</span> assault_data['Date'] = pd.to_datetime(assault_data['Date'], format='%m/%d/%Y')
<span class="code-line">14</span> 
<span class="code-line">15</span> all_days = pd.date_range(assault_data['Date'].min(), assault_data['Date'].max(), freq='D')
<span class="code-line">16</span> days = len(all_days)
<span class="code-line">17</span> events = pd.Series(1, index=assault_data['Date'])
<span class="code-line">18</span> 
<span class="code-line">19</span> import matplotlib.pyplot as plt
<span class="code-line">20</span> from matplotlib.colors import LinearSegmentedColormap
<span class="code-line">21</span> 
<span class="code-line">22</span> # Define the colors for the custom colormap (green to red)
<span class="code-line">23</span> colors = [(0.2, 0.8, 0.2),  # Green
<span class="code-line">24</span>           (1.0, 1.0, 0.6),  # Yellow
<span class="code-line">25</span>           (0.8, 0.2, 0.2)]  # Red
<span class="code-line">26</span> 
<span class="code-line">27</span> n_bins = 100  
<span class="code-line">28</span> 
<span class="code-line">29</span> # Create the colormap
<span class="code-line">30</span> cmap_name = 'my_custom_green_red'
<span class="code-line">31</span> cm = LinearSegmentedColormap.from_list(cmap_name, colors, N=n_bins)
<span class="code-line">32</span> 
<span class="code-line">33</span> calplot.calplot(events, cmap=cm, colorbar=True, edgecolor='black', linewidth=1)
<span class="code-line">34</span> plt.show()
    </code></pre>
  </figure>
</div>

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
  }

  .code-line {
    position: absolute;
    left: 5px; /* Adjusted to reduce distance from the edge */
    width: 30px; /* Adjust width as needed */
    text-align: right;
    color: black; /* Line number color */
    font-size: 12px; /* Adjust font size to match code size */
    padding-right: 5px; /* Adjusted to reduce distance from code */
    pointer-events: none; /* Ensures line numbers do not interfere with text selection */
  }
</style>

<div class="code-block">
  <figure>
    <figcaption>Figure 1: Python Code</figcaption>
    <pre><code class="python">
import pandas as pd
import calplot

# Read the dataset
path = '/Users/thomasstycke/Desktop/DTU/SocialData/Police_Department_Incident_Reports__Historical_2003_to_May_2018_20240130.csv'
data = pd.read_csv(path)
data = data[~data['Date'].str.contains('2018')]

# Filter the data for the 'ASSAULT' category
assault_data = data[data["Category"] == 'ASSAULT']

# Convert the 'Date' column to datetime format
assault_data['Date'] = pd.to_datetime(assault_data['Date'], format='%m/%d/%Y')

all_days = pd.date_range(assault_data['Date'].min(), assault_data['Date'].max(), freq='D')
days = len(all_days)
events = pd.Series(1, index=assault_data['Date'])

import matplotlib.pyplot as plt
from matplotlib.colors import LinearSegmentedColormap

# Define the colors for the custom colormap (green to red)
colors = [(0.2, 0.8, 0.2),  # A cooler green
          (1.0, 1.0, 0.6),  # A cooler yellow
          (0.8, 0.2, 0.2)]  # A cooler red

n_bins = 100  

# Create the colormap
cmap_name = 'my_custom_green_red'
cm = LinearSegmentedColormap.from_list(cmap_name, colors, N=n_bins)

calplot.calplot(events, cmap=cm, colorbar=True, edgecolor='black', linewidth=1)
plt.show()
    </code></pre>
  </figure>
</div>

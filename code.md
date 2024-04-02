---
layout: code
title: Code
slug: /code
---

<style>
  .code-block {
    text-align: center; /* Center the box */
    margin-left: -25%; /* Offset the box to the left */
    margin-right: -25%; /* Offset the box to the right */
  }

  .code-block figure {
    border: 2px solid black; /* Black border */
    border-radius: 5px;
    width: 100%; 
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
</style>

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

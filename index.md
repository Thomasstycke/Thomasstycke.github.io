---
layout: home
---

<h2>From Delicious to Dangerous: The Health Violation Crisis in NYC Eateries</h2>

<b style="text-align: justify; text-justify: inter-word;">
Thinking of dining out in New York City? Picking the perfect spot is more than just about taste—it’s about trust! We’re diving into a dataset describing NYC restaurant inspection results to uncover the connections between location, cuisine, brand, and health violations. Join us on a journey to discover the cleanest kitchens in the city, and make your next meal out a safe and satisfying one!
</b>

<p style="text-align: justify; text-justify: inter-word;">
Every restaurant in NYC has at least one visit from the Department of Health and Mental Hygiene (DOHMH) every year depending on the result of the previous inspection. The dataset describes a total of 28.752 inspection results through a 10-year time period from 2015 to 2024. If any violations are present, the inspection reports define them with specific violation codes.. Based on the extent and frequency of these violations, restaurants are categorized as either in a critical or non-critical state.
</p>

<p style="text-align: justify; text-justify: inter-word;">
Before diving into the historical data, the focus will be on the most recent inspection results. This approach provides a current and relevant guide to the sanitary conditions of NYC restaurants.
</p>

<b style="text-align: justify; text-justify: inter-word;">
So, what is the most common violation type in NYC?
</b>

<p style="text-align: justify; text-justify: inter-word;">
Guided by the latest inspection data, let's explore the violation codes in detail. Each code signifies a distinct type of health infraction, grouped into seven categories that range from minor concerns like improper food storage to more critical issues such as unsanitary cooking conditions or pest presence. Figure 1 provides a clear view of the most common violation types in recent New York City inspections. It reveals that Facility Sanitation is overwhelmingly the most common violation, followed by Pest Control. Conversely. While Chemical Safety is the least frequent, with only 20 recorded instances - which is still 20 too many.
</p>



<figure id="figure1" style="text-align: center; width: 130%; margin-left: -15%; margin-right: -15%;">
  <img src="/assets/img/calendar_plot.png" alt="Descriptive Alt Text" style="width: 100%;">
  <figcaption style="text-align: justify;"><b>Figure 1:</b> A calendar plot displaying the count of crimes categorized as assault from 2003 to 2017. The color bar illustrates the daily count of crimes, highlighting a noticeable trend of significantly higher counts on the first day of each year.</figcaption>
</figure>


<p style="text-align: justify; text-justify: inter-word;">
If you were planning to celebrate New Year's Eve in San Francisco, it's crucial to know which areas might be safer than others. To provide insights, we investigated the top 5 locations where people gather to watch fireworks and mapped them out <a href="#ref1">[1]</a>. The goal was to determine if these popular spots correlate with higher rates of assault incidents, as large crowds often attract incidents.
</p>

<p style="text-align: justify; text-justify: inter-word;">
 <a href="#figure2">Figure 2</a> shows a map of San Francisco and its ten police districts where each district is described with its count of recorded assault crimes per 10,000 residents. The information about residents in each district was gathered from <a href="#ref2">[2]</a>.
</p>

<p style="text-align: justify; text-justify: inter-word;">
Tenderloin emerges as the district with the highest recorded assaults per 10,000 residents, which aligns with its reputation as a high-crime neighborhood <a href="#ref3">[3]</a>. A closer look reveals that Tenderloin had a total of 88 recorded assault incidents, surpassing other districts such as Richmond, Taraval, Park, Ingleside, and Bayview.
</p>

<p style="text-align: justify; text-justify: inter-word;">
Southern district follows closely with the second-highest number of assault incidents per 10,000 residents. Interestingly, although it hosts two popular fireworks viewing spots, our analysis indicates that the incidents are not necessarily concentrated near these locations. Thus, the presence of fireworks viewing spots might not significantly influence assault crime rates in this district.<br><br>
Treasure Island's inclusion in the Southern district may give the impression of high crime rates on January 1st. However, this perception is misleading, as only one assault was recorded through 15 years in Treasure Island, making it seem like a quite safe place to be.
</p>

<p style="text-align: justify; text-justify: inter-word;">
Central district ranks third in terms of assault incidents per 10,000 residents. Notably, the analysis reveals a concerning trend: both Southern and Central districts have a considerable number of recorded incidents near the "border" with Tenderloin. This finding strongly suggests that these areas, especially on New Year's Eve, warrant caution and avoidance.
</p>

<p style="text-align: justify; text-justify: inter-word;">
In conclusion, while the choice of fireworks viewing spots may not significantly impact safety, it remains wise to avoid places that are close to known high-crime neighborhoods, especially Tenderloin.
</p>

<figure id="figure2"> 
  {% include map.html %}
  <figcaption style="text-align: justify;">
    <b>Figure 2:</b>  Choropleth map illustrating the distribution of assault incidents recorded in 2003-2017 across San Francisco's ten police districts. The color scale represents the number of assault incidents recorded per 10,000 residents in each district, offering a normalized perspective accounting for district size variations. The blue circle marker denotes the SF Central Police Station, while red circle markers indicate prime locations for observing New Year's Eve fireworks. Grey circle markers pinpoint specific locations of recorded assault incidents.
  </figcaption>
</figure>

<p style="text-align: justify; text-justify: inter-word;">
To get a better insight into what time of day the incidents happen, we've plotted all the hours from the 31st of December and the 1st of January and the district in which the crime was recorded.  <a href="#figure3">Figure 3</a> shows a detailed temporal analysis of assault incidents reported in various districts on the 31st of December and the 1st of January.
</p>

<figure id="figure3">
  {% include cleaned_bokeh_plot.html %}
  <figcaption style="text-align: justify;">
  <b>Figure 3:</b> A histogram showing the total counts of assault crimes recorded in each district in 2003-2017. The x-axis goes from 00:00 December 31st to 23:00 January 1st, with hours rounded down. The legend with different districts is interactive making it possible to choose which district to display. 
  </figcaption>
</figure>

<p style="text-align: justify; text-justify: inter-word;">
Notably, there is a marked increase in assault reports precisely at midnight (00:00 1st of January) spanning across multiple districts. This surge aligns with the anticipated pattern for New Year’s Eve, as it's a time commonly associated with large public gatherings and festivities. Unfortunately, such occasions can also escalate into conflicts and instances of criminal behavior.
</p>

<p style="text-align: justify; text-justify: inter-word;">
All districts show a peak in reports at noon (12:00), which may be somewhat unexpected for assault cases and could be less about the incidence of assaults and more related to administrative activities within the police force. Since this is a time when shift changes often happen and lunch breaks are common, incidents that occurred earlier might be logged at noon, even though they weren't reported immediately. This suggests it's more of a procedural issue than a genuine increase in assault frequency.
</p>

<p style="text-align: justify; text-justify: inter-word;">
Since the plot displays all 24 hours from December 31st it reveals a strong contrast between midnight on December 31st and midnight on January 1st. Similarly, a notable difference can be observed when comparing the late hours of January 1st with those of December 31st. This observation highlights the uniqueness of New Year’s Eve's activities and their impact on public safety.
</p>

<p style="text-align: justify; text-justify: inter-word;">
In conclusion, as San Francisco celebrates New Year's Eve with fireworks lighting up the night sky, an underlying trend of increasing assault incidents around midnight comes to light. However, an analysis of assaults near popular fireworks locations does not reveal a consistent trend, suggesting these gatherings themselves do not significantly elevate the risk. On the other hand, spending New Year's Eve in or near the Tenderloin district does present a higher risk, as this area is known for its elevated assault incidents. 
</p>

<p style="text-align: justify; text-justify: inter-word;">
Given these insights, how will you choose where to celebrate? Selecting your location could be the key to ensuring the safety and enjoyment of your New Year's Eve experience in the city. Stay safe and make informed choices to welcome the new year with peace and joy.
</p>

<ol>
    <li id="ref1"><a href="https://www.hindustantimes.com/world-news/new-years-eve-fireworks-in-san-francisco-top-7-spots-to-ring-in-2024-celebrations-101704006372655-amp.html">New Year's Eve fireworks in San Francisco: Top 7 spots to ring in 2024</a>. Hindustan Times.</li>
    <li id="ref2"><a href="https://www.prisonpolicy.org/origin/ca/2020/sanfrancisco_police.html">SFPD Disrict Residents</a>. Prison Policy Initiative.</li>
    <li id="ref3"><a href="https://en.wikipedia.org/wiki/Tenderloin,_San_Francisco">Tenderloin, San Francisco</a>. Wikipedia.</li>
</ol>

<head>
  <title>Contributions</title>
  <style>
    table {
      width: 80%;
      border-collapse: collapse;
      margin-left: auto;
      margin-right: auto;
    }
    th, td {
      border: 2px solid #666666; /* Updated border color to darker gray */
      text-align: center;
      padding: 8px;
      color: #666666; /* Updated text color to darker gray */
    }
  </style>
</head>
<body>

<h2 style="color: #666666;">Contributions</h2> <!-- Optional: Updated heading color to darker gray -->

<table>
    <tr>
        <th>Contributions</th>
        <th>Thomas</th>
        <th>Anna-Sofie</th>
    </tr>
    <tr>
        <td>Figures</td>
        <td>50%</td>
        <td>50%</td>
    </tr>
    <tr>
        <td>Site</td>
        <td>50%</td>
        <td>50%</td>
    </tr>
    <tr>
        <td>Text</td>
        <td>50%</td>
        <td>50%</td>
    </tr>
</table>

</body>

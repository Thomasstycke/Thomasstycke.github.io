---
layout: home
---

<h2>New Year, Same Story: San Fransisco's Assaults Renewed</h2>

<p style="text-align: justify; text-justify: inter-word;">
A comprehensive dataset spanning from January 2003 to December 2017, detailing incidents recorded by the San Francisco Police Department, uncovers a troubling trend. Among the various crimes recorded, one stands out: assaults.
</p>

<p style="text-align: justify; text-justify: inter-word;">
Throughout this 15-year period, the average daily count of reported assaults hovered between 28 and 32. However, an alarming deviation is consistently observed on the first day of each new year. On January 1st each year, the number of reported assaults incidents spike remarkably, with reported cases ranging from 47 and 80, averaging out to 56 reported assaults - which is significantly higher than the daily average! This trend becomes evident when reviewing the calendar plot illustrating recorded assault crimes from 2003 to 2017 (See <a href="#figure1">Figure 1</a>). On some days throughout the different years, there is also a high incident count, but no clear pattern emerges as it does with January 1st. In some years, December 31st also exhibits a high count of incidents, which might be attributed to whether officers 'round up' the documentation clock-time to 00:00, or perhaps due to some officers having a shift change around this hour. This rounding up or shift change could influence whether an incident is recorded as belonging to January 1st or December 31st, providing a possible explanation for the fluctuation in incident counts on these dates.
</p>

<figure id="figure1" style="text-align: center; width: 130%; margin-left: -15%; margin-right: -15%;">
  <img src="/assets/img/calendar_plot.png" alt="Descriptive Alt Text" style="width: 100%;">
  <figcaption style="text-align: justify;"><b>Figure 1:</b> A calendar plot displaying the count of crimes categorized as assault from 2003 to 2017. The color bar illustrates the daily count of crimes, highlighting a noticeable trend of significantly higher counts on the first day of each year.</figcaption>
</figure>


<p style="text-align: justify; text-justify: inter-word;">
If you were planning to celebrate New Year's Eve in San Francisco, it's crucial to know which areas might be safer than others. To provide insights, we investigated the top 7 locations where people gather to watch fireworks and mapped them out <a href="#ref1">[1]</a>. Our goal was to determine if these popular spots correlate with higher rates of assault incidents, as large crowds often attract incidents.
</p>

<p style="text-align: justify; text-justify: inter-word;">
Figure 2 shows a map of San Fransisco and its' ten police districts where each district is described with its count of recorded assault crimes per 10,000 residents. The information about residents in each district was gathered from <a href="#ref2">[2]</a>.
</p>

<p style="text-align: justify; text-justify: inter-word;">
Tenderloin emerges as the district with the highest recorded assaults per 10,000 residents, which aligns with its reputation as a high-crime neighborhood <a href="#ref3">[3]</a>. A closer look reveals that Tenderloin had a total of 88 recorded assault incidents, surpassing other districts such as Richmond, Taraval, Park, Ingleside, and Bayview.
</p>

<p style="text-align: justify; text-justify: inter-word;">
Southern district follows closely with the second-highest number of assault incidents per 10,000 residents. Interestingly, although it hosts two popular fireworks viewing spots, our analysis indicates that the incidents are not necessarily concentrated near these locations. Thus, the presence of fireworks viewing spots might not significantly influence assault crime rates in this district.
</p>

<p style="text-align: justify; text-justify: inter-word;">
Central district ranks third in terms of assault incidents per 10,000 residents. Notably, our analysis reveals a concerning trend: both Southern and Central districts have a considerable number of recorded incidents near the "border" with Tenderloin. This finding strongly suggests that these areas, especially on New Year's Eve, warrant caution and avoidance.
</p>

<p style="text-align: justify; text-justify: inter-word;">
In conclusion, understanding the distribution of assault incidents relative to popular New Year's Eve fireworks viewing spots can inform safer celebration plans, highlighting areas to avoid, particularly those neighboring high-crime districts like Tenderloin.
</p>

<figure>
  {% include map.html %}
  <figcaption>
    <figcaption style="text-align: justify;">
    <b>Figure 2:</b>  Choropleth map illustrating the distribution of assault incidents recorded in 2003-2017 across San Francisco's ten police districts. The color scale represents the number of assault incidents recorded per 10,000 residents in each district, offering a normalized perspective accounting for district size variations. The blue circle marker denotes the SF Central Police Station, while red circle markers indicate prime locations for observing New Year's Eve fireworks. Grey circle markers pinpoint specific locations of recorded assault incidents.
  </figcaption>
</figure>

<p style="text-align: justify; text-justify: inter-word;">
To get a better insight into what time of day the incidents happen, we've plotted all the hours from the 31st of December and the 1st of January and the district in whcih the crime was recorded. Figure 3 shows a detailed temporal analysis of assault incidents reported in various districts on the 31st of December and the 1st of January.
</p>

<figure>
  {% include cleaned_bokeh_plot.html %}
  <figcaption style="text-align: justify;">
  <b>Figure 3:</b> This is the captions:
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

<ol>
    <li id="ref1"><a href="https://www.hindustantimes.com/world-news/new-years-eve-fireworks-in-san-francisco-top-7-spots-to-ring-in-2024-celebrations-101704006372655-amp.html">New Year's Eve fireworks in San Francisco: Top 7 spots to ring in 2024</a>. Hindustan Times.</li>
    <li id="ref2"><a href="https://www.prisonpolicy.org/origin/ca/2020/sanfrancisco_police.html">SFPD Disrict Residents</a>. Prison Policy Initiative.</li>
    <li id="ref3"><a href="https://en.wikipedia.org/wiki/Tenderloin,_San_Francisco">Tenderloin, San Francisco</a>. Wikipedia.</li>
</ol>


---
layout: home
---

<h2>From Delicious to Dangerous: The Health Violation Crisis in NYC Eateries</h2>

<b style="text-align: justify; text-justify: inter-word;">
Thinking of dining out in New York City? Picking the perfect spot is more than just about taste—it’s about trust! We’re diving into a dataset describing NYC restaurant inspection results to uncover the connections between location, cuisine, brand, and health violations. Join us on a journey to discover the cleanest kitchens in the city, and make your next meal out a safe and satisfying one!
</b>

<p style="text-align: justify; text-justify: inter-word;">
Every restaurant in NYC has at least one visit from the Department of Health and Mental Hygiene (DOHMH) every year depending on the result of the previous inspection. The dataset describes a total of 28.752 (224115) inspection results through a 10-year time period from 2015 to 2024. If any violations are present, the inspection reports define them with specific violation codes. Based on the extent and frequency of these violations, restaurants are categorized as either in a critical or non-critical state.
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
So, the violations that most possible to be occurring at a restaurant is regarding sanitation and pest...
</p>

<b style="text-align: justify; text-justify: inter-word;">
Craving thai, burger or Chinese food? Maybe have the cuisine in mind when deciding.
</b>

<p style="text-align: justify; text-justify: inter-word;">
Considering a specific cuisine — Burger, Pizza or a Sandwich? The type of cuisine may influence the likelihood of certain violations due to different cooking methods and ingredients. Figure 2 highlights a consistent distribution of violations across various cuisines, with Facility Sanitation consistently ranking highest. Notably, Chemical Safety violations are absent in eateries serving sandwiches or hot dogs.
</p>

<p style="text-align: justify; text-justify: inter-word;">
Figure 2 reveals a trend of the distribution of the violation codes having the same hiarachy. This being, that all the violation codes are distributed somewhat the same; having the facility sanitation code being the most common, the Pest control the second and so on in all kitchens. Though, the figure tells us, that the Chemical Safety violation haven’t been reported in restaurants serving Sandwiches or Hotdogs.
</p>

<figure id="figure2"> 
  {% include map.html %}
  <figcaption style="text-align: justify;">
    <b>Figure 2:</b>  Choropleth map illustrating the distribution of assault incidents recorded in 2003-2017 across San Francisco's ten police districts. The color scale represents the number of assault incidents recorded per 10,000 residents in each district, offering a normalized perspective accounting for district size variations. The blue circle marker denotes the SF Central Police Station, while red circle markers indicate prime locations for observing New Year's Eve fireworks. Grey circle markers pinpoint specific locations of recorded assault incidents.
  </figcaption>
</figure>

<b style="text-align: justify; text-justify: inter-word;">
Hygiene Status
</b>

<p style="text-align: justify; text-justify: inter-word;">
The presence of a violation code doesn’t necessarily equate to a critical hygiene status. Therefore, lets look into how many inspections actually let to the restaurant getting flagged as critical hygiene condition.
</p>

<figure id="figure3">
  {% include violation_group_distribution.html %}
  <figcaption style="text-align: justify;">
  <b>Figure 3:</b> A histogram showing the total counts of assault crimes recorded in each district in 2003-2017. The x-axis goes from 00:00 December 31st to 23:00 January 1st, with hours rounded down. The legend with different districts is interactive making it possible to choose which district to display. 
  </figcaption>
</figure>

<p style="text-align: justify; text-justify: inter-word;">
Figure 3 illustrates that the probability of a restaurant being flagged as critically unhygienic is approximately 50/50 across all cuisines, indicating that the likelihood of encountering severe health risks does not depend on the type of cuisine served. This trend shows an equal distribution of critical and non-critical health ratings, reinforcing that no specific cuisine is more likely to have severe health violations.
</p>

<b style="text-align: justify; text-justify: inter-word;">
DBA
</b>

<p style="text-align: justify; text-justify: inter-word;">
Although there is no distinct pattern indicating higher risks associated with specific cuisines, Figure 4 serves as a practical guide. It plots the top 20 restaurants that consistently receive "Not Critical" flag from the inspections result. Notably, a restaurant can appear multiple times if it is part of a chain, like the various McDonald's locations in NYC. The "Not Critical Proportion" metric used in this chart shows the frequency with which these restaurants pass inspections without critical issues, suggesting they maintain higher standards of cleanliness. If you have a preference for a particular type of cuisine, you can use this data to find establishments with the best health inspection records within that category.
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

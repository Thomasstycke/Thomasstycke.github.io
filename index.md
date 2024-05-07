---
layout: home
---

<h2>From Delicious to Dangerous: The Health Violation Crisis in NYC Restaurants</h2>

<b style="text-align: justify; text-justify: inter-word;">
Thinking of dining out in New York City? Picking the perfect spot is more than just about taste—it’s about trust! We’re diving into a dataset describing NYC restaurant inspection results to uncover the connections between location, cuisine, brand, and health violations. Join us on a journey to discover the cleanest kitchens in the city, and make your next meal out a safe and satisfying one!
</b>


<p style="text-align: justify; text-justify: inter-word;">
Every restaurant in NYC has atleast one visit from the Department of Health and Mental Hygiene (DOHMH) every year depending on the result of the previous inspection. The dataset describes a total of 224.155 inspection results through a 10-year time period from 2015 to 2024. If any violations are present, the inspection reports define them with specific violation codes.. Based on the extent and frequency of these violations, restaurants are given a score and categorized as either in a critical or non-critical state.
</p>

<p style="text-align: justify; text-justify: inter-word;">
Before diving into the historical data, the focus will be on the most recent inspection results. This approach provides a current and relevant guide to the sanitary conditions of NYC restaurants.
</p>

<b style="text-align: justify; text-justify: inter-word;">
So, what is the most common violation type in NYC?
</b>

<p style="text-align: justify; text-justify: inter-word;">
Guided by the latest inspection data, let's begin an in-depth exploration of violation codes. Each code represents a unique type of health violation, carefully categorized into seven distinct groups, as outlined in Table 1. These categories cover a spectrum of concerns, spanning from minor issues like improper facility maintenance to more serious matters such as unsanitary cooking conditions or bad staff hygiene.
</p>

<figure id="figure1" style="max-width: 100%; display: block; margin: 0 auto;">
    {% include violation_groups.html %}
    <figcaption style="text-align: justify;">
        <b>Table 1:</b> Provides definitions of violation groups, along with their counts from the latest inspections and an example of a violation description within each group.
    </figcaption>
</figure>

<br>

<p style="text-align: justify; text-justify: inter-word;">
The counts and frequencies of different violation groups vary. Concurrently, Figure 1 offers insight into the distribution of violation types in recent inspections in NYC. Notably, Facility Sanitation emerges as the most prevalent violation, followed closely by Pest Control. In contrast, Chemical Safety records the lowest frequency, with only 20 instances recorded- which is still 20 too many.
</p>


<figure id="figure2" style="max-width: 100%; display: block; margin: 0 auto;">
    {% include monthly_violation_counts.html %}
    <figcaption style="text-align: justify;">
        <b>Figure 1:</b> Line chart illustrating the inspection count for each defined violation group, depending on the selected time period. Below the chart, an interactive range slider graph allows users to select specific data ranges. Additionally, a legend positioned to the right enables users to choose which violation group to display on the chart.
    </figcaption>
</figure>

<br>

<p style="text-align: justify; text-justify: inter-word;">
Additionally, the plot demonstrates a significant increase in the counts of most violation groups since mid-2022. This surge could be attributed to increased investment in inspections or stricter documentation procedures within this dataset.
However, it's important to note that while Facility Sanitation appears as the most frequent violation, its frequency doesn't necessarily correlate with its level of criticality. To better understand the urgency of each violation group, critical conditions have been investigated and plotted in Figure 2.
</p>

<figure id="figure3" style="max-width: 100%; display: block; margin: 0 auto;">
    {% include total_inspections_criticality.html %}
    <figcaption style="text-align: justify;">
        <b>Figure 2:</b> Stacked Bar Chart displaying the count of inspections dependent of the Violation group. The stacked bars indicated the percentage of the count given the flag critical and not critical.
    </figcaption>
</figure>

<br>

<p style="text-align: justify; text-justify: inter-word;">
Figure 2 highlights the critical nature of certain violation groups, notably Temperature Control, Staff Hygiene, and Chemical Safety.  Notably, despite its high frequency, Facility Sanitation does not emerge as the most critical violation group, suggesting that it may not be as critical to address compared to other violations.It's noteworthy that while Temperature Control ranks as the third most frequent violation, Figure 2 reveals it to be among the most critical. This contrast suggests a nuanced understanding of violation severity beyond mere frequency.
</p>

<b style="text-align: justify; text-justify: inter-word;">
Craving thai, burger or Chinese food? Maybe have the cuisine in mind when deciding.
</b>


<p style="text-align: justify; text-justify: inter-word;">
The type of cuisine may influence the likelihood of certain violations due to different cooking methods and ingredients. Despite these differences, we observed a consistent pattern across all cuisines: approximately 50% of inspections result in a Critical flag, while the remaining 50% receive a Not Critical flag.
Figure 3 provides insights into the distribution of violations across various cuisines, uncovering some differences. While there's a consistent flag distribution, variations in violation types across cuisines suggest that specific culinary practices or ingredients may incline kitchens to certain types of violations.

</p>

<figure id="figure3" style="width: 130%; margin-left: -15%; margin-right: -15%; text-align: center;">
  <img src="assets/img/piechart.png" alt="Descriptive Alt Text" style="width: 100%;">
</figure>
<figcaption style="max-width: 100%; margin-left: auto; margin-right: auto; text-align: justify;">
  <b>Figure 3:</b> Pie-charts for the different cuisines showing the distribution of violation codes reported.
</figcaption>


<br>

<p style="text-align: justify; text-justify: inter-word;">
Figure 3 illustrates a consistent trend in the distribution of violation codes, where Facility Sanitation is the most common violation followed by Pest Control across all kitchens. However, considering the criticality distributions from Figure 2, we observe that cuisines with higher percentages of Temperature Control and Staff Hygiene violations pose a greater risk of being in a critical hygiene condition. Specifically, Asian and Pizza cuisines exhibit notably higher percentages in Temperature Control violations, at 16.8% and 15.6%, respectively. Additionally, Asian cuisine also shows a high percentage in Staff Hygiene violations, along with Hotdogs.
Though, based on the latest inspections, it can be concluded that Hotdog Restaurants are the only ones not reported for a violation of Chemical Safety.
</p>

<b style="text-align: justify; text-justify: inter-word;">
DBA
</b>

<p style="text-align: justify; text-justify: inter-word;">
Although there is no distinct pattern indicating higher risks associated with specific cuisines, Figure 4 serves as a practical guide. It plots the top 20 restaurants that consistently receive "Not Critical" flag from the inspections result. Notably, a restaurant can appear multiple times if it is part of a chain, like the various McDonald's locations in NYC. The "Not Critical Proportion" metric used in this chart shows the frequency with which these restaurants pass inspections without critical issues, suggesting they maintain higher standards of cleanliness. If you have a preference for a particular type of cuisine, you can use this data to find establishments with the best health inspection records within that category.
</p>


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

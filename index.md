---
layout: home
---

<h2>From Delicious to Dangerous: The Health Violation Crisis in NYC Eateries</h2>

<b style="text-align: justify; text-justify: inter-word;">
Thinking of dining out in New York City? Picking the perfect spot is more than just about taste—it’s about trust! We’re diving into a dataset describing NYC restaurant inspection results to uncover the connections between location, cuisine, brand, and health violations. Join us on a journey to discover the cleanest kitchens in the city, and make your next meal out a safe and satisfying one!
</b>

<p style="text-align: justify; text-justify: inter-word;">
Every restaurant in NYC has at least one visit from the Department of Health and Mental Hygiene (DOHMH) every year depending on the result of the previous inspection. The dataset describes a total of 224.115 inspection results through a 10-year time period from 2015 to 2024. If any violations are present, the inspection reports define them with specific violation codes. Based on the extent and frequency of these violations, restaurants are categorized as either in a critical or non-critical state.
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

<p style="text-align: justify; text-justify: inter-word;">
So, the violations that most possible to be occurring at a restaurant is regarding sanitation and pest...
</p>

<p style="text-align: justify; text-justify: inter-word;">
Let's take a closer look at the distribution of violation types across different groups with the following visualization:
</p>

<figure id="figure1" style="max-width: 30%; display: block; margin: 10px auto;">  <!-- Adjusted max-width to 30% assuming scale down to 60% -->
    <div style="transform: scale(0.6); transform-origin: top center;"> <!-- Scale applied here -->
        {% include violation_group_distribution.html %}
    </div>
    <figcaption style="text-align: center; width: 100%; display: block; margin-top: 0;">
        <b>Figure 1:</b> Distribution of Violation Types Across Groups. This visualization highlights the frequency of different health violations across various types of NYC restaurants, with an emphasis on facility sanitation issues and pest control.
    </figcaption>
</figure>



<b style="text-align: justify; text-justify: inter-word;">
Craving Thai, burger or Chinese food? Maybe have the cuisine in mind when deciding.
</b>


<p style="text-align: justify; text-justify: inter-word;">
Considering a specific cuisine — Burger, Pizza or a Sandwich? The type of cuisine may influence the likelihood of certain violations due to different cooking methods and ingredients. Figure 2 highlights a consistent distribution of violations across various cuisines, with Facility Sanitation consistently ranking highest. Notably, Chemical Safety violations are absent in eateries serving sandwiches or hot dogs.
</p>

<p style="text-align: justify; text-justify: inter-word;">
Figure 2 reveals a trend of the distribution of the violation codes having the same hiarachy. This being, that all the violation codes are distributed somewhat the same; having the facility sanitation code being the most common, the Pest control the second and so on in all kitchens. Though, the figure tells us, that the Chemical Safety violation haven’t been reported in restaurants serving Sandwiches or Hotdogs.
</p>

<b style="text-align: justify; text-justify: inter-word;">
Hygiene Status
</b>

<br>

<figure id="figure1" style="max-width: 100%; transform: scale(1.2); display: block; margin: 20px auto; position: relative; overflow: hidden;"> 
    {% include choropleth_AVERAGESCOREASIAN.html %}
    <figcaption style="text-align: justify;">
        <b>Figure 1:</b> Distribution of Violation Types Across Groups. This visualization highlights the frequency of different health violations across various types of NYC restaurants, with an emphasis on facility sanitation issues and pest control.
    </figcaption>
</figure>

<br>
<br>

<p style="text-align: justify; text-justify: inter-word;">
The presence of a violation code doesn’t necessarily equate to a critical hygiene status. Therefore, let's look into how many inspections actually led to the restaurant getting flagged as a critical hygiene condition.
</p>


<p style="text-align: justify; text-justify: inter-word;">
Figure 3 illustrates that the probability of a restaurant being flagged as critically unhygienic is approximately 50/50 across all cuisines, indicating that the likelihood of encountering severe health risks does not depend on the type of cuisine served. This trend shows an equal distribution of critical and non-critical health ratings, reinforcing that no specific cuisine is more likely to have severe health violations.
</p>

<b style="text-align: justify; text-justify: inter-word;">
DBA
</b>

<p style="text-align: justify; text-justify: inter-word;">
Although there is no distinct pattern indicating higher risks associated with specific cuisines, Figure 4 serves as a practical guide. It plots the top 20 restaurants that consistently receive "Not Critical" flag from the inspections result. Notably, a restaurant can appear multiple times if it is part of a chain, like the various McDonald's locations in NYC. The "Not Critical Proportion" metric used in this chart shows the frequency with which these restaurants pass inspections without critical issues, suggesting they maintain higher standards of cleanliness. If you have a preference for a particular type of cuisine, you can use this data to find establishments with the best health inspection records within that category.
</p>

<figure id="figure1" style="max-width: 100%; transform: scale(1.2); display: block; margin: 20px auto; position: relative; overflow: hidden;"> 
    <!-- The container where the selected HTML file will be displayed -->
    <div id="mapContainer">
        {% include choropleth_AVERAGESCOREASIAN.html %}
    </div>
    <figcaption style="text-align: justify;">
        <b>Figure 1:</b> Distribution of Violation Types Across Groups. This visualization highlights the frequency of different health violations across various types of NYC restaurants, with an emphasis on facility sanitation issues and pest control.
    </figcaption>
</figure>

<select id="mapDropdown" style="display: block; margin: 20px auto;">
    <option value="choropleth_AVERAGESCOREASIAN.html">Asian Cuisine Score</option>
    <option value="choropleth_AVERAGESCOREBAKERY.html">Bakery Score</option>
    <option value="choropleth_AVERAGESCOREBEVERAGE.html">Beverage Score</option>
    <option value="choropleth_AVERAGESCOREBURGER.html">Burger Score</option>
    <option value="choropleth_AVERAGESCOREHOTDOG.html">Hot Dog Score</option>
    <option value="choropleth_AVERAGESCOREMEXICAN.html">Mexican Cuisine Score</option>
    <option value="choropleth_AVERAGESCOREPIZZA.html">Pizza Score</option>
    <option value="choropleth_AVERAGESCORESALAD.html">Salad Score</option>
    <option value="choropleth_AVERAGESCORESANDWICH.html">Sandwich Score</option>
    <option value="choropleth_AVERAGESCORESEAFOOD.html">Seafood Score</option>
</select>

<script>
document.getElementById('mapDropdown').addEventListener('change', function() {
    var selectedMap = this.value;
    var container = document.getElementById('mapContainer');
    fetch(selectedMap)
        .then(response => response.text())
        .then(html => {
            container.innerHTML = html;
        })
        .catch(error => console.error('Error loading the map:', error));
});
</script>



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

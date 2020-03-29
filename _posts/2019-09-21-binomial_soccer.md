---
title: 'Binomial in the Soccer field'
date: 2019-09-21
permalink: /posts/2019/binomial_soccer
tags:
  - soccer
  - penalty kicks
  - binomial distribution
  - MDS student
  - UBC
---

{% if 'vega' in article.include %}
<style>
.vega-actions a {
    margin-right: 12px;
    color: #757575;
    font-weight: normal;
    font-size: 13px;
}
.error {
    color: red;
}
</style>
<script src="https://cdn.jsdelivr.net/npm//vega@3.3.1"></script>
<script src="https://cdn.jsdelivr.net/npm//vega-lite@2.4.3"></script>
<script src="https://cdn.jsdelivr.net/npm//vega-embed@3.11"></script>
{% endif %}

<i>“To be or not to be ..nomial"</i>  
<span style="color:gray">- Statistical bad joke based on William Shakespeare, by me.</span>

<center><img src="https://media0.giphy.com/media/KnSm1GhuvUjFm/giphy.gif" width="200" alt="goalkeeper"  /></center>

*Source: [Goalkeeper Sweety GIF](https://media0.giphy.com/media/KnSm1GhuvUjFm/giphy.gif), via GIPHY*
  
*Comment: Take a look [here](https://github.com/vcuspinera/vcuspinera.github.io/blob/master/files/2019-binomial_soccer.ipynb) to the Jupyter notebook with the calculations and simulations of this blog.*

In Mexico there are two specific things you probably have learn since kid: eat Chile and play Soccer. The first one is optative, the second is required. Therefore, you could unknow a lot of important things in life -as math, biology or statistics- but for sure you would know about soccer.
  
Personally, I am not a huge soccer fan like my father, father in law, friends, co-workers or even wife, but each 4 years I dust off my green-jersey from 1998's Mexico soccer team and almost religiously follow the World Cup games.
  
In the soccer field, over last World Cups, the national team has been playing quite-good until they meet the Penalty Shootout, where it looks like the team has been cursed for many many years.
  
Recently, I read an interesting article$^1$ related with our National Team's headache, [Penalty Kicks... by the Numbers](https://cdn4.sportngin.com/attachments/document/0057/0846/The_Science_of_Soccer_Online-_Penalty_Kicks__By_the_Numbers.pdf) from Jay Williams, who talks about different statistic related with different soccer leagues and championships. In Williams' article, one specific number jumped to my sight when I read the next sentence:
> _"From the penalty kicker’s standpoint, __85%__ of the penalty shots placed on goal were successful"._
  
As a Mexican who feel that his National Team is cursed, and as a future Data Scientist, I feel the duty of study -and share with you- the probability of winning a game by scoring as much goals as possible in the Penalty Shootout.

However, in the case of Mexico, I felt that this effective soccer goals rate probably was lower, so I look for some statistics from [transfermarkt.com](https://www.transfermarkt.com/mexiko/elfmeterschiessen/verein/6303) and calculate that about __73%__ of the penalty shots placed by the Mexican team were successful.
  
And here is where the Binomial distribution enter the soccer field. The binomial distribution helps us to obtain the probability distribution of `k` number of successes from a total of `n` independent trials, where each one event has a `p` probability of success. The formal formula is expressed after this paragraph. If you are interested to know more about this statistical Binomial distribution I recommend you to visit [Binomial Distribution in Wikipedia](https://en.wikipedia.org/wiki/Binomial_distribution)
$$\binom{n}{k} p^k (1-p)^{n-k}$$

From this point, if I suppose 4 of 5 successful penalty shootout are a good score, I would be interested in obtain the probability that the Mexican team scores __4__ goals in a penalty shootout of __5__ penalty kicks, assuming a __0.73__ probability of score a goal. If I plug in these numbers, the formula looks like $\binom{5}{4} {0.73}^4 (0.27)^1$ ...returning a __38%__ probability that my green team would score 4 out of 5 penalty kicks in a shootout!

If we go further and obtain the complete Binomial distribution, we could find that the probability of scoring 4 or more goals in a penalty shootout for the Mexican team is __59%__.

This doesn't sound as bad. However, if replicate the previous process assuming the `p` of __85%__ of success for score a penalty kickout mentioned by Jay Williams, we would find out that the probability of scoring 4 or more goals in a penalty shootout for an average team is equal to __84%__.

So when we compare these successes rates in scoring 4 out of 5 penalty kicks in a penalty shootout from Mexico (__59%__) vs. the average team (__84%__), we only thing that comes to my mind is that my greens should keep training penalty kicks!

<center><img src="/images/penalty_shootout_dist.png" /></center>

*Source: [Jupyter Notebook of the Binomial in Soccer field](https://github.com/vcuspinera/vcuspinera.github.io/blob/master/files/2019-binomial_soccer.ipynb), 2020, by Vic Cuspinera.*



<center><img src="/images/penalty_shootout_dist.html" /></center>

<div id="vis0"></div>
<script type="text/javascript">
var spec0 = {"config": {"view": {"width": 400, "height": 300}}, "hconcat": [{"data": {"url": "https://vega.github.io/vega-datasets/data/cars.json"}, "mark": "circle", "encoding": {"color": {"type": "nominal", "field": "Origin", "legend": null}, "size": {"type": "ordinal", "field": "Cylinders", "scale": {"range": [20, 100]}}, "tooltip": [{"type": "nominal", "field": "Name"}, {"type": "quantitative", "field": "Horsepower"}, {"type": "quantitative", "field": "Miles_per_Gallon"}, {"type": "ordinal", "field": "Cylinders"}, {"type": "nominal", "field": "Origin"}], "x": {"type": "quantitative", "field": "Horsepower"}, "y": {"type": "quantitative", "field": "Miles_per_Gallon"}}, "selection": {"selector005": {"type": "interval", "bind": "scales", "encodings": ["x", "y"]}}, "transform": [{"filter": {"selection": "selector004"}}]}, {"data": {"url": "https://vega.github.io/vega-datasets/data/cars.json"}, "mark": "rect", "encoding": {"color": {"condition": {"type": "nominal", "field": "Origin", "legend": null, "selection": "selector004"}, "value": "lightgray"}, "size": {"value": 250}, "y": {"type": "nominal", "axis": {"title": "Select Origin"}, "field": "Origin"}}, "selection": {"selector004": {"type": "multi", "encodings": ["color"]}}}], "$schema": "https://vega.github.io/schema/vega-lite/v2.4.3.json"};
var embed_opt0 = {"mode": "vega-lite"};

function showError(el0, error){
el.innerHTML = ('<div class="error">'
+ '<p>JavaScript Error: ' + error.message + '</p>'
+ "<p>This usually means there's a typo in your chart specification. "
+ "See the javascript console for the full traceback.</p>"
+ '</div>');
throw error;
}
const el0 = document.getElementById('vis0');
vegaEmbed("#vis0", spec0, embed_opt0)
.catch(error => showError(el0, error));
</script>


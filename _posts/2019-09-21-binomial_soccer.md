---
title: 'Binomial distribution in the Soccer field'
date: 2019-09-21
permalink: /posts/2019/binomial_soccer
tags:
  - soccer
  - binomial distribution
  - MDS student
  - UBC
---

<i>“To be or not to be ..nomial"</i>  
<span style="color:gray">- Statistical bad joke based on William Shakespeare, by me.</span>

<center><img src="https://media0.giphy.com/media/KnSm1GhuvUjFm/giphy.gif" width="200" alt="goalkeeper"  /></center>

<center>*Source: [Goalkeeper Sweety GIF](https://media0.giphy.com/media/KnSm1GhuvUjFm/giphy.gif), via GIPHY*</center>
  
In Mexico there are two specific things you probably have learn since kid: eat chile and soccer game. The second one is required. Maybe, you could unknow a lot of important things in life -as math, biology or statistics- but for sure you would know about soccer.
  
Personally, I am not a huge soccer fan like my father, father in law, friends, co-workers or even wife, but each 4 years I dust off 1998 green jersey from Mexico's soccer team and almost religiously follow the World Cup games. In the soccer field, over last World Cups, the national team has been palying quite-good well until they meet the Penalty Shootout, where it looks like the team has been cursed for many many years.
  
Recently, I read an interesting article$^1$ related with our National Team's headache, the Penalty Kicks, where the author, Jay Williams, talk about different statistic related with Soccer Leages and Championships as different European and South America's professional leagues, the European Championships and World Cup. In Williams' article, one specific number jumped to my sight when I read the next sentence:
> _"From the penalty kicker’s standpoint, __85%__ of the penalty shots placed on goal were successful"._

As a mexican who's National Team is cursed, and as a future Data Scientist, I feel the duty of study - and share with you- the probability of winning a game by scoring as much goals as possible in the Penalty Shootout.
  
For this purpose, we will need the talk about the Binomial distribution. In case you haven't heard the word "Binomial", do not panic, actually it will be quite fun.

With help of Wikipedia$^2$, we would find that...
> _"In probability theory and statistics, the binomial distribution with parameters n and p is the discrete probability distribution of the number of successes in a sequence of n independent experiments, each asking a yes–no question, and each with its own boolean-valued outcome: success/yes/true/one (with probability p) or failure/no/false/zero (with probability q = 1 − p)."_

If we go further, we find the probability mass function (which we will need for a further calculation) as
#### $\binom{n}{k} p^k (1-p)^{n-k}$  
Where $p$ is the probability of success, $n$ is the total number of events, and $k$ is the number of events we are interested to find out.

...so, long story short, the Binomial Distribution is a statistical tool who needs two imputs: the probability of success (aka $p$) and the number of times we will see the event ($n$), and returns the probability of this happening number of succeses  happens in the n-events.

Returning to the Soccer field, suppose that our team again comes to the Penalty Shootout in the next world cup. If we know that the probability of secoring one Penalty Kick is 85%, which means a $p=0.85$, and we know that our team would shoot 5 penalty kicks ($n=5$), now we can calculate the probability of our team scoring  4 of the 5 penalties.
  
If we compute this information into the previous formula we get $\binom{5}{4} 0.5^4 (0.15)^{1}$, which is equal to 0.3915  
This means that a team has __*39.15%*__ chances of scoring 4 times in a Penalty Shootout! I believe that for the case of Mexico this number is probably higher than the real value, but this could be seen in future analysis.
  
Finally, I believe this was an interesting point of view and learnt some Probability and Statistic in the path! See you around.


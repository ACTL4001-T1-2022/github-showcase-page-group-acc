# Team Selection

---

### Team Construction

The Raritan football team was constructed by performing unsupervised regression analysis on historical player data to determine the statistics that contributed the most to each player’s competitiveness. 

The regressor variables that indicated a player’s relative strength were their **league standing, tournament rank and minutes played divided by ninety (90s).**

The most significant predictors for each player position were identified via sequential replacement subset selection and the relative influence output of the boosting method.

**Significant Predictors for Each Player Position:**
<figure markdown>
  ![predictors](/img/predictors.png)
</figure>

Afterwards, a metric to evaluate each player’s proficiency was formed from the sum of the standardised significant variables. The final team selected using our team selection method is found below with an average team metric of 14.51 and consisting of 30 players.

<figure markdown>
  ![team](/img/team.png)
</figure>

* By using a maximum of 19 predictors, this greatly reduced the number of variables for each player.
* Only the most relevant predictors were chosen to allow for a better picture of each player’s skill and expertise.
* The final metric was comparable and allowed for an accurate depiction of a specific player's skill.

To measure the success of the metric, the following plot demonstrates the relationship between the average metric and the ranking of the teams in the 2021 tournament. 

<figure markdown>
  ![correlation graph](/img/graph.png)
</figure>


There is an approximate relationship indicated by the graph; the higher the rank, the higher the average metric (hence performance of the team) which is in line with our assumptions. To account for any modelling/inference errors and deviations from the actual, more conservative measures were put into place in the prediction of win probabilities. 


---

### Win Probability

Given that our team metric is correlated with team performance, we use the difference between team metrics to derive the probability of a certain team winning.
The intuitive idea behind the method is that greater differences suggest higher probabilities of winning. The probability of winning against each team can be 
seen in the table below:

<figure markdown>
  ![win prob](/img/2021_team_stats.png)
</figure>

We also make a set of (baseline) assumptions on the tournament structure and growth environment: 

* The tournament involves group stages of eight groups, where two teams from each group emerge. The remaining 16 teams play normal tournament bracket 
style matches (up to four more games). 

* The probability our team exits group stages in any given year is a static 40% (this is a conservative assumption to reflect the weak relation between 
win rate and team metric). This can be adjusted for sensitivity analysis. 

* We reinvest all excess cash flows back into the team, and so we very conservatively assume a 0.5% growth rate over our competitors. This growth will be 
reflected by an annual increase in our team metric. This can also be adjusted for sensitivity analysis. 

* We face four random opponents after group stages. 

Using the win rates against each team, and the set of assumptions, the probability of winning the tournament at least once in the next 10 years can be calculated. 
This is visualised in the graphs below with varying set of assumptions (grey line is the baseline). 

<figure markdown>
  ![gs win sens](/img/gswin_sa.png)
</figure>

<figure markdown>
  ![gr sens](/img/gr_sa.png)
</figure>

Under the baseline assumptions, the team has a **95% chance of winning a final in the next ten years**. The chances of placing top 5 in the next 5 years is
approximately 83%. This in turns suggests a sufficiently high chance to place top 10 in the next 5 years. 


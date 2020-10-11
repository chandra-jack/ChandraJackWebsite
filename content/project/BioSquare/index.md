---
date: "2020-10-06T00:00:00Z"
external_link: ""
image:
  caption: 
  focal_point: Smart
links:
- icon: twitter
  icon_pack: fab
  name: Follow
  url: https://twitter.com/ChandraJack1
#slides: example
summary: Tripartite interaction simulation
tags:
- Herbivore
- Invasion
- Microbiology
- Simulation
title: BioSquare
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""
---


### Third-party mutualists have contrasting effects on host invasion under the enemy-release and biotic-resistance hypotheses

Chandra N. Jack • Maren L. Friesen • Arend Hintze • Leigh Sheneman

Plants engage in complex multipartite interactions with mutualists and antagonists,
but these interactions are rarely included in studies that explore plant invasiveness.
When considered in isolation, we know that beneficial microbes can enhance an exotic
plant’s invasive ability and that herbivorous insects often decrease an exotic plant’s
likeliness of success. However, the effect of these partners on plant fitness has not been
well characterized when all three species coevolve. We use computational evolutionary
modeling of a trait-based system to test how microbes and herbivores simultaneously
coevolving with an invading plant affect the invaders’ probability of becoming established.
Specifically, we designed a model that explores how a beneficial microbe would influence
the outcome of an interaction between a plant and herbivore. To model novel interactions,
we included a phenotypic trait shared by each species. Making this trait continuous and
selectable allows us to explore how trait similarities between coevolving plants, herbivores
and microbes affect fitness. Using this model, we answer the following questions: 
1. Can a beneficial plant-microbe interaction influence the evolutionary outcome of antagonistic interactions between plants and herbivores? 
2. How does the initial trait similarity between interacting organisms affect the likelihood of plant survival in novel locations? 
3. Does the effect of tripartite interactions on the invasion success of a plant depend on whether organisms interact through trait similarity [Enemy Release Hypothesis (ERH)] or dissimilarity [Biotic Resistance Hypothesis (BRH)]?

### Conclusions
We found that it was much more difficult for plants to invade under the ERH but that beneficial microbes increase the probability of plant survival in a novel range under both hypotheses. Genetically dissimilar microbes can also have positive benefits, which is important for many mutualisms where there isn’t vertical transmission.


### Simulation setup

#### Environment and genome space
- Each organism has a genome that consists of 2 genes that is set as a 2D vector, G = (X,Y) that acts as a single trait.
- The biotic environment is limited to 128 x 128 toroidal surface. At every update of the model, each organism interacts with eight other random individuals. The interaction strength ($\Delta$) is determined by the phenotypic distance (*d*) between two organisms (*i* and *j*), which is defined using Hamming distance 
*d*<sub>i;j</sub> = |X<sub>i</sub> - X<sub>j</sub>| + |Y<sub>i</sub> - Y<sub>j</sub>|

- A payoff matrix is filled out based on the interacting organisms and fitness is calculated by averaging all payoffs.
{{< figure src="Picture1.png" >}}


#### Evolution in the population
1. 1% of the population killed
2. Replaced through fitness proportional selection
3. Replacements have a 1% chance of mutating

{{< figure src="Picture2.png" >}}

### Predictions

We operate under two assumptions:
* Shared evolutionary history = Defensive Arms Race
* Naïve interactions = Maladapted Plant-Herbivore Interaction

If maladaptation is **disadvantageous** for herbivores:
- <span style = "color:red;">Enemy Release Hypothesis (ERH)</span>
  - Herbivores preferentially consume native plants
- <span style = "color:blue;">H</span> -> <span style = "color:green;">P </span>: -m; Herbivores will attempt to **increase** trait matching

If maladaptation is **advantageous** for herbivores:
- <span style = "color:red;">Biotic Resistance Hypothesis (BRH)</span> 
  - Herbivores preferentially consume introduced plants
- <span style = "color:blue;">H</span> -> <span style = "color:green;">P </span>: 2-m; Herbivores will attempt to **decrease** trait matching

### Experimental Conditions
For each hypothesis we varied the trait similarity between plants and herbivores (6 different values spanning trait space) and between plants and microbes (2 values, near and far)

### Results


#### The presence of a beneficial microbe can increase plant survival in a novel habitat even if the initial trait similarity is low.
  {{< figure src="Picture3.png" >}}

#### The frequency and final outcome of all organisms in the community are influenced by their initial trait similarity to each other.
{{< figure src="Picture4.png"  >}}
{{< figure src="Picture5.png"  >}}


#### Trait similarity between the plant and the microbe always increases as indicated by the decrease in mean difference between the genes. 
The similarity between the plant and the herbivore fluctuates over time. The plant and microbe genomes evolve to yield matching traits

{{< figure src="Picture6.png"  >}}
{{< figure src="Picture7.png"  >}}


#### Selection pressure changes trait values

The variance of the genetically-determined trait in our system can determine whether the organisms are under selection or if changes in the traits are due to genetic drift. When the variance is at the red line (variance = 1/12), then changes in trait values are due to genetic drift. Otherwise, the organisms are under selection.

{{< figure src="Picture8.png"  >}}
{{< figure src="Picture9.png"  >}}






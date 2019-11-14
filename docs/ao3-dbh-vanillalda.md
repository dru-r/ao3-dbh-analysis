# Topics in AO3 Detroit: Become Human fics
What are some topics that appear in D:BH fics?<br>
(Yes, there is smut. There is always smut.)<br>

This was a little exercise I did to try preprocessing for topic modelling (specifically, Latent Dirichlet Allocation, or LDA) on a form of text (long-form fiction) that I typically don't work with in my research. The results aren't too exciting but they're largely interpretable (which is good), so I'm sharing them here. <b>Full blog post detailing preprocessing [here]</b>.

### Interactive visualisation is [here](https://nbviewer.jupyter.org/github/dru-r/ao3-dbh-analysis/blob/master/docs/vanilla%20lda_detroit%20ao3.ipynb)
LDA doesn't generate topic labels for the user, so here are some topic labels I subjectively came up with based on the output [below](###suggested-topic-labels)

## Details about the visualisation
I built the LDA model with Gensim and the visualisation was created using pyLDAvis.<br>

Some things to note, presented in a rather hand-wavey way:
- <b>Circle size</b>: prevalance of topic in corpus. You'll notice that topics 1 and 2 are relatively larger than the rest and are also kind of more general. This is an artefact of a choice by me to follow [this research paper](https://mimno.infosci.cornell.edu/papers/NIPS2009_0929.pdf). As the authors observed it has the nice effect of putting corpus (in this case, DBH)-specific common words into just a couple of frequent topics (i.e., topics 1 and 2). 
- <b>Distances between circles</b>: topics close in semantic meaning should appear closer together. This is achieved via dimensionality reduction. I wouldn't read too much into the actual distances, but the relative distances may be interesting (e.g. topics 24 and 31 - on the bedroom and bathroom - are relatively close).
- <b>List of terms as you click through each topic</b>: useful words for trying to make sense on the topic.
- <b>The blue bars next to each term</b>: overall frequency of the term in the corpus (e.g. 'humans' has a blue bar that almost hits 50k).
- <b>The sliding bar on the top (relevance metric, with adjustable lambda λ)</b>: The [original research paper](https://www.aclweb.org/anthology/W14-3110.pdf) suggests setting it at 0.6 for optimal human interpretation. But in any case, you definitely can play around with it. Setting it at 1 gives you the default output from LDA, and setting it at 0 sets it to really topic-specific words (notice the change in proportion between the red:blue bars). 
- <b>Hovering over a term</b>: To see in what other topics the term appears in (circle size proportional to term-specific frequencies in corpus). A term might appear in different topics because words typically have more than one meaning (e.g. duck - a bird, or to lower one's body).


### Suggested topic labels
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: left;">
      <th></th>
      <th>Topic Labels</th>
      <th>Top 5 words, lambda=.6</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>General language</td>
      <td>fact, idea, reason, thinking, question</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Facial expressions</td>
      <td>gaze, expression, spoke, glanced, continued</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Body parts</td>
      <td>neck, throat, teeth, weight, palm</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Interactive actions</td>
      <td>says, looks, nods, asks, turns</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Movements</td>
      <td>walked, opened, stopped, grabbed, walking</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Android processing</td>
      <td>model, information, data, humans, models</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Sadness/negative emotions</td>
      <td>tears, hurts, crying, pain, please</td>
    </tr>
    <tr>
      <th>8</th>
      <td>DPD</td>
      <td>desk, coffee, office, precinct, chair</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Places</td>
      <td>tree, walls, light, trees, windows</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Smut (past tense)</td>
      <td>cock, hips, moaned, tongue, moan</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Revolution</td>
      <td>humans, leader, revolution, news, everyone</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Crime scene</td>
      <td>scene, crime, victim, crime_scene, police</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Actions inwards/towards</td>
      <td>feels, tries, takes, hears, knows</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Security/law enforcement</td>
      <td>elevator, security, guards, building, ship</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Darkness/death (supernatural/spiritual)</td>
      <td>world, death, blood, soul, fear</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Aggressive actions</td>
      <td>hissed, growled, glared, snapped, slammed</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Reflective actions</td>
      <td>says, knows, wants, thinks, feels</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Guns</td>
      <td>gun, bullet, shot, ground, shoot</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Smut (present tense)</td>
      <td>cock, hips, moans, thighs, dick</td>
    </tr>
    <tr>
      <th>20</th>
      <td>The Mission (the Connor topic?)</td>
      <td>missions, deviants, machine, lieutenant, deviancy</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Swearing/casual language</td>
      <td>fucking, guy, hell, asshole, ass</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Physical affection actions</td>
      <td>love, kiss, kissed, kissing, cheek</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Non-physical affection actions</td>
      <td>smiled, laughed, sighed, chuckled, grinned</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Sleeping</td>
      <td>bed, couch, sleep, bedroom, morning</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Food</td>
      <td>food, kitchen, eat, table, breakfast</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Family</td>
      <td>boy, child, girl, mother, kid</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Medical care</td>
      <td>hospital, doctor, wound, pain, ambulance</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Android errors</td>
      <td>memory, error, system, systems, instability</td>
    </tr>
    <tr>
      <th>29</th>
      <td>Celebrations</td>
      <td>party, dress, crowd, suit, stage</td>
    </tr>
    <tr>
      <th>30</th>
      <td>Thirium/biocomponents</td>
      <td>thirium, pump, thirium_pump, regulator, damaged</td>
    </tr>
    <tr>
      <th>31</th>
      <td>Bathroom</td>
      <td>bathroom, clothes, shower, water, shirt</td>
    </tr>
    <tr>
      <th>32</th>
      <td>Vehicles</td>
      <td>car, seat, road, drive, parking</td>
    </tr>
    <tr>
      <th>33</th>
      <td>Alcohol</td>
      <td>drink, bar, bottle, beer, alcohol</td>
    </tr>
    <tr>
      <th>34</th>
      <td>Phone communication</td>
      <td>phone, text, cigarette, call, message</td>
    </tr>
    <tr>
      <th>35</th>
      <td>Stores</td>
      <td>box, store, shop, flowers, book</td>
    </tr>
    <tr>
      <th>36</th>
      <td>Cold weather</td>
      <td>snow, rain, park, bench, weather</td>
    </tr>
    <tr>
      <th>37</th>
      <td>Pets</td>
      <td>dog, cat, fur, dogs, tail</td>
    </tr>
    <tr>
      <th>38</th>
      <td>Art</td>
      <td>brother, painting, paint, art, canvas</td>
    </tr>
    <tr>
      <th>39</th>
      <td>Android stress</td>
      <td>stress, levels, stress_levels, stress_level, level</td>
    </tr>
    <tr>
      <th>40</th>
      <td>Is this Gavin Reed?</td>
      <td>detective, ace, angel, demon, robo</td>
    </tr>
    <tr>
      <th>41</th>
      <td>Music</td>
      <td>music, song, dance, piano, singing</td>
    </tr>
    <tr>
      <th>42</th>
      <td>Sea</td>
      <td>water, fish, beach, pool, sand</td>
    </tr>
    <tr>
      <th>43</th>
      <td>ABO</td>
      <td>sex, alpha, pole, scent, smell</td>
    </tr>
    <tr>
      <th>44</th>
      <td>AU?</td>
      <td>knife, blade, fire, rope, flames</td>
    </tr>
  </tbody>
</table>




# Differences in topic usage between AO3 D:BH fics of different ratings
This is a follow-up of sorts to my first investigation [(using unigrams)](dbh-ratingslanguse.md).<br>
The TL;DR of that post:<br>
1) Mature and teen fics (to a lesser degree) typically use words that relate more to aggression (e.g. blood) than explicit fics. <br>
2) Explicit fics strongly use smut-centric language. They're followed by mature fics, then teen and gen fics (with little difference between teen and gen fics; thanks to writers who tag appropriately!) <br>
3) It was <b>really</b> hard to understand what characterised teen and especially gen fics just looking at unigrams. <br>
<br>
So - how else to understand what characterises/distinguishes the content of gen/teen/mature/explicit D:BH fics?<br>
<br>
Quite recently I was introduced to the [structural topic modeling algorithm (STM)](https://cran.r-project.org/web/packages/stm/vignettes/stmVignette.pdf). I talked about [applying vanilla latent dirichlet allocation (LDA) before](dbh-vanillalda.md). Vanilla LDA really just retrieves the topics in the corpus and the topic distribution of each document. <br>
<br>
STM goes a step further - it can incorporate metadata about each document in the modeling (e.g. what rating was the story assigned?)*. This metadata may affect topic prevalence (e.g. how often does a topic appear in gen fics vs mature fics?) and/or topic content (e.g. how does the vocabulary of a topic about school differ between gen fics vs teen fics?). With this knowledge of the metadata, you can do pretty cool stuff like compare how topics are used differently by different authors, for example, or track topic prevalence over time.<br>
<sub>*note that STM is not just the vanilla LDA algorithm + metadata. STM falls under the family of topic models but is a separate algorithm. LDA can be used to initialise an STM model but the default is to use non-negative matrix factorisation.</sub><br>
<br>
In this analysis, I focus on how the rating of a fic may affect the prevalence of topics that appear in it. In other words, how are different topics used to different extents between the four ratings? <br>
<br>
Note that there are already some sanity checks in place for this analysis: <br>
1) Explicit fics should have relatively higher prevalence of a smut topic(s) versus all other ratings. <br>
2) Based on my first analysis, mature fics should hopefully be characterised by more aggressive/violence-related topics.<br>

### Content
1) [Topics retrieved by STM](#topics-retrieved-by-stm) <br>
2) [Comparison of topic prevalence between different ratings](#comparison-of-topic-prevalence-between-different-ratings)<br>
3) [Comparison of vocabulary of seemingly similar topics](#comparison-of-vocabulary-of-seemingly-similar-topics)<br>
<br>
Full blog post on preprocessing and training [here](insert link later). STM done and images generated [using the R package](https://www.structuraltopicmodel.com). No fancy interactives because I'm dog vomit bad at R.

## Topics retrieved by STM <br>
### Vocabulary of topics
<sub><b>Topic labels not prescriptive and manually decided on by me</b></sub><br>
<sub><b>Prob = words with highest probability for the topic</b></sub><br>
<sub><b>FREX = words both frequently appearing and relatively exclusive to the topic</b></sub><br>
<sub><b>Words stemmed by the Porter stemmer (truncate word to (pseudo) root form; e.g. cities/city to citi)</b></sub><br>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
</head>
<body>

<div style="overflow-x:auto;">
  <table>
    <tr>
      <th> </th>
      <th>Topic</th>
      <th>Top 5 Prob Words</th>
      <th>Top 5 FREX Words</th>
    </tr>
    <tr>
      <td>1</td>
      <td>Art</td>
      <td>paint, play, book, man, music</td>
      <td>paint, danc, song, music, art</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Android biocomponents</td>
      <td>thirium, memori, bodi, damag, pump</td>
      <td>wire, repair, regul, thirium, biocompon</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Crime cases</td>
      <td>case, lieuten, scene, offic, crime</td>
      <td>crime, victim, evid, scene, crime_scene</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Android stress/error</td>
      <td>level, stress, system, error, stress_level</td>
      <td>stress_level, error, stress, level, instabl</td>
    </tr>
    <tr>
      <td>5</td>
      <td>DPD</td>
      <td>detect, desk, coffe, offic, partner</td>
      <td>desk, break_room, coffe, detect, captain</td>
    </tr>
    <tr>
      <td>6</td>
      <td>Medical</td>
      <td>detect, chest, keep, shoulder, son</td>
      <td>doctor, technician, hospit, slave, put_hand</td>
    </tr>
    <tr>
      <td>7</td>
      <td>Building interiors</td>
      <td>door, room, floor, wall, step</td>
      <td>stair, hallway, hall, door, door_open</td>
    </tr>
    <tr>
      <td>8</td>
      <td>Family/other AU</td>
      <td>brother, boy, mother, child, man</td>
      <td>alpha, brother, twin, demon, mother</td>
    </tr>
    <tr>
      <td>9</td>
      <td>Swearing</td>
      <td>fuck, shit, hell, ass, fuckin</td>
      <td>shit, fuck, fuckin, fucker, get_fuck</td>
    </tr>
    <tr>
      <td>10</td>
      <td>Negative emotion</td>
      <td>tear, hurt, cri, breath, happen</td>
      <td>tear, cri, sob, trembl, hurt</td>
    </tr>
    <tr>
      <td>11</td>
      <td>Expression</td>
      <td>word, express, question, mind, tone</td>
      <td>tone, express, convers, intent, goal</td>
    </tr>
    <tr>
      <td>12</td>
      <td>Driving</td>
      <td>car, seat, drive, park, phone</td>
      <td>car, passeng, driver, park_lot, passeng_seat</td>
    </tr>
    <tr>
      <td>13</td>
      <td>Resting</td>
      <td>bed, sleep, couch, night, room</td>
      <td>couch, sleep, bed, pillow, blanket</td>
    </tr>
    <tr>
      <td>14</td>
      <td>Deviancy</td>
      <td>devianc, mission, emot, machin, deviat</td>
      <td>program, machin, human, emot, mission</td>
    </tr>
    <tr>
      <td>15</td>
      <td>Aggression</td>
      <td>hiss, fist, yank, snarl, smoke</td>
      <td>man, stare, feet, back, air</td>
    </tr>
    <tr>
      <td>16</td>
      <td>Injury</td>
      <td>blood, pain, wound, knife, leg</td>
      <td>knife, wound, bleed, blood, pain</td>
    </tr>
    <tr>
      <td>17</td>
      <td>Touch</td>
      <td>finger, lip, skin, chest, breath</td>
      <td>fingertip, palm, thumb, brow, flutter</td>
    </tr>
    <tr>
      <td>18</td>
      <td>Smut</td>
      <td>finger, cock, mouth, hip, kiss</td>
      <td>moan, cock, hip, thrust, thigh</td>
    </tr>
    <tr>
      <td>19</td>
      <td>Feelings</td>
      <td>felt, took, knew, came, found</td>
      <td>felt, felt_hand, made_feel, felt_someth, took_moment</td>
    </tr>
    <tr>
      <td>20</td>
      <td>Setting</td>
      <td>dog, water, snow, tree, sky</td>
      <td>tree, sky, fish, sun, grass</td>
    </tr>
    <tr>
      <td>21</td>
      <td>Dialogue 1</td>
      <td>talk, nod, tell, took, went</td>
      <td>said_look, thank_said, know_said, said_smile, look_said</td>
    </tr>
    <tr>
      <td>22</td>
      <td>Dialogue 2</td>
      <td>give, tell, nod, sit, shake</td>
      <td>goe, say_look, shake_head, say_voic, say_know</td>
    </tr>
    <tr>
      <td>23</td>
      <td>Revolution</td>
      <td>peopl, human, other, leader, everyon</td>
      <td>leader, group, freedom, ship, revolut</td>
    </tr>
    <tr>
      <td>24</td>
      <td>Affection</td>
      <td>love, kiss, lip, cheek, press</td>
      <td>love, love_love, kiss, kiss_cheek, boyfriend</td>
    </tr>
    <tr>
      <td>25</td>
      <td>Food/eating</td>
      <td>kitchen, food, eat, tabl, cloth</td>
      <td>food, cook, bowl, dish, eat</td>
    </tr>
    <tr>
      <td>26</td>
      <td>Movement</td>
      <td>walk, nod, man, led, room</td>
      <td>bus, girl, nod_head, walk, place_hand</td>
    </tr>
    <tr>
      <td>27</td>
      <td>Guns</td>
      <td>gun, shot, kill, bullet, shoot</td>
      <td>gun, bullet, shoot, aim, trigger</td>
    </tr>
    <tr>
      <td>28</td>
      <td>School</td>
      <td>friend, talk, kid, year, day</td>
      <td>school, dad, friend, date, kid</td>
    </tr>
    <tr>
      <td>29</td>
      <td>Technology</td>
      <td>model, inform, use, design, screen</td>
      <td>tablet, data, project, test, product</td>
    </tr>
    <tr>
      <td>30</td>
      <td>Time</td>
      <td>day, noth, everyth, left, done</td>
      <td>spent, day, gotten, week, gone</td>
    </tr>
  </table>
</div>

</body>
</html>

### Prevalence of topics in corpus of fics <br>
<sub><b>Topic label followed by top 5 FREX words</b></sub><br>
![image](/visuals/07_stm/topic_props.jpg)

## Comparison of topic prevalence between different ratings
### Focusing on Gen <br>
Some results unlike the previous unigram comparison! We see that versus the other ratings, D:BH gen is characterised by relatively greater use of the art, resting, feelings, setting, affection, food/eating, movement, and school topics. These are rather reminiscent of fluff fics (to me, you may disagree). Check out the plots below:<br>
<br>
<b>Gen vs Teen</b><br>
![image](/visuals/07_stm/gen-teen.jpg)<br>
<b>Gen vs Mature</b><br>
![image](/visuals/07_stm/gen-mature.jpg)<br>
<b>Gen vs Explicit</b><br>
![image](/visuals/07_stm/gen-explicit.jpg)<br>
### Focusing on Teen <br>
D:BH Teen and D:BH Mature don't seem to diverge greatly beyond Mature incorporating more usage of touch and smut topics (physicality). In contrast, D:BH Teen has a greater usage of topics like deviancy, injury, guns, crime (the building interiors topic is probably related to crime scene setups), android stress, the revolution versus D:BH Explicit. This closely matches the results from the unigram comparison (sanity check ticked). Note too how Gen and Teen are similar in their (lesser) usage of the smut topic versus Explicit (another sanity check ticked). Check out the plots below:<br> 
<br>
<b>Teen vs Mature</b><br>
![image](/visuals/07_stm/teen-mature.jpg)<br>
<b>Teen vs Explicit</b><br>
![image](/visuals/07_stm/teen-explicit.jpg)<br>
### Focusing on Mature <br>
<b>Mature vs Explicit</b><br>
Like D:BH Teen, D:BH Mature has greater usage of topics like crime cases, android stress, negative emotion, injury, guns, revolution versus D:BH explicit. D:BH Explicit is largely distinguished by its Mature counterpart by the smut topic (and to a much lesser degree, the touch and affection topics). These closely follow the unigram comparison (sanity check ticked). Check out the plot for the topic usage comparison below:<br>
![image](/visuals/07_stm/mature-explicit.jpg)<br>
Note how strongly the smut topic is characteristic of Explicit fics (moreso than violence/crime-related topics for Mature fics) - this also matches the H-statistic of the unigrams. If you return to the charts from that post ([unigrams characteristic of mature fics](/visuals/05_kw/mature_n1.html), [unigrams characteristic of explicit fics](/visuals/05_kw/explicit_n1.html)), you'll see that the H-statistic (and thus the corresponding effect size) of smut words for Explicit fics is way larger than the violence-related words for Mature fics. <br>

## Comparison of vocabulary of seemingly similar topics
This is tangential to characterising the different ratings. But when I was labeling the topics, there were a couple of topics that seemed ambiguously similar to me. STM offers a feature to compare the vocabulary of two topics - I found this very helpful. <br>
<br>
Note: Words further along the left/right axis are more closely related to the topic labelled on the left/right respectively. Words in the middle (around the dotted line) are central to <i>both</i> topics. Word size is relative to its frequency within the two topics (bigger = more frequent).<br>
### Aggression vs Injury <br>
![image](/visuals/07_stm/aggvsinjury.jpg)<br>
### Injury vs Guns <br>
![image](/visuals/07_stm/injuryvsguns.jpg)<br>
### Touch vs Smut <br>
![image](/visuals/07_stm/touchvssmut.jpg)<br>
### Touch vs Affection <br>
![image](/visuals/07_stm/touchvsaffection.jpg)<br>

## Ending notes <br>
1) Though I accounted for story publishing date in the modeling, I did not show the results here. Previously I've already tried a dynamic topic model on this corpus and I didn't see a lot of changes in topics over time. I think the Detroit fandom is still too new, but it would be exciting to apply this to Harry Potter's. <br>
<br>
2) I'm concerned by how small the confidence intervals are in the topic prevalence comparison charts; I'm not really sure if this is expected behaviour (KIV-ing this). <br>
<br>
3) Overall I'm still quite thrilled by what it's achieved in this very specific corpus of fiction. The STM would be very cool to apply on more social science-driven corpora (as suggested by its original authors). However, I'm not entirely clear about covariate selection for modeling and assessing the 'quality' of the covariates used/model fit. I hope to find more readings on this.

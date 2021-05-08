# Drarry on AO3: Tropes through tags
This is something that I’ve been dreaming of (sounds like a hyperbole, but it really isn’t!) since I started this little fandom/fic analysis project. This is really just about only possible through AO3’s generous data dump, since scraping the huge amount of Harry Potter fics on the site would be quite difficult (for me, as a solo grunt, and AO3’s servers – if I didn’t rate limit myself properly). <br><br>
After getting into a fandom for a while, we kind of intuitively know about the tropes that exist in it after consuming the works of others (and maybe even producing our own). Within Harry Potter, there are so many that have accumulated across the history of the fandom – creature inheritance, Hogwarts 8th year, Harry in Slytherin AUs, etc. And we know that when we see certain tags – e.g., creature inheritance – we can expect to see certain other tags (e.g. veela Draco Malfoy, magical bonds/soulmates). <b> Are we able to capture some of these tropes or ideas automatically given a huge dataset of tags?</b> I attempt that here, looking at each rating (Gen/Teen/Mature/Explicit) separately. <br><br>
<b>As with my work on using tags to characterise characters in D:BH fandom, I want to reiterate that tags capture only a small part of the picture.</b> Many tropes aren’t explicitly laid out in their tags. Also, due to the way I’ve done preprocessing, only tags that meet a certain threshold for usage are kept – so I can’t really address much rarer tags. In short – this is really a rough overview. <br><br>
Typically I lay out my preprocessing steps on [my Tumblr](https://program-800.tumblr.com) and just link the main images here, but I’ve decided to tie them both together here since the preprocessing is pretty integral in influencing what you see in the end. <br>

## Content
1) [Preprocessing and network creation](#preprocessing-and-network-creation) <br>
2) [Explicit tag network](#explicit-tag-network)<br>
3) [Mature tag network](#mature-tag-network)<br>
4) [Teen tag network](#teen-tag-network)<br>
5) [Gen tag network](#gen-tag-network)<br>
6) [Conclusion](#conclusion)<br>
<br><br>
## Preprocessing and network creation
### Tag standardisation and fic selection
The dataset from AO3 has a very nice mapping of tags to the ‘main’ tag. For example, tags Draco, Draco Malfoy, Dracy Malfoy – there is an indication that all these tags actually mean the same thing, and map back to the ‘main’ character tag Draco Malfoy. Thus, before I did anything else – for standardisation, I converted all the not-main tags to their respective ‘main’ tags (i.e., subbing ‘Dracy Malfoy’ to ‘Draco Malfoy’). <br><br>
I then selected a certain subset of Drarry-tagged fics: those written in English and those with ‘Harry Potter’ as the only fandom tagged. That left me 47403 fics. The following preprocessing and network creation steps were then applied separately to each of the four ratings. <br>
### Preprocessing tags and finding clusters of tags
I worked with only the freeform tags. For each fic, I concatenated its freeform tags into a list. The only tags I removed were ‘Draco Malfoy – Freeform’ and ‘Harry Potter – Freeform’. For each rating, the max times a tag appeared was capped around 10+% of all fics of that rating. The main filtering I did was to keep only tags that appeared at least 3 (for Explicit, General) or 4 (for Teen, Mature) times. If only 1 or 2 fics used the tags, it wouldn’t give that much information and might lead to noise in the final network. <br><br>
I then created a basic network with the tags represented as nodes and edges between them weighted by the number of fics that used both the tags. Following that, I applied [Serrano’s disparity filter]( https://www.pnas.org/content/106/16/6483) at a value of α = .001 to only keep only statistically significant edges. <br><br>
After that, I applied the Louvain algorithm. I ran it for 1000 times and picked the partition with the highest modularity. Do note that the modularity figures were typically on the lower end across all ratings, meaning that there weren’t very dense/clear subcluster of tags within the networks. For high modularity, you’d want to see a network with dense links between nodes of the same group, with sparse links between different groups. I list the modularity figures for each rating in the respective section below. <br><br>
The tags aren’t the be-all-and-end-all of things, for sure – given the restrictive filtering I used and the lack of examination of actual fic content. Nevertheless, we do still see some semantically coherent and interesting subclusters arise for each rating. The graphs were created with the help of pyvis, as usual. I hope you have fun exploring them! <br>
### Details of what is shown in the networks of each rating 
There are two main sets of networks shown for each rating: <br>
1) A full network – this contains all the tags leftover after filtering for that rating. These are a bit laggy (especially the explicit one), so click with caution if you have some important tabs open in your browser, I guess. In these networks, you will see the tags coloured by the group assigned by the Louvain algorithm. Hovering/clicking on a node shows up to the top 5 tags that co-occur with the node’s tag, regardless of group. Hovering over an edge shows the number of fics that have been tagged with the respective two nodes. <br><br>
2) Multiple networks, split by Louvain group – each network contains only the tags assigned to the same group by the Louvain algorithm. Many of them consist of only 2 nodes, I’ve noted networks in the table with 5 or less nodes with an asterisk. Hovering/clicking on a node shows up to the top 5 tags in that same Louvain group that co-occur with the node’s tag. Hovering over an edge shows the number of fics that have been tagged with the respective two nodes. <br><br>
I’ve also added my comments on each group, but they’re just my opinion/own scribbles on what the group might be about. Again – modularity figures were low so it’s not like we got well-defined subclusters. These aren’t the gold standard of truth by any means, but I think they do at least reveal somewhat some tropes that we as readers/writers have come to be familiar with. <br>
## Explicit tag network
<b>Modularity = .336</b><br>

### Full network
[Link](/visuals/drarry/01_tagnetworks/explicit/full_explicit.html)<br>

### Networks by Louvain group
Asterisks* denote a network with 5 or less nodes.<br><br>

<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
</head>
<body>

<div style="overflow-x:auto;">
  <table>
    <tr>
      <th></th>
      <th>Example tags</th>
      <th>Link to network</th>
     <th>Comments</th>
    </tr>
    <tr>
      <td>1</td>
      <td>Post-Hogwarts, Auror Harry Potter, Clubbing, POV Draco Malfoy, Potions Master Draco Malfoy</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/0_explicit.html">Link</a></td>
      <td>about when the boys are adults/finding romance after school</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Alternate Universe, First Time, Mpreg, Drama, Fluff</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/1_explicit.html">Link</a></td>
       <td>AUs and main story ‘themes’; perhaps fluff/humor got mixed up with the darker stuff due to sharing common links  in AU/mpreg, etc – which could fall on either side of the spectrum</td>
    </tr>
    <tr>
     <td>3</td>
      <td>Hogwarts Eighth Year, Slow Burn, Depression, Secret Relationship, Coming Out</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/2_explicit.html">Link</a></td>
       <td>immediate post-war stuff and its consequences</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Rimming, Rough Sex, Dirty Talk, Possessive Behaviour, Begging</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/3_explicit.html">Link</a></td>
       <td>this as much is clear, i think</td>
    </tr>
    <tr>
      <td>5</td>
      <td>Bottom Draco Malfoy, Porn with Feelings, Established Relationship, Top Harry Potter, Harry Potter Has a Large Cock</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/4_explicit.html">Link</a></td>
       <td>i really want to call this the bottom draco gang</td>
    </tr>
    <tr>
      <td>6</td>
      <td>BDSM, Orgasm Delay/Denial, Dom Harry, Sex Toys, Praise Kink</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/5_explicit.html">Link</a></td>
       <td>definitely bdsm</td>
    </tr>
    <tr>
      <td>7</td>
      <td>Oral Sex, Consent, Sex, Anal, Gay Sex</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/6_explicit.html">Link</a></td>
       <td>not really sure why this is on its own – perhaps the tags are more general</td>
    </tr>
    <tr>
      <td>8</td>
      <td>Alpha/Beta/Omega Dynamics, Omega Draco Malfoy, Alpha Harry Potter, Omega Verse, Knotting</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/7_explicit.html">Link</a></td>
       <td>a/b/o</td>
    </tr>
    <tr>
      <td>9</td>
      <td>Top Draco Malfoy, Bottom Harry Potter, Dom/sub Undertones, First Time Bottoming, Draco Malfoy Has a Large Cock</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/8_explicit.html">Link</a></td>
       <td>is this the bottom harry gang</td>
    </tr>
    <tr>
      <td>10</td>
      <td>Creature Fic, Veela Draco Malfoy, Creature Harry Potter, Mates, Veela Mates</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/9_explicit.html">Link</a></td>
       <td>creature inheritance</td>
    </tr>
    <tr>
      <td>11</td>
      <td>Manipulative Albus Dumbledore, Ginny Weasley Bashing, Ron Weasley Bashing, Molly Weasley Bashing, Hermione Granger Bashing</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/10_explicit.html">Link</a></<td>
       <td>taking another pov of harry’s story</ td>
    </tr>
    <tr>
      <td>12*</td>
      <td>Threesome – M/M/M, Foursome – M/M/M/M, Spitroasting, Double Penetration, Teacher-Student Relationship</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/11_explicit.html">Link</a></<td>
       <td>orgies?</ td>
    </tr>
    <tr>
      <td>13*</td>
      <td>Christmas, Snow, Christmas Presents, Christmas Fluff, Christmas Smut</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/12_explicit.html">Link</a></td>
       <td>christmas</td>
    </tr>
    <tr>
      <td>14*</td>
      <td>Audio Format: MP3, Podfic & Podficced Works, Podfic, Audio Format: Streaming, Audio Format: M4B</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/13_explicit.html">Link</a></td>
       <td>podfics</td>
    </tr>
    <tr>
      <td>15*</td>
      <td>Rape, Torture, Psychological Torture, Sexual Violence</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/14_explicit.html">Link</a></td>
       <td>non-con stuff</td>
    </tr>
    <tr>
      <td>16*</td>
      <td>Bisexual Harry Potter, Gay Draco Malfoy, Gay Harry Potter, Bisexual Draco Malfoy</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/15_explicit.html">Link</a></td>
       <td>sexuality of them both</td>
    </tr>
    <tr>
      <td>17*</td>
      <td>Fanart, Art, Digital Art, NSFW Art</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/16_explicit.html">Link</a></td>
       <td>art stuff</td>
    </tr>
    <tr>
      <td>18*</td>
      <td>Vampires, Vampire Draco Malfoy, Blood Drinking, Vampire Sex</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/17_explicit.html">Link</a></td>
       <td>vampires! baz, anyone?</td>
    </tr>
    <tr>
      <td>19*</td>
      <td>Public Sex, Public Nudity, Public Blow Jobs</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/18_explicit.html">Link</a></td>
       <td>public sex, clearly</td>
    </tr>
    <tr>
      <td>20*</td>
      <td>Professor Draco Malfoy, Professor Harry Potter, Hogwarts Professors</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/19_explicit.html">Link</a></td>
       <td>the boys as professors</td>
    </tr>
    <tr>
      <td>21*</td>
      <td>Vaginal Sex, Vaginal Fingering, Cunnilingus</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/20_explicit.html">Link</a></td>
       <td>female-gendered sex acts</td>
    </tr>
    <tr>
      <td>22*</td>
      <td>Belly Kink, Belly Rubs, Weight Gain</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/21_explicit.html">Link</a></td>
       <td>weight gain kinks</td>
    </tr>
    <tr>
      <td>23*</td>
      <td>Genderswap, Female Harry, Trans Draco Malfoy</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/22_explicit.html">Link</a></td>
       <td>non-male representations of harry/draco</td>
    </tr>
    <tr>
      <td>24*</td>
      <td>Quidditch Player Harry, Quidditch Player Draco Malfoy</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/23_explicit.html">Link</a></td>
       <td>quidditch careers</td>
    </tr>
    <tr>
      <td>25*</td>
      <td>Fanfiction, Rating: NC17</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/24_explicit.html">Link</a></td>
       <td></td>
    </tr>
    <tr>
      <td>26*</td>
      <td>Emotional/Psychological Abuse, Physical Abuse</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/25_explicit.html">Link</a></td>
       <td>abuse</td>
    </tr>
    <tr>
      <td>27*</td>
      <td>Age Difference, Cross-Generation Relationship</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/26_explicit.html">Link</a></td>
       <td>age difference relationships</td>
    </tr>
    <tr>
      <td>28*</td>
      <td>Gryffindor, Slytherin</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/27_explicit.html">Link</a></td>
       <td>this group of 2 appears in the other ratings too, and i’m not entirely sure why</td>
    </tr>
    <tr>
      <td>29*</td>
      <td>Rape Recovery, Rape Aftermath</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/28_explicit.html">Link</a></td>
       <td>recovering/handling rape</td>
    </tr>
    <tr>
      <td>30*</td>
      <td>Chubby Draco Malfoy, Body Image</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/29_explicit.html">Link</a></td>
       <td>i’ve seen a couple of chubby!harry fics around too, but perhaps those tags fell off in the filtering</td>
    </tr>
    <tr>
      <td>31*</td>
      <td>Soulmate-Identifying Marks, Alternate Universe - Soulmates</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/30_explicit.html">Link</a></td>
       <td>soulmate AUs</td>
    </tr>
    <tr>
      <td>32*</td>
      <td>Slytherin Harry Potter, Dark Harry</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/31_explicit.html">Link</a></td>
       <td>dark harry AU – i’ve seen it a couple of times tied with weasley/dumbledore bashing, but they’re likely not entirely mutually inclusive</td>
    </tr>
    <tr>
      <td>33*</td>
      <td>Switch Draco Malfoy, Switch Harry Potter</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/32_explicit.html">Link</a></td>
       <td>switching</td>
    </tr>
    <tr>
      <td>34*</td>
      <td>Legilimency (Harry Potter), Occlumency (Harry Potter)</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/33_explicit.html">Link</a></td>
       <td>not a surprise; both boys were involved in these canonically</td>
    </tr>
    <tr>
      <td>35*</td>
      <td>Touching, HP Taste of Smut Fest 2020</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/34_explicit.html">Link</a></td>
       <td>i feel like there might’ve been a couple more tags here that got filtered out</td>
    </tr>
    <tr>
      <td>36*</td>
      <td>Supernatural Elements, Horror</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/35_explicit.html">Link</a></td>
       <td>horror</td>
    </tr>
    <tr>
      <td>37*</td>
      <td>Kinktober, Kinktober 2019</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/36_explicit.html">Link</a></td>
       <td>that certain time of the year</td>
    </tr>
  </table>
</div>

</body>
</html>

<br>
## Mature tag network
<b>Modularity = .521</b><br>

### Full network
[Link](/visuals/drarry/01_tagnetworks/mature/full_mature.html)<br>

### Networks by Louvain group
Asterisks* denote a network with 5 or less nodes.<br><br>

<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
</head>
<body>

<div style="overflow-x:auto;">
  <table>
    <tr>
      <th></th>
      <th>Example tags</th>
      <th>Link to network</th>
     <th>Comments</th>
    </tr>
    <tr>
     <td>1</td>
      <td>Post-Hogwarts, Hogwarts Sixth Year, Harry Potter Epilogue What Epilogue | EWE, Draco Malfoy Redemption, Hogwarts Eighth Year</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/0_mature.html">Link</a></td>
      <td>canon divergence – either post-war, or in the turning point of their sixth year; seems similar to explicit’s group 1 and 3</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Alternate Universe, Hurt/Comfort, Mpreg, Drama, Drug Use</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/1_mature.html">Link</a></td>
       <td>AUs and main story ‘themes’; this is rather similar to explicit’s group 2</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Albus Dumbledore Bashing, Ginny Weasley Bashing, Creature Inheritance, Good Malfoy Family (Harry Potter), Dark Harry</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/2_mature.html">Link</a></td>
       <td>dark harry AU</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Depression, Post-Traumatic Stress Disorder – PTSD, Panic Attacks, Mental Health Issues, Suicide Attempt</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/3_mature.html">Link</a></td>
       <td>mental health</td>
    </tr>
    <tr>
      <td>5</td>
      <td>Drarry, wolfstar, romione, Gay, Smut</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/4_mature.html">Link</a></td>
       <td>not terribly sure about this one, to be honest</td>
    </tr>
    <tr>
      <td>6</td>
      <td>Anal Sex, Blow Jobs, Oral Sex, Hand Jobs, Rimming</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/5_mature.html">Link</a></td>
       <td>sexual stuff</td>
    </tr>
    <tr>
      <td>7</td>
      <td>Audio Format: MP3, Podfic, Audio Format: M4B, Audio Format: Streaming, Podfic & Podficced Works</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/6_mature.html">Link</a></td>
       <td>podfics</td>
    </tr>
    <tr>
      <td>8*</td>
      <td>Good Draco Malfoy, Good Narcissa Black Malfoy, Good Severus Snape, Draco Malfoy & Harry Potter Friendship</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/7_mature.html">Link</a></td>
       <td>where narcissa is a soft mom</td>
    </tr>
    <tr>
      <td>9*</td>
      <td>Gay Draco Malfoy, Bisexual Harry Potter, Bisexual Draco Malfoy, Gay Harry Potter</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/8_mature.html">Link</a></td>
       <td>sexuality</td>
    </tr>
    <tr>
      <td>10*</td>
      <td>Creature Fic, Veela Draco Malfoy, Veela (Harry Potter), Veela Mates</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/9_mature.html">Link</a></td>
       <td>creature inheritance/veelas</td>
    </tr>
    <tr>
      <td>11*</td>
      <td>Soulmate-Identifying Marks, Alternate Universe – Soulmates, Soulmates, Soul Bond</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/10_mature.html">Link</a></td>
       <td>soulmate AU</td>
    </tr>
    <tr>
      <td>12*</td>
      <td>Drabble, Ratings: R, Drabble Collection</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/11_mature.html">Link</a></td>
       <td></td>
    </tr>
    <tr>
      <td>13*</td>
      <td>Bottom Draco Malfoy, Top Harry, Top Harry Potter</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/12_mature.html">Link</a></td>
       <td>it’s a little interesting that a lot of the bottom draco gang tags from explicit group 5 don’t pop up together here</td>
    </tr>
    <tr>
      <td>14*</td>
      <td>Digital Art, Art, Fanart</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/13_mature.html">Link</a></td>
       <td>fanart</td>
    </tr>
    <tr>
      <td>15*</td>
      <td>Dom Draco Malfoy, Sub Harry, Sub Harry Potter</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/14_mature.html">Link</a></td>
       <td>dom draco</td>
    </tr>
    <tr>
      <td>16*</td>
      <td>Sub Draco Malfoy, Dom Harry, Dom Harry Potter</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/15_mature.html">Link</a></td>
       <td>sub draco</td>
    </tr>
    <tr>
      <td>17*</td>
      <td>Top Draco Malfoy, Bottom Harry, Bottom Harry Potter</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/16_mature.html">Link</a></td>
       <td>top draco</td>
    </tr>
    <tr>
      <td>18*</td>
      <td>Chubby Draco Malfoy, Belly Kink, Weight Gain</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/17_mature.html">Link</a></td>
       <td>weight gain kink</td>
    </tr>
    <tr>
      <td>19*</td>
      <td>Alpha/Beta/Omega Dynamics, Omega Draco Malfoy, Alpha Harry Potter</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/18_mature.html">Link</a></td>
       <td>a/b/o</td>
    </tr>
    <tr>
      <td>20*</td>
      <td>Abuse, Child Abuse</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/19_mature.html">Link</a></td>
       <td>abuse</td>
    </tr>
    <tr>
      <td>21*</td>
      <td>Harry Potter Epilogue Compliant, Infidelity</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/20_mature.html">Link</a></td>
       <td>get married -> cheat</td>
    </tr>
    <tr>
      <td>22*</td>
      <td>Alternate Universe – Non-Magical, Alternate Universe – Modern Setting</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/21_mature.html">Link</a></td>
       <td>muggle-ish AUs?</td>
    </tr>
    <tr>
      <td>23*</td>
      <td>Jealousy, Possessive Behavior</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/22_mature.html">Link</a></td>
       <td>what it says on the tin</td>
    </tr>
    <tr>
      <td>24*</td>
      <td>Boys In Love, Boys Kissing</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/23_mature.html">Link</a></td>
       <td>this has fluff energy</td>
    </tr>
    <tr>
      <td>25*</td>
      <td>Holidays, Christmas</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/24_mature.html">Link</a></td>
       <td>the holiday season</td>
    </tr>
    <tr>
      <td>26*</td>
      <td>Ron Weasley is a Good Friend, Hermione Granger is a Good Friend</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/25_mature.html">Link</a></td>
       <td>the golden trio being supportive gang</td>
    </tr>
    <tr>
      <td>27*</td>
      <td>Professor Harry Potter, Professor Draco Malfoy</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/26_mature.html">Link</a></td>
       <td>the boys as professors</td>
    </tr>
    <tr>
      <td>28*</td>
      <td>Remus Lupin Lives, Sirius Black Lives</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/27_mature.html">Link</a></td>
       <td>makes me think of fics where they become the parental figures for harry</td>
    </tr>
    <tr>
      <td>29*</td>
      <td>Female Harry Potter, Alternate Universe – Gender Changes</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/28_mature.html">Link</a></td>
       <td>i’ve seen female draco malfoy as a tag too – perhaps it got filtered out here</td>
    </tr>
    <tr>
      <td>30*</td>
      <td>Gryffindor, Slytherin</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/mature/29_mature.html">Link</a></td>
       <td> </td>
    </tr>
  </table>
</div>

</body>
</html>

<br>
## Teen tag network
<b>Modularity = .390</b><br>

### Full network
[Link](/visuals/drarry/01_tagnetworks/teen/full_teen.html)<br>

### Networks by Louvain group
Asterisks* denote a network with 5 or less nodes.<br><br>

<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
</head>
<body>

<div style="overflow-x:auto;">
  <table>
    <tr>
      <th></th>
      <th>Example tags</th>
      <th>Link to network</th>
     <th>Comments</th>
    </tr>
    <tr>
      <td>1</td>
      <td>Hogwarts Eighth Year, Post-War, Mutual Pining, Boys In Love, Kissing</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/0_teen.html">Link</a></td>
      <td>eighth year getting together</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Humor, Romance, One Shot, Slash, Mpreg</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/1_teen.html">Link</a></td>
       <td>fluff and crack</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Harry Potter Epilogue What Epilogue | EWE, Draco Malfoy in the Muggle World, Post-Hogwarts, POV Harry Potter, Number Twelve Grimmauld Place</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/2_teen.html">Link</a></td>
       <td>post-war getting together</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Hurt/Comfort, Post-Traumatic Stress Disorder – PTSD, Angst with a Happy Ending, Fluff and Angst, Draco Malfoy Needs a Hug</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/3_teen.html">Link</a></td>
       <td>mental health/trauma experience and possible recovery</td>
    </tr>
    <tr>
      <td>5</td>
      <td>Established Relationship, Drabble, Domestic Fluff, Ambiguous/Open Ending, Slice of Life</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/4_teen.html">Link</a></td>
       <td>established r/s fluff mostly</td>
    </tr>
    <tr>
      <td>6</td>
      <td>Slytherin Harry Potter, Alternate Universe – Canon Divergence, Alternate Universe – No Voldemort, Female Draco Malfoy, Good Slytherins</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/5_teen.html">Link</a></td>
       <td>rewriting canon</td>
    </tr>
    <tr>
      <td>7</td>
      <td>Drarry, Hogwarts, How Do I Tag, I’m Bad At Tagging, Gryffindor</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/6_teen.html">Link</a></td>
       <td>can i call this the i’m not sure what tags to add group? i empathise with this a ton</td>
    </tr>
    <tr>
      <td>8</td>
      <td>Slow Burn, Enemies to Friends to Lovers, Draco Malfoy Redemption, Hogwarts Sixth Year, Post-Battle of Hogwarts</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/7_teen.html">Link</a></td>
       <td>the draco malfoy redemption arc, set in either 6th year or after the war</td>
    </tr>
    <tr>
      <td>9</td>
      <td>Auror Harry Potter, Auror Draco Malfoy, Potions Master Draco Malfoy, Unspeakable Hermione Granger, Auror Ron Weasley</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/8_teen.html">Link</a></td>
       <td>ministry of magic careers</td>
    </tr>
    <tr>
      <td>10</td>
      <td>Albus Dumbledore Bashing, Ron Weasley Bashing, Good Malfoy Family (Harry Potter), Good Severus Snape, Molly Weasley Bashing</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/9_teen.html">Link</a></td>
       <td>similar to the other groups we saw in explicit/mature; canon divergence/another pov of harry’s story</td>
    </tr>
    <tr>
      <td>11</td>
      <td>Christmas, Christmas Fluff, Christmas Party, 25 Days of Harry and Draco, Winter</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/10_teen.html">Link</a></td>
       <td>christmas</td>
    </tr>
    <tr>
      <td>12</td>
      <td>Podfic, Audio Format: MP3, Audio Format: Streaming, Podfic Length: 0-10 Minutes, Audio Format: M4B</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/11_teen.html">Link</a></td>
       <td>podfics</td>
    </tr>
    <tr>
      <td>13</td>
      <td>Gay Draco Malfoy, Lesbian Pansy Parkinson, Bisexual Harry Potter, Coming Out, Person of Color Harry Potter</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/explicit/12_teen.html">Link</a></td>
       <td>sexuality; i haven’t read that many person of color harry fics so i can’t really comment on that</td>
    </tr>
    <tr>
      <td>14*</td>
      <td>Alternate Universe – Muggle, Alternate Universe – Coffee Shops & Cafes, Alternate Universe – High School, Meet-Cute, Alternate Universe – College/University</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/13_teen.html">Link</a></td>
       <td>muggle AU</td>
    </tr>
    <tr>
      <td>15*</td>
      <td>Art, Digital Art, Fanart, Comic, Fandom Kombat 2020</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/14_teen.html">Link</a></td>
       <td>art stuff</td>
    </tr>
    <tr>
      <td>16*</td>
      <td>Professor Harry Potter, Professor Draco Malfoy, Defense Against the Dark Arts Professor Harry Potter, Professor Neville Longbottom</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/15_teen.html">Link</a></td>
       <td>the boys as profs</td>
    </tr>
    <tr>
      <td>17*</td>
      <td>Veela Draco Malfoy, Creature Fic, Creature Inheritance, Veela Mates</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/16_teen.html">Link</a></td>
       <td>creature inheritance</td>
    </tr>
    <tr>
      <td>18*</td>
      <td>Alternate Universe – Time Travel, Time Travel, Time Travel Fix-It</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/17_teen.html">Link</a></td>
       <td>time travel! time turner fics are bae</td>
    </tr>
    <tr>
      <td>19*</td>
      <td>Top Draco Malfoy, Bottom Harry Potter, Bottom Harry</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/18_teen.html">Link</a></td>
       <td>top draco gang</td>
    </tr>
    <tr>
      <td>20*</td>
      <td>Bottom Draco Malfoy, Top Harry, Top Harry Potter</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/19_teen.html">Link</a></td>
       <td>bottom draco gang</td>
    </tr>
    <tr>
      <td>21*</td>
      <td>Soulmate-Identifying Marks, Soulmates, Alternate Universe - Soulmates</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/20_teen.html">Link</a></td>
       <td>soulmates AU</td>
    </tr>
    <tr>
      <td>22*</td>
      <td>Homophobia, Internalized Homophobia, Homophobic Language</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/21_teen.html">Link</a></td>
       <td>homophobia</td>
    </tr>
    <tr>
      <td>23*</td>
      <td>Ficlet, Facebook: The Pen15 is Mightier, Community: hogwarts365</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/22_teen.html">Link</a></td>
       <td> </td>
    </tr>
    <tr>
      <td>24*</td>
      <td>Hogwarts Fourth Year, Yule Ball (Harry Potter), Triwizard Tournament</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/23_teen.html">Link</a></td>
       <td>book four</td>
    </tr>
    <tr>
      <td>25*</td>
      <td>Black Hermione Granger, Indian Harry Potter, Desi Harry Potter</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/24_teen.html">Link</a></td>
       <td>persons of color representations</td>
    </tr>
    <tr>
      <td>26*</td>
      <td>Trans Female Character, Trans Character, Trans Draco Malfoy</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/25_teen.html">Link</a></td>
       <td>trans representations</td>
    </tr>
    <tr>
      <td>27*</td>
      <td>Remus Lupin Lives, Sirius Black Lives</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/26_teen.html">Link</a></td>
       <td> </td>
    </tr>
    <tr>
      <td>28*</td>
      <td>Community: hp_drizzle, HP Drizzle Fest 2019</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/27_teen.html">Link</a></td>
       <td></td>
    </tr>
    <tr>
      <td>29*</td>
      <td>Halloween, Halloween Costumes</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/28_teen.html">Link</a></td>
       <td>halloween</td>
    </tr>
    <tr>
      <td>30*</td>
      <td>Lily Evans Potter Lives, James Potter Lives</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/29_teen.html">Link</a></td>
       <td>no comments but harry totally deserves happiness and a family</td>
    </tr>
    <tr>
      <td>31*</td>
      <td>Drunken Confessions, Drunkenness</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/30_teen.html">Link</a></td>
       <td>drunk</td>
    </tr>
    <tr>
      <td>32*</td>
      <td>Ron Weasley is a Good Friend, Hermione Granger is a Good Friend</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/31_teen.html">Link</a></td>
       <td>we stan good friends</td>
    </tr>
    <tr>
      <td>33*</td>
      <td>Epistolary, Letters</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/32_teen.html">Link</a></td>
       <td>letters</td>
    </tr>
    <tr>
      <td>34*</td>
      <td>LGBTQ Themes, LGBTQ Character</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/33_teen.html">Link</a></td>
       <td> </td>
    </tr>
    <tr>
      <td>35*</td>
      <td>Advent Calendar, Community: hd_seasons</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/34_teen.html">Link</a></td>
       <td></td>
    </tr>
    <tr>
      <td>36*</td>
      <td>Draco Malfoy Loves Harry Potter, Harry Potter Loves Draco Malfoy</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/35_teen.html">Link</a></td>
       <td>these tags (together) make me happy</td>
    </tr>
    <tr>
      <td>37*</td>
      <td>Creature Harry Potter, Creature Draco Malfoy</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/teen/36_teen.html">Link</a></td>
       <td>not sure why this is separate from creature inheritance</td>
    </tr>
  </table>
</div>

</body>
</html>

<br>
## Gen tag network
<b>Modularity = .390</b><br>

### Full network
[Link](/visuals/drarry/01_tagnetworks/gen/full_gen.html)<br>

### Networks by Louvain group
Asterisks* denote a network with 5 or less nodes.<br><br>

<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
</head>
<body>

<div style="overflow-x:auto;">
  <table>
    <tr>
      <th></th>
      <th>Example tags</th>
      <th>Link to network</th>
     <th>Comments</th>
    </tr>
    <tr>
      <td>1</td>
      <td>Harry Potter Epilogue What Epilogue | EWE, Established Relationship, Domestic Fluff, Post-Hogwarts, Light Angst</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/0_gen.html">Link</a></td>
      <td>non canon compliance, post-war?</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Humor, Romance, One Shot, Drama, Mpreg</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/1_gen.html">Link</a></td>
       <td>general story themes?</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Hogwarts Eighth Year, First Kiss, Draco Malfoy Redemption, Getting Together, Secret Relationship</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/2_gen.html">Link</a></td>
       <td>post-war getting together</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Angst, Hurt/Comfort, Hogwarts Sixth Year, Character Death, Unrequited Love</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/3_gen.html">Link</a></td>
       <td>pain and hurt</td>
    </tr>
    <tr>
      <td>5</td>
      <td>Drarry, Drabble, Short & Sweet, Don’t copy to another site, Drarry Discord Writers Corner Drabble Challenge</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/4_gen.html">Link</a></td>
       <td>soft drabbles</td>
    </tr>
    <tr>
      <td>6</td>
      <td>Christmas, Christmas Fluff, 25 Days of Harry and Draco, Mistletoe, Snow</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/5_gen.html">Link</a></td>
       <td>christmas</td>
    </tr>
    <tr>
      <td>7</td>
      <td>POV Harry Potter, POV Draco Malfoy, Ficlet, Good Draco Malfoy, Facebook: The Pen15 is Mightier</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/6_gen.html">Link</a></td>
       <td>not too sure about this one</td>
    </tr>
    <tr>
      <td>8</td>
      <td>Friendship, Crack, Inspired By Tumblr, Crack Treated Seriously, Wordcount: 100-500</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/7_gen.html">Link</a></td>
       <td>crack</td>
    </tr>
    <tr>
      <td>9</td>
      <td>Fanart, Comic, Art, Digital Art, H/D Erised 2020</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/8_gen.html">Link</a></td>
       <td>fanart</td>
    </tr>
    <tr>
      <td>10</td>
      <td>Auror Partners, Auror Draco Malfoy, Healer Draco Malfoy, Auror Harry Potter, St Mungo’s Hospital</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/9_gen.html">Link</a></td>
       <td>auror/healer careers</td>
    </tr>
    <tr>
      <td>11*</td>
      <td>Cute, Happy Ending, Happy, Funny, Love</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/10_gen.html">Link</a></td>
       <td>fluff tags</td>
    </tr>
    <tr>
      <td>12*</td>
      <td>Podfic, Audio Format: MP3, Audio Format: Streaming, Podfic Length: 0-10 Minutes, Podfic & Podficced Works</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/11_gen.html">Link</a></td>
       <td>podfics</td>
    </tr>
    <tr>
      <td>13*</td>
      <td>Boys In Love, 100 Ways to Say I Love You Writing Challenge, So Married, Boys Kissing</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/12_gen.html">Link</a></td>
       <td>more fluff tags?</td>
    </tr>
    <tr>
      <td>14*</td>
      <td>Enemies to Friends to Lovers, Friends to Lovers, Enemies to Friends, Enemies to Lovers</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/13_gen.html">Link</a></td>
       <td>enemy canon to lover fanon</td>
    </tr>
    <tr>
      <td>15*</td>
      <td>Gay Draco Malfoy, Gay Harry Potter, Bisexual Harry Potter</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/14_gen.html">Link</a></td>
       <td>sexuality</td>
    </tr>
    <tr>
      <td>16*</td>
      <td>Alternate Universe – Modern Setting, Alternate Universe – Muggle, Alternate Universe – Non-Magical</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/15_gen.html">Link</a></td>
       <td>muggle AU</td>
    </tr>
    <tr>
      <td>17*</td>
      <td>Soulmate-Identifying Marks, Alternate Universe – Soulmates, Soulmates</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/16_gen.html">Link</a></td>
       <td>soulmates AU</td>
    </tr>
    <tr>
      <td>18*</td>
      <td>Yule Ball (Harry Potter), Dancing, Hogwarts Fourth Year</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/17_gen.html">Link</a></td>
       <td>fourth year</td>
    </tr>
    <tr>
      <td>19*</td>
      <td>Podfic Welcome, Microfic, Tumblr: drarrymicrofic</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/18_gen.html">Link</a></td>
       <td> </td>
    </tr>
    <tr>
      <td>20*</td>
      <td>Community: hd_seasons, Advent Calendar</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/19_gen.html">Link</a></td>
       <td> </td>
    </tr>
    <tr>
      <td>21*</td>
      <td>Married Couple, Community: slythindor100</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/20_gen.html">Link</a></td>
       <td></td>
    </tr>
    <tr>
      <td>22*</td>
      <td>Valentine’s Day, Valentine’s Day Fluff</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/21_gen.html">Link</a></td>
       <td>valentine’s</td>
    </tr>
    <tr>
      <td>23*</td>
      <td>Family Fluff, Family Feels</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/22_gen.html">Link</a></td>
       <td>family</td>
    </tr>
    <tr>
      <td>24*</td>
      <td>Book 4: Harry Potter and the Goblet of Fire, Triwizard Tournament</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/23_gen.html">Link</a></td>
       <td>triwizard</td>
    </tr>
    <tr>
      <td>25*</td>
      <td>Love Confessions, Declarations of Love</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/24_gen.html">Link</a></td>
       <td>love confessions</td>
    </tr>
    <tr>
      <td>26*</td>
      <td>Mutual Pining, Pining</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/25_gen.html">Link</a></td>
       <td>pining</td>
    </tr>
    <tr>
      <td>27*</td>
      <td>Professor Draco Malfoy, Professor Harry Potter</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/26_gen.html">Link</a></td>
       <td>boys as profs</td>
    </tr>
    <tr>
      <td>28*</td>
      <td>New Year’s Eve, New Year’s Kiss</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/27_gen.html">Link</a></td>
       <td>new year’s</td>
    </tr>
    <tr>
      <td>29*</td>
      <td>Halloween, Halloween Costumes</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/28_gen.html">Link</a></td>
       <td>halloween</td>
    </tr>
    <tr>
      <td>30*</td>
      <td>Old Fic, reposted</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/29_gen.html">Link</a></td>
       <td>reposting old stuff</td>
    </tr>
    <tr>
      <td>31*</td>
      <td>Slytherin, Gryffindor</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/30_gen.html">Link</a></td>
       <td></td>
    </tr>
    <tr>
      <td>32*</td>
      <td>Remus Lupin Lives, Sirius Black Lives</td>
      <td><a href="dru-r.github.io/ao3-dbh-analysis/ visuals/drarry/01_tagnetworks/gen/31_gen.html">Link</a></td>
       <td> </td>
    </tr>
  </table>
</div>

</body>
</html>

<br>
## Conclusion
The results in the end were rather coarse. But across the ratings, we do see the common themes which pop up in many Drarry fics clustering somewhat together. To name a couple: immediate post-war redemptions/getting together, post-Hogwarts fumbling to find their way together, canon-divergence/EWE AUs, muggle AUs, mpreg, the ‘good’ side actually being manipulative, creature inheritance, season/holiday fics, dark Harry, mental health/abuse, soulmate AUs, professors Harry/Draco, genderbending. <br><br>
For each of the ratings, we also see some slightly more specific to them: <br>
1) In explicit, we see dirty talk/rough sex, BDSM, A/B/O, threesomes, torture, and more specific descriptions of bottom/top Harry/Draco. <br>
2) In mature, we also see A/B/O, and a group specifically for mental health issues. <br>
3) In teen fics, there’re groups for the Yule Ball specifically, letters, and drunken confessions. <br>
4) Multiple groups in gen fic overall appear to characterise the rating as having a fair amount of fluff, humour, and softness. <br><br>

There are still many other things that intrigue me about the tropes in Drarry – and which I hope to be able to explore (but am still unsure of at the moment; mainly because I’m still thinking about how/if it is possible). Things like how do tropes evolve over time, how do some tropes arise from others, how to catch the patterning of the rise/fall of popularity of tropes, and how to ‘retrieve’ tropes from the fic text itself to get a more granular view of what I’ve tried to do here. 47k+ fics is not completely unreasonable to (very slowly) scrape and test these ideas but for now, I’ll be returning to work on AO3’s tag data dump first.

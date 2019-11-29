# Differences in word use between AO3 D:BH fics of different ratings
Do mature-rated fics use different language from explicit-rated fics? What words are generally used more in teen-rated fics versus mature-rated fics? <br>
<br>
We can already guess how explicit fics may differ from the rest (sMuT) so my interest in running this analysis was really to see:
1) What differentiates the general audience/teen/mature fics from each other, and 
2) What differentiates mature/explicit fics (since mature-rated fics may also make references to sex/violence). <br>
<br>
<b>Note: I dropped Not Rated fics for this analysis, leaving 12647 fics for analysis. Full blog post on preprocessing and other details here. (link details later).</b> <br>
<br>
To recap AO3's rating system, taken from [here](https://archiveofourown.org/faq/tutorial-posting-a-work-on-ao3?language_id=en#pwtrating):<br>
- General Audiences: The content is unlikely to be disturbing to anyone, and is suitable for all ages. <br>
- Teen And Up Audiences: The content may be inappropriate for audiences under 13. <br>
- Mature: The content contains adult themes (sex, violence, etc) that aren't as graphic as explicit-rated content.<br>
- Explicit: The content contains explicit adult themes, such as porn, graphic violence, etc.<br>

[Click here to skip to the results](#results).

## Analysis done
I was admittedly not very sure how to proceed! Based on past readings, log-likelihood ratio tests and chi-square tests seem to be the tests of choice for comparing whether certain words occur more often in one corpus versus another (e.g. men vs women).<br>
<br>
However, I recently came across [this interesting paper](https://users.ics.aalto.fi/lijffijt/articles/lijffijt2015a.pdf) which argues for the suitability of using other tests instead (i.e., t-tests, Mann-Whitney U-tests, bootstrap tests). The Mann-Whitney U-test is commonly thought of as the non-parametric equivalent of the t-test (very loosely put). Given that I have 4 groups (4 ratings) instead of 2, however, I went with what's commonly called the non-parametric equivalent (again, very loosely put!) of the ANOVA - the <b> [Kruskal-Wallis test](https://en.wikipedia.org/wiki/Kruskal%E2%80%93Wallis_one-way_analysis_of_variance)</b>. I discuss that and the corrections for multiple comparisons in my blog post. <br>
<br>
What I would like to clarify here is that <b> the Kruskal-Wallis does not test for differences in group means or medians</b>. (If you want to assume it's testing for medians, you have to assume that the distribution across all your groups are identical). Basically, K-W is a rank-based test. <br>
<br>
In this scenario, we'd rank all 12647 fics by their length-corrected (so we don't have a bias towards longer fics) frequencies of perhaps the word "love". So the fic that's used the word "love" least is given the rank 1, the fic that's used it the most 12647, and everyone else in between. Then we sum the ranks within each of the 4 groups and compare the average rank from each group to test for statistical significance.

## Results
I wasn't sure how best to show the results, so I went with a dot graph displaying the mean ranks for each of the ratings. <br>
<br>
<b>Note:</b><br>
- I limited each graph to the top-200 words based on the H-statistic (smallest to largest at the bottom). This statistic can be converted to an effect size (eg. eta-squared), but I didn't do it here (there's enough information in the charts for you to calculate it on your own if you'd like, though). There were many more significant words for the explicit/mature charts, but it would be pretty unwieldy to show them all. <br>
- Please hover over the dots to get info on mean rank for that rating, the sample size for that rating, etc! <br>
### 1. Words generally used the most by mature fics
Note: I'm only showing words that were significantly different between mature/explicit fics. I wanted to know what differentiated these two rather similar ratings.<br>
<b>[Click here for the interactive chart](/docs/visuals/05_kw/mature_n1.html).</b>
#### Key takeaways from chart
1) Mature fics generally have a focus on more aggressive words than explicit fics (e.g. blood, bitch, broken).
2) Even teen fics generally use words that suggest aggression/harm more than explicit fics (e.g. hurt, cases, stress, died, shoot).
So while AO3's explicit rating does encapsulate graphic violence, it does seem the D:BH explicit fics centre more around the smut aspect than gore/violence/etc).
3) While mature fics generally use female pronouns (she/her) and the collective 'people' the most, explicit fics use them the least.
Not entirely surprising given all the M/M ships in D:BH, but it was nice that the test picked it up.
### 2. Words generally used the most by explicit fics
Note: Again, I'm only showing words that were significantly different between mature/explicit fics.<br>
<b>[Click here for the interactive chart](/docs/visuals/05_kw/explicit_n1.html).</b>
#### Key takeaways from chart
1) Really clean patterning of mean ranks! The self-rating system seems to work pretty well (??). Sexual terms are far and away the most used by explicit fics, suggesting a strong focus on smut.
2) Teen and gen fics are generally similar in their lack of usage of smut-suggestive terms like nipples, prostate, lust, etc.
### 3. Words generally used the most by teen fics
Note: This chart isn't as big as the first two because the number of words were teen fics ranked the first in mean ranks just wasn't as large.<br>
<b>[Click here for the interactive chart](/docs/visuals/05_kw/teen_n1.html).</b>
#### Key takeaways from chart
1) Teen fics generally use certain function words the most (e.g. pronouns, common verbs like am/be).
I'm not really sure why this is the case, but it's interesting to see that explicit fics have the lowest mean ranks for some of these terms. My uneducated guess is that these represent some different emphases in story construction - but these are just words out-of-context (i.e., don't read too much into them)!
### 4. Words generally used the most by gen fics
Note: Again, this chart is tiny because there just weren't a lot of words where gen fics ranked the top in mean ranks.<br>
<b>[Click here for the interactive chart](/docs/visuals/05_kw/ga_n1.html).</b>
#### Key takeaways from chart
Not much really. From the overall analysis, it seems like gen fics are just characterised by an <i>absence</i> of stuff - which was quite disappointing for me. But understandable at the same time, as this analysis was rather crude. This is something I'd like to work more on, perhaps by incorporating some information about story structure or syntax. 

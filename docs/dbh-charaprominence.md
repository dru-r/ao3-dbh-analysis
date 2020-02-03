# Comparison of character prominence between the actual game and fandom
If you're here from my Tumblr post and looking for the interactive versions of the charts, here they are!<br>
[Pie chart of game dialogue share](/visuals/09_prominence/dbhgame_dialogpie.html) | [Pie chart of fic tag share](/visuals/09_prominence/dbhfic_charatagprops.html) | [Bar chart comparing percentages from game/fic](/visuals/09_prominence/dbhgame_vs_fic.html)<br> 
<br>
<b>If you aren't from Tumblr, do read on first before viewing the charts</b>. Usually I like to dump all the methodology in a separate Tumblr post and drop a link here, but I think for this analysis it is best presented together with the methods since I made a fair bit of assumptions. Most of the writing here reprinted from my Tumblr post.<br><br>
The question that sparked this little analysis was quite simple: which characters gained prominence moving from canon to fics, and which characters actually lost prominence? I won't pretend I had a compelling scientific reason for doing this (as with most of the other stuff I've done on here); I just wonder a lot about (what some might consider rather pointless) things in general.<br>
## Content
1) [Considerations](#considerations) <br>
2) [Dialogue share from the actual game](#dialogue-share-from-the-actual-game)<br>
3) [Share of character tags from AO3 fics](#share-of-character-tags-from-fics)<br>
4) [Final results](#final-results)
5) Extra: [A character cooccurence network built from AO3 fics](#a-character-cooccurence-network-built-from-fics)
<br><br>
## Considerations
1) What is prominence? There are many ways to conceptualise the prominence of a character - how many times did they appear (and what counts as an appearance; just walking across the street, or actually being the focus of action)? How much screen-time did they get? How many lines did they say? How many times their name appeared or they were referred to? Maybe even how much influence they had over events? And how can we capture it as a measurable construct?<br>
2) If we’ve got an answer for (1), how do we compare that between different mediums? D:BH is a fully-fledged game with heavy imagery and fics are mainly just plain text. <br>
<br>
After thinking about the data I had in hand (and the assumptions I needed to make), I went with very simplistic operationalisations of prominence. <b>For the actual game, I relied on the dialogue transcriptions from the [Detroit: Become Text project](https://detroitbecometext.github.io/chapters). For fics, I relied on the character tags provided by the AO3 authors.</b><br>
<br>
I'll talk more about the assumptions I made in the respective sections.<br>

## Dialogue share from the actual game
Dataset: All game chapters transcribed by the awesome Detroit: Become Text project. Note that it is mostly dialogue that has been transcribed.<br>
### Preprocessing and assumptions
Very clean HTML files so I just wrote some code to pull out character names and count the number of lines each had. <br>
<br>
<b>Assumption 1: </b>Share of dialogue is indicative of character prominence in the game. I decided on this mainly due to being limited by the information I had (mostly transcribed dialogue only) and also because D:BH is a very conversation-heavy game. Note this means, however, characters that appear but don't speak (e.g. Sumo, RK900) are considered to have zero prominence.<br><br>
<b>Assumption 2</b>: Sometimes characters might be interchangeable for certain lines, e.g. Josh <i>or</i> Simon can tell Markus, “<i>Be careful, Markus. Our people need you.</i>” I chose to drop these lines and not assign them to any character’s count since there were only 15 of them in the whole transcription.<br><br>
<b>Assumption 3</b>: The game has multiple scenarios based on your choices. I chose not to distinguish between them, taking the whole transcription as a long text document. I thought that if the writers decided a character was important enough to have/be in several variants of the scenario (e.g. Connor’s multiple endings versus the unnamed android Markus picked up paint from), I should not discount that.<br>
<br>
Following this, I selected 40 named characters (i.e., no random policeman/passer-bys) for visualisation and comparison. These 40 characters together had 3745 transcribed lines.<br>
### Results<br>
![image](/visuals/09_prominence/canon.png)<br>
[Click here for the interactive version - with numbers, sample dialogue](/visuals/09_prominence/dbhgame_dialogpie.html)<br>
<br>
<b>Note the percentage is calculated from the lines of these 40 characters only</b> (i.e., does not cover dialogue counts of unnamed policemen, unnamed deviants, etc). Connor, Kara, and Markus are the three main playable characters, so it's no wonder they take up almost 50% of the chart. North has more lines than the rest of the Jericho members since there are scenarios where she takes Markus' place. Fan favourites like Gavin actually hold only a very little slice of this dialogue pie.<br>

## Share of character tags from fics
Dataset is my usual pool of 13k+ fics (I need to update this sometime!).<br>
### Preprocessing and assumptions
I collated all the tags that fell under the Character category (61333 tags). I had to do a fair bit of manual cleaning as usual due to misspellings/different ways to tag a character.<br><br>
<b>Assumption:</b> Picking out dialogue lines from fic and <b>attributing it correctly to characters</b> is an extremely difficult task. So, I chose tags - I assumed that characters that are important or at the very least more than a one-liner would receive a tag. At the same time, I assumed that characters that are really just one-liner appearances (like “<i>He saw Nines walk across the room.” </i>with zero mention of Nines in the rest of the fic) would <i>not</i> get tagged. <br><br>
Clearly this is not foolproof since everyone has different ideas of what constitutes a character that should be tagged, but it’s what I worked with (otherwise I would have to read and check every fic - and even then the final decision of 'was this character important enough to warrant a tag' is pretty subjective). Note:<br><br>
1) Ambiguous tags like “<i>everyone</i>” were not assigned to any character.<br>
2) Tags that mentioned multiple characters (e.g “<i>mentioned North and Josh”</i>) or ships were also not assigned to any character. I assumed if the character was significant enough (i.e., not just lurking around the background saying nothing), they would have warranted their own tag.<br>
3) Tags that were in the style of “<i>Connor (mentioned)</i>” were <b>still added to their respective characters</b>. Again, we all have varying ideas of what a “mention” actually means, so I decided to be less stringent and more inclusive here.<br>
4) Tags for ‘<i>Jericho’  </i>and<i> ‘Jericrew’, </i>etc - I added 0.25 to the counts of Jericho members (Markus, North, Simon, and Josh) each time such a tag appeared. Whether I did that or not probably wouldn’t have drastically changed the results though, since there were only 87 Jericho-related character tags.<br><br>
I then pulled out the tags referring to the same 40 characters I had looked at for the game dialogue and made a pie chart. These 40 characters together received 53274 tags.<br>
### Results<br>
![image](/visuals/09_prominence/fandom.png)<br>
[Click here for the interactive version - better view of numbers](/visuals/09_prominence/dbhfic_charatagprops.html)<br>
<br>
<b> Note the percentage is calculated from the total number of times these 40 characters were tagged</b> (e.g., does not include tag counts for own characters/OCs - which were tagged quite a bit as well). Connor holds on to his share in the AO3 fic fandom and there are huge jumps from Gavin and RK900. A number of DPD members (Tina, Fowler, Chris) also seem to have slightly bigger slices of the pie in fandom.<br><br>
Trying to compare two pie-charts (especially those little slivers) is probably living hell though, so I put the information from both into a barchart.<br.

## Final results<br>
![image](/visuals/09_prominence/canonvsfandom_static.png)<br>
[Click here for the interactive version - better view of numbers](/visuals/09_prominence//visuals/09_prominence/dbhgame_vs_fic.html)<br><br>
I sorted the characters so the leftmost ones are the ones that lost the most prominence moving from canon to fandom and the rightmost ones are the ones that gained the most. The middle ones are well, just middling - not much change. Obviously the percentages are not one-on-one comparable since prominence had to be operationalised differently between the two sources, but I think it does capture a trend. Of the main playables, only Connor sees a slight gain (not sure how much more he can gain to be honest, such a dominant character in canon and fandom!) - Markus and Kara are much less emphasised than in canon. Perhaps because Connor is such a popular character, his DPD coworkers end up getting a boost too (since they may be more likely to appear when he does in fics?).<br>

## A character cooccurence network built from fics
I didn't touch on this in my Tumblr post (since I felt it didn't really add to the analysis), but since I had gone out of my way to clean 61333 tags, I decided to [make this little graph](/visuals/09_prominence/ao3_dbhchara_cooccur_filtered.html).<br>
### Reading the graph
This graph basically reflects how frequently characters have been tagged together on the same fic - so, nodes are characters and they are linked if they have been tagged together on one fic. Links are weighted by the number of times a pair of characters have been tagged together on fics.<br><br>
<b>Link thickness and colour</b>: Links are thicker and brighter if a pair of characters have been tagged together on fics more often.<br>
<b>Node size and colour</b>: Nodes are sized by weighted degree. Brighter nodes are those with greater weighted degree.<br>
Hover over nodes and links to get more information!<br><br>
Note that all the information reflected in the graph (about tag count, top 5 characters that appear with said character, number of unique characters said character has appeared with in fics) were calculated from the initial graph of all characters. However, the displayed interactive graph is a condensed version. The initial unfiltered graph looked like this:<br><br>
![image](/visuals/09_prominence/hairball.png)<br>
Big oof.<br><br>
So I used [Serrano et al.'s (2009) disparity filter](https://www.pnas.org/content/106/16/6483.short) at α=.05 to filter the graph. Basically the disparity filter purports to preserve important connections in the network via testing for statistical significance in each link of the network (i.e., the link likely did not occur by random chance). As we can see from the final interactive graph, it cleans up a lot of the miscellaneous links and makes reading it much easier.<br><br>
For more networks, I also have one for ships up [here](https://dru-r.github.io/ao3-dbh-analysis/dbh-shipnetwork.html).

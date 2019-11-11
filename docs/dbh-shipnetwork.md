# An interactive visualisation of ships in the AO3 Detroit: Become Human fandom
Ever took time out of your life to ponder pointless questions like:
- What percentage of fics shipping RK900 with the reader are explicit? <br>
- Who're the top characters shipped with Ralph? <br>
- How much naughty time does Connor potentially get up to in fics where he's in a ship(s)? (i.e. percentage of fics with Connor in a ship(s) that are explicit) <br>
- Who're the characters that get shipped with the widest variety of characters? (hint: it's probably who you think it is) <br>

Well, then, this graph is just for you!<br>

Explore the relations between the characters in the DBH fic fandom, get some insights on the ships involving your favourite character(s) in this interactive network of DBH ships!

This visualisation was created with the help of the awesome library pyvis.

Full blog post detailing this graph's creation [here](https://program-800.tumblr.com/post/188743310956/exploring-dbh-fics-part-2)

# ACCESS THE GRAPH: [click here for the interactive visualisation!](ao3_dbhships.html)

## Okay, how do I read this graph?
#### Info when hovering over a character node:
Hovering over a character's node gives you information on:
- The percentage of fics with them in a ship(s) that are explicit
- The top 5 most common characters they're shipped with

#### Node size: 
The bigger the character's node, the more characters that character has been shipped with.

#### Node colour:
- White: Most of the fics shipping the character are not explicit (~10% and below; 35th quantile and below)
- Orange: A relatively moderate percentage of fics shipping the character are explicit (~10% to ~30%, 35th to 65th quantile)
- Red: A relatively greater percentage of the fics shipping the character are explicit (~30% and above, 65th quantile and above)

#### Info when hovering over a link between two characters:
Hovering over a link between two characters gives you information on:
- The percentage of fics shipping these 2 characters that are explicit.

#### Link thickness:
The thicker the link between two characters, the more times they've been shipped together across all the fics.

#### Link colour:
- White: None of the fics shipping the 2 characters are explicit (0%, ~40th quantile).
- Orange: A relatively moderate percentage of the fics shipping the 2 characters are explicit (0 to ~38%, between ~40th to 70th quantile)
- Red: A relatively greater percentage of the fics shipping the 2 characters are explicit (~38% and above, 70th quantile and above)

### Edit logs:
05/11/19: Fixed some dead links.

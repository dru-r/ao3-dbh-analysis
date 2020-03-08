# An interactive visualisation of character cooccurence across AO3 Detroit: Become Human fics
I created this  network as a summary of the dataset for myself, but decided to release it here since it might be interesting for others to view as well. The network is meant to be a bird's eye view of character appearance stats across the D:BH fandom. Specifically, it summarises: <br>

1) The most common rating the character typically appears in<br>
2) How many unique characters the character has appeared with<br>
3) The top 5 characters that appear with the character<br>
4) How often the character is shipped whenever they appear<br>
5) The most common rating of the character’s shipfics, and <br>
6) How many fics a pair of characters have appeared in together<br>
7) The most common rating a pair of characters typically appears in together<br>
8) How often a pair of characters are shipped together whenever they appear<br>
9) The most common rating of a pair of characters' shipfics<br>

Full blog post detailing the network's creation [here](https://program-800.tumblr.com/post/612029495975821312/exploring-dbh-fics-part-10).<br>

<b>[Access the network here!](/visuals/10_chara_cooccur/ao3_dbhchara_cooccur_v2_filter.html)</b> <br>

If you are interested in just ships specifically, [do visit my earlier work on it](dbh-shipnetwork.md).

## How do I read this graph? <br>
### Node qualities
Nodes are characters. <br><br>
<b>Node size</b>: The larger a character node, the more unique characters the character has appeared with.<br>
<b>Node shape</b>: <br>
Star-shaped nodes indicate characters that are shipped in 50% or more fics that they appear in. <br>
Diamond-shaped nodes indicate characters that are shipped in 25% to 50% of the fics they appear in.<br>
Regular circle-shaped nodes are characters that are shipped in below 25% of the fics they appear in. <br>
<b>Node colour</b>: Node colour is determined by the fic rating the character typically appears in. <br>
Colour reference: grey = Not Rated, green = Gen, blue = Teen, orange = Mature, red = Explicit.<br>
<br>
<b>Hovering over a node</b> gives you the following info:<br>
- The most common rating the character typically appears in<br>
- How many unique characters the character has appeared with<br>
- The top 5 characters that appear with the character<br>
- How often the character is shipped whenever they appear<br>
- The most common rating of the character’s shipfics (e.g. <i>28.97% of fics shipping Connor are Explicit</i>; the top rating for Connor shipfics is Explicit)<br><br>

### Link qualities
Characters are linked if they have appeared in at least one fic together. <br><br>
<b>Link thickness</b>: The thicker the link, the more often that pair of characters has appeared together.<br>
<b>Link colour</b>: Link colour is determined by the fic rating the character pair typically appears in. The colour scheme follows that of the character nodes.<br>
<br>
<b>Hovering over a link between two characters</b> gives you the following info:<br>
- How many fics a pair of characters have appeared in together<br>
- The most common rating a pair of characters typically appears in together<br>
- How often a pair of characters are shipped together whenever they appear<br>
- The most common rating of a pair of characters' shipfics (e.g. <i>83.33% of fics that ship Kamski and ST200 are Explicit</i>; the top rating for Kamski/ST200 shipfics is Explicit)<br>

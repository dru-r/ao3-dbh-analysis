# (A partial attempt at) automatically finding similar summaries (AO3 D:BH fics)
A self-indulgent application of Word Mover's Distance to my dataset. (Very sparse) details of process covered in a blog post [here](insert link later). <br>
<br>
Sometime back, I [trained a word2vec model on my dataset of D:BH fics](dbh-w2vtrial.md). I've been wanting to do something useful with it and recently came across [Word Mover's Distance (WMD)](https://markroxor.github.io/gensim/static/notebooks/WMD_tutorial.html), so I thought - why the hell not, I guess. Instead of relying solely on bag-of-words counts for assessing document similarity, WMD also taps on the word embeddings from the word2vec model. In other words, even though two documents might not use the same words, similarity can still be assessed via the distance needed to 'travel' between their word embeddings.<br>
<br>
I only managed to run WMD on about a 1000~ summaries before I stopped it (as the Gensim tutorial mentions, the queries take longer as the text gets longer). For reference I had about 12,000 summaries I wanted to go through. The results are interesting, but I'm not satisfied - likely, I didn't preprocess well enough, my word2vec model is probably suspect as well, and finding some way to include other data (i.e., author-provided tags, warnings, etc) will definitely strengthen the results. <br>
<br>
Nonetheless, I present the WIP results <b>[here](/visuals/11_wmdtrial/ao3_dbhsumms_partial_wmd.html)</b>, as an interactive pyvis network as usual.<br>
<br>
This graph is very simple, nothing much:<br>
1. Nodes are summaries, coloured by their ratings. Red = explicit, orange = mature, pink = teen, white = gen. <br>
2. Nodes are linked if the respective summaries have at least .55 similarity with each other. <br>
3. Thicker edges means the similarity between the two summaries was calculated as higher.

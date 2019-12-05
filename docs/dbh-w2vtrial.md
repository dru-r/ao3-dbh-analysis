# Finding similar words based on word usage patterns in AO3 D:BH fics (word2vec)
An application of word2vec to my corpus of AO3 D:BH fics. <b>Full details of preprocessing and training covered [here](insert link later).</b><br>

While there are pre-trained word vectors out there built off far more massive datasets (like Google's!), the datasets are typically rather different from fanfics (e.g. Google News). I think this site [provides a demo for Google's](https://bionlp-www.utu.fi/wv_demo) - you can use it to see how the similar words may differ between that model and this one.<br>

Since the idea behind word2vec is that words which share similar contexts should be similar in meaning*, I'd imagine using pre-trained embeddings may not fare quite as well for fics if we're interested in their nuances. While it'll probably work for the bulk of generic words (e.g. 'happy', 'joyful'), some subtleties arising from fandom might not be caught. For example, 'alpha'. Searching for it in the demo gives 'betas' and 'omega' in the top 10 words, but it's obviously not capturing the same idea as A/B/O! We see 'standard_deviation', 'gamma', 'ligand' - which obviously indicates that 'alpha' is captured in the mathematical sense. In this model trained on D:BH fics, we see 'mate' and 'werewolf' popping up within the top 10 words instead. <br>

Qualitatively, the model produces a visualisation and word similarities that do make sense; words that should be similar to each other have smaller distances to each other. Still, given that (1) the results are affected by hyperparameter choice, as with many algorithms, and (2) that an extrinsic task (e.g. classifying text) might give a better indication of how <i>useful</i> the learned word2vec embeddings are - and I have none thought of currently - I recommend that this visualisation be taken only for what it is - an exploratory tool for fun. <br>

<sub>*note that this implies that similar words =/= necessarily synonyms; e.g. 'happy' and its antonym 'unhappy' would still be considered similar under this definition. As I used the skip-gram word2vec model, the model is actually learning how to predict the context words given an input word (e.g. 'revolution'). Intuitively, 'happy' and 'unhappy' would have similar surrounding context words despite their opposing meanings.</sub><br>

## Visualisation<br>
<b>Click here for the [3D visualisation](https://dru-r.github.io/w2v-embedding-projector/) of the embeddings of 18,733 words. Works better in desktop (Chrome) browsers. Note</b>:<br>
1) Click on State 0 (under bookmarks) to load the saved 3D UMAP projection.<br>
2) Works better in Chrome. I can't load the bookmark on Firefox for some reason.<br>
3) Please search for 'toaster'.<br>

### Visualisation details<br>
All credit to tensorflow, I just forked the [projector repo](https://github.com/tensorflow/embedding-projector-standalone) and added my data.<br>
1) Search for a word using the Search bar on the top-right, or click on a word in the visualisation to check out its most similar words (calculated and ordered based on cosine similarity between the word embedding vectors).<br>
2) In the display of most similar words, the number next to each word represents the cosine <i>distance</i> between the word you searched for/clicked on and that word. Cosine distance is just 1-cosine similarity, so smaller distance =  greater similarity.<br>
3) PCA/TSNE/UMAP options (bottom left) are different dimension reduction techniques youu can pick for the visualisation. Each vector was originally 200-dimensions so these techniques just shrink them down into a human-visualisable 2- or 3-dimensions. They each produce [rather different results](https://github.com/lmcinnes/umap_paper_notebooks/blob/master/UMAP%20WordEmbedding%20hundredThousand.ipynb). <br>
Going to be honest - I picked UMAP just because it ran faster on my dataset than TSNE. I know that for TSNE, you can't interpret global structure (e.g. cluster A is far from cluster B doesn't mean cluster A and B are really different) and that the end-visualisation is very dependent on the parameters you pick. UMAP is a really new algorithm that purportedly claims to preserve some semblance of global structure (but cluster distances still aren't directly interpretable). It's still quite blackboxy to me so I need to do more reading. For starters, some discussion [here](https://stats.stackexchange.com/questions/402668/intuitive-explanation-of-how-umap-works-compared-to-t-sne) and [here][(https://pair-code.github.io/understanding-umap).<br>

## Ending notes
This exercise has been a little more self-indulgent - mainly done because I never got the chance to use word2vec in formal work. Like with the LDA post, the results turned out pretty okay, so I decided to share them.<br>
<br>
Unlike LDA however, I'm not as familiar with word2vec and UMAP. Currently I'm still reading up on the actual theory/papers so I may return to edit this write-up in future.<br>

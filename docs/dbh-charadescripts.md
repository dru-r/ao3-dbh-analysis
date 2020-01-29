# Understanding fanon representations of characters from story tags
It's no secret that fanon and canon representations of characters can diverge quite a bit - if you've read any amount of fic, that much is clear. This divergence fascinates me <i>a ton</i> and was one of the driving factors for me to pick up programming and text analysis. Why is there this divergence? Why are certain qualities ascribed more to some characters than others? 
<br><br>
I find this especially interesting in the realm of slash. Even in the absence of explicit homosexual relationships in canon material to guide assignment, we can often find certain characters appearing more as bottoms (or tops) than others in fanon. Are there characteristics - personality-wise, appearance-wise - in the character's canon form that predisposes them to a particular role in fanon?
<br><br>
I don't think these questions can be fully answered by quantitative methods. And we're getting ahead of ourselves anyway. To answer these questions, we need to start from the very beginning - <i><b>what is the fanon character like, anyway</b></i>? And that's something I think quantitative methods can help with, given the huge amount of text we need to summarise and sift through. <br>
<br>
In this analysis, I focus <b>only on author-provided tags</b>. Obviously, that means we only get a part of the picture, since qualities are likely described and performed much more within the text of the story itself. Those may be more difficult to retrieve though, so I'm starting small. Methodology covered in [a blog post](https://program-800.tumblr.com/post/190178483501/exploring-dbh-fics-part-8).
<br><br>
Wordclouds generated using the WordCloud library of Python. Character masks are screencaps I got off Google and edited myself.

## Characters
<p float="left">
  <a href="https://dru-r.github.io/ao3-dbh-analysis/dbh-charadescripts.html#connor-in-fanon">
    <img src="https://raw.githubusercontent.com/dru-r/ao3-dbh-analysis/master/docs/visuals/08_charatags/connor_.png" width="200" title="Connor" alt="Connor"/></a>
  <a href="https://dru-r.github.io/ao3-dbh-analysis/dbh-charadescripts.html#rk900-in-fanon">
    <img src="https://raw.githubusercontent.com/dru-r/ao3-dbh-analysis/master/docs/visuals/08_charatags/nines_3.png" width="200" title="RK900" alt="RK900"/></a>
  <a href="https://dru-r.github.io/ao3-dbh-analysis/dbh-charadescripts.html#hank-anderson-in-fanon">
    <img src="https://raw.githubusercontent.com/dru-r/ao3-dbh-analysis/master/docs/visuals/08_charatags/hank_.png" width="200" title="Hank Anderson" alt="Hank Anderson"/></a>
  <a href="https://dru-r.github.io/ao3-dbh-analysis/dbh-charadescripts.html#gavin-reed-in-fanon">
    <img src="https://raw.githubusercontent.com/dru-r/ao3-dbh-analysis/master/docs/visuals/08_charatags/gavin_.png" width="200" title="Gavin Reed" alt="Gavin Reed"/></a>
</p>

<b>Extra discussion: [Bottoms, submissives, alphas](#bottoms-submissives-alphas)</b><br>
<b>[Ending notes](#ending-notes)</b>

## Connor in fanon
![image](/visuals/08_charatags/connor_wc.png)<br>
<b>Top 3 words in the wordcloud are: <i>bottom, adorable, trans</i>.</b> <br>
This is interesting given that Connor in canon is the most advanced android model out on the field and is built specifically to hunt other (deviant) androids. In most of his routes, you will kill at least one person/android. This includes the 'good' Connor route, if you want to keep him alive. I think the wordcloud shows that Connor's gentle appearance is very (successfully) impactful.  
<br><br>
For clarity I separated 'deviant', 'machine', and 'human' descriptions from the wordcloud. The breakdown is here: <br>
![image](/visuals/08_charatags/connor_is.jpg) <br>
We see a clear preference for deviant Connor.

## RK900 in fanon
![image](/visuals/08_charatags/nines_wc.png)<br>
<b>Top 3 words in the wordcloud are: <i>top, protective, soft</i>.</b> <br>
RK900 is another interesting case. We don't actually have much of a "canon" RK900, since we only see him on the machine Connor route for a couple of seconds and he doesn't say anything (beyond staring at Connor as he leaves). Yet, the wordcloud suggests a rather coherent picture that the fandom has developed for RK900. To me, it seems a fair bit more dominant/stronger than Connor's fanon depiction. Why? I can only guess it's because he's supposed to be an 'upgrade' to Connor, but physically, his appearance is exactly the same - save for the fact that he has blue eyes instead of brown.
<br><br>
Again, for clarity I separated 'deviant', 'machine', and 'human' descriptions from the wordcloud. The breakdown is here: <br>
![image](/visuals/08_charatags/nines_is.jpg) <br>
We see a clear preference for deviancy in RK900 too.

## Hank Anderson in fanon
![image](/visuals/08_charatags/hank_wc.png)<br>
<b>Top 3 words in the wordcloud are: <i>good parent, parent, protective</i>.</b> <br>
My personal fic reading revolves mainly around RK1700 so fanon Hank as parental never really stuck out to me as a huge trait - but this wordcloud suggests otherwise! Very understandable, given Hank's tragic backstory regarding his son and his in-game protectiveness of Connor/referring to Connor as 'son' (in some routes; the ones where he isn't openly antagonistic and wants to blow Connor's processors out). Hank's canonical general depressive and self-destructive tendencies are also reflected in the wordcloud. There's also a fair amount of exploration as Hank as the android instead.

## Gavin Reed in fanon
![image](/visuals/08_charatags/gavin_wc.png)<br>
<b>Top 3 words in the wordcloud are: <i>asshole, android, trans</i>.</b> <br>
Gavin is a strange beast to me. He doesn't appear a lot in the game (and when he does, he's always a dick to Connor) but he seems very popular with the fandom. Personally I am really not a fan of him - I avoid shipfics with him and in my playthrough barely saw him at all (didn't let Connor give him his coffee and just brushed him off before entering the evidence room). Asshole being Gavin's top descriptor is really no wonder, but looking at the other descriptors in the wordcloud, there's definitely a fair amount of redemption arc/exploration of other traits that were not exhibited in the admittedly rather one-dimensional canon character. Exploration of Gavin as the android is also rather high.

## Bottoms, submissives, alphas
The last thing I'd like to discuss for now is the breakdown of the bottom/top, submissive/dominant, alpha/omega tags for each of these four characters.
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
</head>
<body>

<div style="overflow-x:auto;">
  <table>
    <tr>
      <th>Character</th>
      <th>Bottom % (out of Bottom+Top)</th>
      <th>Sub % (out of Sub+Dom)</th>
      <th>Omega % (out of Omega+Alpha)</th>
    </tr>
    <tr>
      <td>Connor</td>
      <td>62.5% (of total 419)</td>
      <td>61.7% (of total 81)</td>
      <td>92.2% (of total 51)</td>
    </tr>
    <tr>
      <td>RK900</td>
      <td>35.7% (of total 221)</td>
      <td>18.9% (of total 37)</td>
      <td>26.2% (of total 42)</td>
    </tr>
    <tr>
      <td>Hank Anderson</td>
      <td>56.0% (of total 336)</td>
      <td>29.6% (of total 27)</td>
      <td>10.9% (of total 46)</td>
    </tr>
    <tr>
      <td>Gavin Reed</td>
      <td>66.5% (of total 266)</td>
      <td>78.9% (of total 57)</td>
      <td>71.8% (of total 39)</td>
    </tr>
  </table>
</div>

</body>
</html>

Connor and Gavin are tagged as being bottoms, submissive, and omegas more often than they are characterised as tops/doms/alphas. In contrast, we have Hank who's kind of middling between bottom/top, but is strongly dominant and more often alpha otherwise. RK900 on the other hand appears as dominant all around - more often tagged as a top, alpha, and dominant. <br>
<br>
Now off-hand I'm not really sure why Gavin is typically characterised as sub and bottom. In-game he has zero qualms pulling out a gun to threaten Connor/beating Connor at the workplace and is generally very assertive of himself. Maybe it's the attractive 'bad guy with a soft side' trope at play? <br><br>
For Hank - I was a little surprised that he was so balanced in the top/bottom role but then skewed so heavily to dominant and alpha. Maybe not all top Hanks are tagged because there's some assumption that a grizzly hardened lieutenant will be the top...or I'm missing out something by not exploring outside of RK1700 and some limited Hankcon fics. <br><br>
Connor could really go either way depending on playstyle, but I think deviant Connor (i.e., making largely 'soft'/empathetic choices) is a very popular choice and again, Connor's character design lends itself to a very soft first impression. Based on unsubstantiated self-theorising, fanon RK900 probably turned out so dominant largely in part to contrast against Connor/Gavin (who he usually is shipped with/appears in fics with).<br>

## Ending notes
This was a really fun exercise and I was glad that I could pull out rather coherent pictures automatically and based on very limited tag information. Still I cannot stress enough that this is not the complete picture - likely, the automated heuristics don't capture everything perfectly and <b>very importantly, a lot of personality traits and qualities are demonstrated via actions and/or descriptions in the fics, rather than flat-out described in a short tag</b>. Clearly, this method is also insufficient for characters that appear less in fandom, like Luther, maybe even Kara(!).

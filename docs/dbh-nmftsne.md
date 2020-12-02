# Visualising D:BH fics based on verb usage
Can fics be clustered based on verb usage? For example, would I be able to see a cluster for character introspection fics, for date-y fics, for smut, etc? I had hoped the answer would be a nice yes, but as with all the new things I'm learning, it's a "no, until you figure out how to git gud".<br>
<br>
Nevertheless I'm leaving this up first as a WIP. <b>Full blog post detailing process is [here](holder)</b>.
<br>
### Interactive visualisation is [here](/visuals/14_tsne-nmf/tsne-nmf.html).
[Credits to palette found here](https://lospec.com/palette-list/dots). Each fic is represented by one dot in the scatterplot, and I've put the top 5 tf-idf weighted words for that fic in its hover data. More or less a gigantic hairball, but I'd like to point out the little group of smutty-seeming fics lurking at the bottom left (topics 2, 5, 18, and 32 selected).<br>
![image](/visuals/14_tsne-nmf/tsne-nmf-exp.PNG)
### Top 15 keywords for each NMF topic
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: left;">
      <th></th>
      <th>Top 15 keywords</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>go, do, put, happen, feel, miss, check, wait, plan, change, drop, drive, shut, figure, worry</td>
    </tr>
    <tr>
      <th>1</th>
      <td>say, ask, mean, sound, leave, find, do, put, should, guess, thank, may, lean, repeat, roll</td>
    </tr>
    <tr>
      <th>2</th>
      <td>moan, pull, thrust, push, suck, lick, cum, stroke, bite, pant, groan, whine, slide, tease, gasp</td>
    </tr>
    <tr>
      <th>3</th>
      <td>can, help, should, turn, must, may, stop, hear, keep, ask, shake, raise, fix, build, breathe</td>
    </tr>
    <tr>
      <th>4</th>
      <td>feel, get, experience, understand, breathe, touch, stare, realize, hear, become, smile, turn, wonder, remember, burn</td>
    </tr>
    <tr>
      <th>5</th>
      <td>press, pull, reach, slide, hold, lean, draw, slip, push, curl, shift, brush, wrap, fall, rest</td>
    </tr>
    <tr>
      <th>6</th>
      <td>look, sit, stand, wear, put, open, notice, lean, point, close, show, stare, cover, must, confuse</td>
    </tr>
    <tr>
      <th>7</th>
      <td>like, watch, enjoy, play, eat, wear, buy, work, pick, spend, try, learn, read, use, laugh</td>
    </tr>
    <tr>
      <th>8</th>
      <td>love, cry, hold, whisper, marry, share, spend, become, deserve, hug, fall, play, grow, cuddle, wrap</td>
    </tr>
    <tr>
      <th>9</th>
      <td>know, mean, understand, do, hate, happen, wish, learn, speak, deserve, lose, hope, live, trust, meet</td>
    </tr>
    <tr>
      <th>10</th>
      <td>would, hope, have, care, wonder, end, change, wish, turn, plan, spend, assume, allow, matter, decide</td>
    </tr>
    <tr>
      <th>11</th>
      <td>could, help, keep, do, hear, lose, wish, bring, stare, imagine, realize, suppose, happen, handle, break</td>
    </tr>
    <tr>
      <th>12</th>
      <td>want, touch, hurt, care, deserve, ask, stop, understand, hate, should, live, stay, stare, talk, ruin</td>
    </tr>
    <tr>
      <th>13</th>
      <td>make, do, keep, use, have, manage, bring, put, turn, work, catch, cover, ruin, taste, mean</td>
    </tr>
    <tr>
      <th>14</th>
      <td>come, bring, wait, play, hear, realize, run, stay, open, call, stand, follow, jump, expect, pass</td>
    </tr>
    <tr>
      <th>15</th>
      <td>ask, reply, answer, explain, nod, sigh, try, exclaim, add, admit, suggest, state, wait, sit, call</td>
    </tr>
    <tr>
      <th>16</th>
      <td>see, hear, watch, show, meet, remember, hope, lead, catch, miss, wait, pass, notice, send, shine</td>
    </tr>
    <tr>
      <th>17</th>
      <td>get, work, call, put, keep, have, head, wait, pick, guess, be, roll, send, stick, laugh</td>
    </tr>
    <tr>
      <th>18</th>
      <td>fuck, hate, need, fucking, shove, throw, piss, do, be, ignore, shut, mutter, laugh, glare, suck/td>
    </tr>
    <tr>
      <th>19</th>
      <td>think, may, mean, should, realize, guess, suppose, wonder, talk, consider, imagine, sound, forget, believe, remember</td>
    </tr>
    <tr>
      <th>20</th>
      <td>take, put, hold, bring, set, pick, open, keep, hand, offer, drink, wait, throw, drop, wash</td>
    </tr>
    <tr>
      <th>21</th>
      <td>walk, pull, grab, stand, run, open, turn, sit, place, push, scan, follow, yell, put, step</td>
    </tr>
    <tr>
      <th>22</th>
      <td>will, may, promise, should, must, wish, protect, hope, kill, wait, destroy, change, turn, believe, hide</td>
    </tr>
    <tr>
      <th>23</th>
      <td>try, keep, stop, hear, hurt, push, manage, hold, happen, ignore, force, run, sound, scream, calm</td>
    </tr>
    <tr>
      <th>24</th>
      <td>die, kill, shoot, cry, hurt, save, fall, happen, live, run, scream, lose, stop, whisper, remember</td>
    </tr>
    <tr>
      <th>25</th>
      <td>begin, speak, continue, place, become, cause, hear, grow, reply, attempt, return, remain, respond, fall, rise</td>
    </tr>
    <tr>
      <th>26</th>
      <td>smile, laugh, nod, chuckle, sigh, whisper, thank, grin, help, shake, smirk, hug, blush, giggle, hold</td>
    </tr>
    <tr>
      <th>27</th>
      <td>move, watch, stop, open, push, close, lay, remove, continue, touch, hold, keep, reach, place, fall</td>
    </tr>
    <tr>
      <th>28</th>
      <td>find, search, hide, help, run, realise, abandon, lose, catch, bring, follow, grow, decide, manage, spot</td>
    </tr>
    <tr>
      <th>29</th>
      <td>give, hold, wear, thank, bring, have, earn, meet, hand, tease, save, keep, set, try, help</td>
    </tr>
    <tr>
      <th>30</th>
      <td>need, help, work, keep, nod, stay, should, thank, see, run, hurt, do, worry, check, shake</td>
    </tr>
    <tr>
      <th>31</th>
      <td>seem, notice, decide, should, may, realize, sound, happen, have, consider, expect, figure, speak, suppose, glance</td>
    </tr>
    <tr>
      <th>32</th>
      <td>kiss, pull, lean, press, turn, touch, wrap, laugh, smile, whisper, cup, blush, caress, close, nuzzle</td>
    </tr>
    <tr>
      <th>33</th>
      <td>may, work, become, remain, allow, understand, use, return, design, consider, create, send, follow, appear, continue</td>
    </tr>
    <tr>
      <th>34</th>
      <td>start, play, hear, stop, continue, decide, turn, notice, happen, talk, become, work, finish, end, do</td>
    </tr>
    <tr>
      <th>35</th>
      <td>let, hold, keep, close, fall, stop, use, stay, show, guide, lower, trust, put, promise, relax</td>
    </tr>
    <tr>
      <th>36</th>
      <td>tell, talk, call, happen, remember, speak, should, listen, hear, sit, answer, mean, understand, care, hate</td>
    </tr>
    <tr>
      <th>37</th>
      <td>leave, stay, miss, stand, return, fill, pass, ignore, keep, hide, stop, follow, realise, wait, enter</td>
    </tr>
    <tr>
      <th>38</th>
      <td>turn, stare, glance, stand, watch, step, nod, raise, shake, blink, frown, follow, sigh, speak, mutter</td>
    </tr>
    <tr>
      <th>39</th>
      <td>sit, sleep, wake, eat, watch, lay, rest, stay, fall, remember, set, rub, lie, read, close</td>
    </tr>
  </tbody>
</table>




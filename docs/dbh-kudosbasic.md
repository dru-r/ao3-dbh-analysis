# An initial look at kudos on AO3 D:BH fics
Basic descriptives of kudos. With information on the users who left kudos and the amount of guests per story who contributed kudos, I'm hoping to do more in-depth analyses to follow up. I'll update if there's any interesting!<br>

### Note:
I scraped the kudo list at the end of each story (e.g. Connor, Markus, Kara, and 2 more users Hank and Sumo, as well as 5 guests left kudos on this work!) and used regex to extract the (1) names of registered users, and (2) the number of guests who left kudos. <br>
<br>
Overall, I extracted information on <b>3144226 kudos</b> this way. AO3 also provides its own kudo count on each story; summing those gave me a total of <b>3144430</b>. There's a discrepancy of 204 kudos between my extracted number and AO3's reported total - a very small discrepancy. On closer inspection, I see that 202 fics are missing 1 kudos each from my extraction, and 2 fics are missing 2 kudos. I'm not sure about AO3's backend, but I'm thinking that the cause could be readers leaving kudos while I was scraping. <br>
In any case, I went ahead with the information I extracted.

## Breakdown of kudos-givers (user vs guest)
![image](/visuals/13a_kudos_basics/users_vs_guest.PNG)<br>
[Click here for the interactive version with numbers](/visuals/13a_kudos_basics/user_vs_guest.html)<br>

## Breakdown of kudos-givers (user vs guest), by rating
![image](/visuals/13a_kudos_basics/users_vs_guest_byrating.PNG)<br>
[Click here for the interactive version with numbers](/visuals/13a_kudos_basics/user_vs_guest_byrating.html)<br>

## Distribution of proportion of kudos-givers who are guests, by rating
For each fic, I divided the number of guests kudos-givers against the total number of kudos it received. I was wondering, for example, if explicit fics might skew more to a higher guest kudos-giver proportion, etc? (spoiler: the answer is no!) <br>
![image](/visuals/13a_kudos_basics/guestprop_byrating.PNG)<br>
[Click here for the interactive version with numbers](/visuals/13a_kudos_basics/guestprop_byrating.html)<br>


---
layout: post
title:  Album Statistics with Python
---

In May of 2014, I released my first video game music album titled <i>Aural Nostalgia Vol. 1</i> in partial fulfillment of the requirements to graduate from the Honors Institute at Michigan Tech.

Fast-forward three years and I have made somewhere in the realm of $200 to $300. The past several months my income from this album has been roughly $9/month. The company that distributes my album (and takes care of royalty payments to the copyright holders) is Soundrop and every month they send me a CSV file of the previous month's transactions. This file contains a wealth of information that is tedius to go through by hand using MS Excel. So I put my coding skills to good use and wrote up a Python script that will read in the CSV file, parse the contents, and plot several variables as pie charts. 

The variables I'm interested in are total quantities purchased or streamed as a function of service and total money earned as a function of track, country, and service. Figure 1 shows the total amount of streams or purchases by service. Spotify has the most streams at 87.7% and Apple Music has the second largest piece of the pie at 7.9%. Figure 1 shows that people stream my music more than they buy and download it.  

<div class="w3-card-4">
   <img src="/images/Sep_2017_09-15-2017_Quantity.png" class="w3-round" alt="Quantity Stats">
   <div class="w3-container" style="text-align:center;">
      Figure 1: Total streams/purchases by service
   </div>
</div>
<br />
Figure 2 shows the income earned by country. Unsurprisingly, the United States makes up almost three-quarters of the pie. The "Other" category includes all countries with income less than 15 cents. I <i>am</i> surprised by how many countries (39!) listen to my music, though.


<div class="w3-card-4">
   <img src="/images/Sep_2017_09-15-2017.png" class="w3-round" alt="Money by country">
   <div class="w3-container" style="text-align:center;">
      Figure 2: Total money earned by country
   </div>
</div>
<br />

Figure 3 shows the income earned by service. Spotify again makes up the largest piece of the pie, which is a little surprising because streams earn less than purchases. As seen in Figure 1, there was a lot of streams this month. Unlike some other artists, I don't mind people streaming my music instead of buying it outright. That's what I do. I can't even remember the last time I purchased music from iTunes, Google Play, or Amazon. I have backed a few Kickstarter albums, though. 

Before now, I haven't even heard of iTunes Match or Google Play Locker. It seems that iTunes Match lets you upload your own iTunes library (up to 100,000 songs) to the cloud for $25 a year so you can stream them from up to nine devices. So kind of like Google Music in the beginning except Google Music was free. So I guess artists still make money when a song is uploaded to the cloud via iTunes Match? It looks like Google Play Locker is similar, but is free and allows for 50,000 songs.
<div class="w3-card-4">
   <img src="/images/Sep_2017_09-15-2017_Service.png" class="w3-round" alt="service stats">
   <div class="w3-container" style="text-align:center;">
      Figure 3: Total money earned by service
   </div>
</div>
<br />
Figure 4 shows the total money earned by track. It appears that my arrangements of the two Metroid Prime 1/2 songs are the most popular followed by "Mt. Coronet" from Pokemon Diamond/Pearl/Platinum. Maybe I should release more Metroid Prime Trilogy music. Well, I do have <a href="https://soundcloud.com/willpisani/theme-of-u-mos-3-13-2013">four</a> <a href="https://soundcloud.com/willpisani/torvus-bog-redux-3-13-2013">in</a> <a href="https://soundcloud.com/willpisani/metroid-prime-3-corruption-1">the</a> <a href="https://soundcloud.com/willpisani/mptrilogy-title-theme-7-4-2012">pipeline</a>, at various stages of completion. 
<div class="w3-card-4">
   <img src="/images/Sep_2017_09-15-2017_Track.png" class="w3-round" alt="Track Stats">
   <div class="w3-container" style="text-align:center;">
      Figure 4: Total money earned by track
   </div>
</div>
<br />

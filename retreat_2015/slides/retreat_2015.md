![](slides/img/awesome.jpg)
## Bioinformatics 



Note: So today I'm going to tell you about the exciting stuff that's been going on in the bioinformatics team in the last twelve months.


\new_slide
###### How to lose friends and alienate people
## With computer games
Note: The first thing will be how we made ourselves feel like the least popular people in the world by inventing and releasing a computer game.

\sub_slide
<img src="slides/img/shyam.png" style="border:none;border-radius:50%;background-color:white;padding:20px;">

[Shyam Rallapalli](https://github.com/shyamrallapalli)

Note: And this is work that was done by Shyam.

\sub_slide
### Fraxinus: a citizen-science game to tackle ash dieback
![Fraxinus game screen](slides/img/fraxinus_game.jpg)

Note: In 2012 ash dieback, caused by _Hymenoscyphus fraxineus_ was reported in the wild in the UK, it caught everyone a bit by surprise as it seemed to spread across the country really quickly and there was something of a national outcry that something must be done. 

As part of a wider crowdsourcing effort we tried to involve the general public to do some work that we thought humans would be better at than our algorithms. We did this with a game called Fraxinus, it’s a FLASH only facebook game designed by myself and the BAFTA nominated game company Team Cooper in Sheffield. This is the main game screen of Fraxinus. The game contains sequences from an assembly of _H.fraxineus_ and reads from different isolates.

The aim of the game is to do alignments for us. And the game provides the tools a player needs to do that.

Along the top we have Target Pattern, from one of our references. Targets are pre-selected to be the sites the algorithms make a mess in. 

The rest of the coloured rows are reads from DNA sequencing experiments. The player can Shift, insert and delete nucleotides to make best alignment. Score for matches, score deducted for mismatches and creating and extending gaps. Once player has maximum score they think they can get, they can claim the pattern for themselves and get points for that. 

We released Fraxinus and started to analyse the results from the puzzles that people were playing and the behaviour of the players.

\sub_slide
#### Players converge on the same solutions
![](slides/img/fraxinus_puzzles_alignments_different.jpg)

Note: The players provided a lot of information, basically the players showed a surprising agreement with each other in the solutions that they provided, these figures show the split of differences between the players and software and the striking thing is that they either agree with the software completely, or they all disagree with the software in the same way. This validates the notion that replay and competition in the game got us better alignments.  

\sub_slide
#### Players beat software, especially on INDELs
![](slides/img/fraxinus_puzzles_snps_indels_different.jpg)

Note: The players genuinely contributed better results than the software. Here the yellow areas represent the proportion of puzzles the players were better at. On average about 12 percent of the puzzles we uploaded were improved by the players. In the INDELs we uploaded we get improvements of about 30 percent.

And they were better regardless of how we score them, we get the same pattern if we use the identity of sequences or the scoring matrix used in the software.

So the game filled its primary purpose, it helped reliably increase our stock of knowledge about genetic variants in ash dieback which we plugged back into our public databases for use by anyone.

\sub_slide
#### OMG! We were soo popular!
![](slides/img/world_map.jpg)

Note: And it did this on a large scale, Fraxinus was a very popular game. Part of the strength of Fraxinus was that it got a lot of media attention, thanks mostly to the comms team. Their efforts pushed us into the pages of several major newspapers and on the TV and as a result we got over 60 000 hits to the game from 137 different countries, which is loads! So it was a big success in those terms and is a significant crowdsourcing project.

\sub_slide
#### Players deserted the game
![](slides/img/fraxinus_visits_over_time.jpg)
<span class="fragment roll-in">
			<img src="slides/img/friends-2-10k.png">
</span>
<span class="fragment roll-in">
				<img src="slides/img/friends-2-500.png">
</span>
<span class="fragment roll-in">
				<img src="slides/img/friends-2-25.png">
</span>

Note: But as time progressed, we found that those headline numbers were masking something much more interesting. Players were leaving the game at an astonishing rate. 

This figure shows the number of visits, sampled each day. Note that this is on a log scale and the decrease is still very visible with a sharp initial part and a long tail. 

On average we lost 95 % of our visitors, each day.

To put this in perspective, if we start off with 10000 on Monday *CLICK*

on Tuesday we have 500 *CLICK* 

and by Wednesday we've just *CLICK* 25 left.   


\sub_slide
#### So, we were like...
![](slides/img/merida.jpg)

Note: Now, no one likes losing friends that quickly, not even bioinformaticians! So we weren't impressed. Apparently we'd snatched defeat from the jaws of victory...

\sub_slide
#### But thats ok, a 'hardcore' did most work anyway
![](slides/img/contributions.jpg)

Note: But it turns out we needn't have worried. Most players contributed very little at all. In this figure, which is players versus cumulative number of alignments, we see about 50 percent of the actual work was done by just 49 of the 60,000 people who ever visited. We picked up a hardcore of players who kept coming back and playing over and over.

\sub_slide
#### How much work gets done? 

$$ Work Done = \frac{Human Time - Education Cost}{Task Length} $$

![](slides/img/fraxinus_visits_over_time.jpg)

Note: So then our attention turned to the more general question of how many tasks could get done, in any crowdsourcing project? 

It was easy to formulate a general idea of this, its the total time spent divided by the time it takes to do the task, taking count of any time it takes to learn to do the task.

In a specific sense then the total human time can be measured for Fraxinus, its the time spent on the website. 

But the general pattern for any crowdsourcing project is different. The total human time provided is basically all the visits you get multiplied the time spent each visit added up, so more or less the area under the curve, here. The pattern of visits then is the important thing. So we need to capture that.

\sub_slide
#### A power law fits the player data
$$ y = 4074 x^{-0.94} $$
![](slides/img/power_law.jpg)
$$ y = ax^k $$

Note: 
And we looked at our and other crowdsourcing projects visit data. They follow a remarkably similar pattern to our very lossy one, with that same drastic curve.

So we went ahead and fit the Fraxinus visit data with regression using log-log scales, and we find that it matches up to a power law relationship, which is a similar relationship to exponential growth curves. In our case it goes backwards, losing stuff exponentially, rather than growing. And the general form provides a basis for a model for player visit numbers. 

\sub_slide
#### A model for the work done 


$$ y = ax^k $$

<span class="fragment roll-in">$$\int_s^f f(x) = ax^{-\alpha}$$</span>

<span class="fragment roll-in">$$  \int_s^f f(x) = i(z + a^{-\alpha}) + ja\omega x^{-\beta}$$</span>

Note: and from this basis we 

**click** re-jig the thing to be an integral, to represent the total sum of times, 

**click** then add in some terms to take account of the relative contributions of returning and new players AND to allow us to represent media events that attract an arbitrary new set of players.

So this gives us a tool with which we can run scenarios relating to human involvement and interest in tasks and work out how much stuff can be done and the sorts of audience we can reach. 
 

\sub_slide

#### Predicting the work and progress from different crowdsourcing strategies 
![](slides/img/fraxinus_preds.jpg)

Note: and this slide shows just that, we see here the models take on the Fraxinus parameters, it replays that scenario very closely.

It also shows that had we not had extra press releases after our initial set we wouldnt have lost very much at all.

We also see that it would have been very hard to make something like this work through a viral strategy. These last four show different friend recruitment regimes, and to get any where near what we saw from the traditional media interest, you need to get on average very silly numbers of friends playing and staying immediately. The red line has players recruiting 10 others immediately and them all staying. So crowdsourcing is all about the release plan, really, purely viral strategies need to be extremely infectious, a better bet is to reach for some sort of bigger name who can help push your activity to a wide audience, this may be traditional media.





\sub_slide

* Lots of people play - for a little bit
* A few people stay - forever
* Most of the opportunity for work is at the beginning
* It's a friend-losing game
* Viral doesn't work

Note: So here's what we learned about the game of crowdsourcing...

\new_slide
###### Studying the effect of host jumps on pathogen genome size
## With mathematics

Note: Im going to change tack now and move over to something a bit more familiar, the study of pathogen genome size and host jumps, but with mathematical, rather than biochemical approaches.

\sub_slide

<img src="slides/img/carlos.png" style="border:none;border-radius:50%;background-color:white;padding:20px;">

[Carlos Lugo](https://twitter.com/kupkasmale)

Note: and this is Carlos' work.

\sub_slide
#### Genomes are expanded in some filamentous plant pathogens
![](slides/img/expansion_table.png)

_Raffaele and Kamoun 2012_

Note: It's been observed that the genomes of several lineages of filamentous plant pathogens, these ones with the bigger blue blobs here,  have repeat-rich genomes, with these regions being effector rich and highly polymorphic, suggesting they may be undergoing particular selection.

We're interested in the mechanics of this phenomenon, the things that cause the genomes to be the way they are. In particular we're interested in what effect a change of hosts can have on a genome.  We can't run lab or field experiments on this so our better alternative is to use models to help us lay out our thoughts and work through scenarios that might have been.  


\sub_slide
###### Models are not just for predicting the future - they are an aid to understanding
![](slides/img/Watson-Crick-DNA-model.jpg)

Note: It's important to note what we hope to get out of our models. Often people will ask 'what will your model predict?', in the sense of 'how many y's will you get out for so many x's put in. And this is a pretty fair question, but it kind of misses an important point about many of our most useful models. Many of the world's models don't predict anything, they're simply there to help us understand what we are talking about better.

And my favourite example of that is summed up in this picture. This is, obviously, Crick and Watson with their model of the DNA helix. This isn't something they put together to help other people understand their insight afterwards. This is what they used to have that insight. Basically, they sat around in the lab with their data, staring at it, not sure what it meant. So they decided to build models, physical ones, from bits and pieces in the lab. Each one would be just a hypothesis of the structure of DNA. None of their data gave them the structure, they had to try out lots of different configurations, that fit the data. And some of them were wrong, including a three spined one, with the backbone in the middle, until they managed to work out one that seemed convincing to them. The model here was the aid to understanding that helped them settle and be convinced about what the actual structure was.

And this is what we are doing with the mathematical models we are making, trying to investigate a process that we can't run for real and test out what might have gone on in real life, and from the behaviour of the model, see what the features of host jump dynamics might be. 

\sub_slide
#### Model for host jump (I)

$$ N_g(t)=N_u + N_e $$ with 

$$ L(t)= \sum _{i \in g} l_i $$

$$ W_g=\frac{1}{N_e}\sum_j \frac{s_j}{s_j + s_o} $$

Note: So here's the first part of Carlos' model. 

\sub_slide
![](slides/img/confused.gif)

Note: Yeah, not as intuitive as the DNA one, right?

But that's because it is in mathematical notation, which is deliberately terse, and not really 'readable' in the usual sense.

\sub_slide
![](slides/img/read_maths.png)

Note: Basically, you have to fight with maths. The notation that gets used isn't something to get hung up on. It is always a bit esoteric and isn't as important as the thing that its describing, it isn't a cop-out to study a picture over the notation. Notation is just there to be as unambiguous as possible about what we are doing when we do get to write it down, so here's the model in graphical form.

\sub_slide
#### A graphical representation of model rules
![](slides/img/transformsnew.png)

Note: The main entity is the effector, and it can do certain stuff, basically transition into something else, with certain probabilities. The most likely is that it changes into itself but it can do other things, duplicate, recombine, get lost, get attached to a non-coding region which stands for transposable elements. 

Each effector has a value that stands for its contribution to the overall fitness of the organism and allows us to compare collections and populations. We can allow the system to change over time. according to the transition probabilities and at certain points reset the contributions to fitness. This mimics the action of host jumps.

The model progresses in time steps, so we get to view the changes according to the rules we have built in as time progresses.


\sub_slide
#### More frequent hopping increases genome length
![](slides/img/glengths.png) 

Note: This figure show the effect of jumping at different intervals, with a fixed proportion of contributions being reset. While genome lengths go up generally if jump happens at certain points it will go up more quickly. So, the simple action of hopping can be a driver for genome expansion. 

\sub_slide
#### More distant the host the greater the length change
![](slides/img/genome_lengths.png) 

Note: But it also seems to be a complex interplay between the distance of the jump and the proportion of effectors that stop contributing to fitness. Here the value C is the proportion that stop contributing and when this goes up, the genome length increases quicker.

If we take C to 0.3 though, the picture looks much more like it does at 0.1, so there may be a sweet spot of distance and hopping frequency that can really drive the expansion of genomes.


\sub_slide
* Genome length increases under straightforward mechanical processes
* Frequency and distance of jump interact to affect the rate of expansion
* Extreme expansion may occur at a sweet spot

Note: So here's what we're learning...		

\new_slide
###### Finding causative mutations in genetic screens
## Without a reference genome
Note: We've also been working on finding mutations in forward genetic screens when we don't have the luxury of a useful reference genome. The problem were trying to solve is to identify the actual causative mutation directly from the sequence or a broken draft assembly.

\sub_slide

<img src="slides/img/pilar.png" style="border:none;border-radius:50%;background-color:white;padding:10px;height:100px;float:left;" >
[Pilar Corredor Moreno](https://github.com)

<img src="slides/img/ed.png" style="border:none;border-radius:50%;background-color:white;padding:10px;height:100px;float:left;" >
[Ed Chalstrey](https://github.com)

<img src="slides/img/shyam.png" style="border:none;border-radius:50%;background-color:white;padding:10px;height:100px;float:left;" >
[Shyam Rallapalli](https://github.com)


Note: And this is the work of Pilar, Ed and soon Shyam

\sub_slide
#### SNP frequency peaks around causative mutation after crosses
![](slides/img/crosses.png)

Note:  We take advantage of the fact that in forward genetic screens, when we do mutagenesis we introduce SNPs at a uniform rate across the genome, subsequent crosses and selection fix the causative mutation in the population but also reduce the mutagenesis induced SNPs further away from the bit were selecting for in the screen, so we get a fading out of homozygous SNPs from the mutagenesis across the genome. 

We can use this information to reconstruct the order of contigs or reads from unassembled genomes.


\sub_slide
#### GATROC - genetic algorithm for reordering contigs

![](slides/img/order.png)

<img src="slides/img/images_hyp.gif" height=200>

Note: When we have a draft assembly of contigs or just reads, then the random order means that the distribution is smoothed out. We can put the peak back by reordering the contigs properly and we’ve been doing this with genetic algorithms that explore permutations and select the most appropriate. This picture shows a version looking for the optimum blue line and improving the permutations at each iteration.

However, this fails on real sized genomes, mostly because there were too many fragment permutations to explore in a sensible time. 

\sub_slide
#### SDM - A rapid sorter of fragments

![](slides/img/001.png)

Note: To gain speed this we developed a pre-filtering and sorting algorithm that can reconstruct the shape and approximate order of contigs or reads prior to any finishing that might be needed.

Its called SDM and it works by first placing all the fragments into ascending order of SNP frequency, so that we have a frequency plot that looks like this

\sub_slide
#### SDM - A rapid sorter of fragments

![](slides/img/sdm.gif)

Note: Then it works its way up that list, assigning the fragments to the far ends of another list in turn, building up toward the middle so that the original shape can be rebuilt. The fragments closest to the centre then become the ones most likely to be those with the mutation we are looking for. 


\sub_slide
####	SDM is accurate down to 10kb contigs
![](slides/img/sorting.png)

Note: So we've applied this so far on pseudo-unassembled genomes, by which I mean Arabidopsis that we've broken up into a test set so we can run SDM on it, and we can really see the causative mutations start to appear.

This figure shows the ratio of Homozygous to Heterozygous SNPs from a published sequencing by mapping scheme using NGS reads. The fragments go down to 10kb size, which is getting down to the level of bigger PacBio reads, and the peak is starting to appear in the right place here.

So we have a good basis for moving this into a real scenario, and we're looking for collaborators. If you have mutagenised plants and you're carrying out a screen we'd love to talk to you.

\sub_slide

* SDM can find causative mutations down to 10kb fragments
* We would like to try it 'for real' - can you help?

\new_slide
###### How to win friends and improve lives
## With core awesome

Note: Lastly I'd like to show you some of the core projects that we've been doing to help improve productivity of the lab through bioinformatics support.

\sub_slide
[Martin Page, Esq](https://www.twitter.com/biodevops)
<img src="slides/img/martin.png" style="border:none;border-radius:50%;background-color:white;padding:10px;height:100px;float:left;" >

[Graham Etherington]()
<img src="slides/img/gravestone.png" style="border:none;border-radius:50%;background-color:white;padding:10px;height:100px;float:left;" >

[Christian Schudoma]()
<img src="slides/img/christian.png" style="border:none;border-radius:50%;background-color:white;padding:10px;height:100px;float:left;" >

\sub_slide
#### CandiSNP - A tool for visualising and mapping mutations
[http://candisnp.tsl.ac.uk/awesome](http://candisnp.tsl.ac.uk/awesome)

Etherington, Monaghan _et al_ Plant Methods *2014*, 10:41 
<video controls width="750" data-src='slides/img/candisnp.mov' autoplay="true" loop="true"></video>

Note: One thing we developed this year with the Zipfel group is CandiSNP a tool for visualising and identifying causative mutations from forward genetic screens on reference genomes. It makes use of SNP density plots as a mapping strategy to identify and refine chromosomal positions of causative mutations from screened plant populations.


CandiSNP has an interactive live interface to label and filter based on a candidate SNP approach. It allows you to upload your SNP list, visualise it and start filtering and identifying candidates by marking up snp types with colour, mouse hovers let you see annotations like the transition that was caused and gene models that SNPs fall into etc. 

It is an effective tool and is particularly useful for analysing sequence data from bulked back-crossed mutants, which contain fewer polymorphisms than data generated from out-crosses.

And soon CandiSNP will be an end to end tool. We've developed the interface so that it can be used directly within Galaxy and incorporated into interactive SNP calling pipelines.

\sub_slide
#### SugarNet - A tool for inspecting co-regulatory networks
###### I know the name sucks ... any suggestions?
<video controls width="750" data-src='slides/img/sugarnet.mov' autoplay="true" loop="true"></video>

Note: Another tool we've created, also with the Zipfel group is SugarNet, which allows you to upload time-course expression data and runs methods that predict transcriptional regulatory interactions. From this it builds a transcriptional regulatory network.

The networks can be visualised and interrogated interactively on screen by adjusting things like layout and colour schemes and applying network statistic counters. The tool makes a difficult bioinformatics analysis easier and allows us to go straight to understanding structures as well as providing candidate regulators for further analysis. 


\sub_slide
#### Kraken - metagenomics 
![](slides/img/krona.png)

Note: And something we've been working on recently is porting the powerful Kraken metagenomics sequence taxonomy classifier to a graphical interface within galaxy.

Kraken can quickly and accurately workout the taxonomic level that an individual sequence read came from, we have optimised this for use on phyopathogenic organisms on a plant background and built tools that can extract all sequences quickly from a given taxonomic level for easy and more complete downstream assembly. Soon we will have implented an interactive visualisation like this krona plot which will allow exploration of the taxa represented in the phytopathogen interaction metagenome or transcriptome.

\sub_slide
#### Quantification of disease in low quality images
![](slides/img/ir_image8.jpg)

Note: We've also been working on new technologies for in lab and in field disease identification and quantification. Our starting point has been very low quality infrared images like this one. USing IR gives us much more information about the physiological state of plant tissue than standard RGB images.

\sub_slide
#### Quantification of disease in low quality images
![](slides/img/segmented.png)

Note: We convert the signal to a measure of IR enrichment and ditch colour information, which reduces the problem to a single data dimension that we can put through a simple peak finding analysis to find the regions of the leaf that correspond to different physiological states. So the red areas are the photosyntetically active tissues, the yellow are the infected and the light blue are necrotic. So we have a fast effective pipeline for analysing and quantifying diseased plant images.
 
\sub_slide
#### Cheap hardware

![](slides/img/raspberrypi.jpg)

&#163; 35 

Note:  This doesn't require intense computation or specialised software so you can take advantage of hardware like the Raspberry Pi, which is a tiny little computer which costs peanuts and has a user-programmable set of metal pins sticking out if that a user can control by simple Python software running on the Pi.

\sub_slide
#### Home-made robots
<img src="slides/img/robot.jpg" height=350>

Note: With those pins you can connect up to any electrical device like stepper motors or camers and use those to build various things like camera driving robots for use in the lab for time lapsing, for things like specialised phenotyping machines or even for automating your genetic screens. So this is a little raspberry pi driven cam-robot. The pi is hidden here at the front and its running a little motor along this track made by two shower curtain rails a and a timing belt out of a washing machine. Total cost without camera is about 50 pounds. 

\sub_slide
#### The future is flying robots

<img src="slides/img/qcopter.png" height=400>

Note: And one plan we have for the near future is to mount this computational image software onto quadcopters running GPS autopilot and fly them over fields to examine disease progress and facilitate a sort of flying digital immune system.

\sub_slide

###### The big event this summer
#### Galaxy Community Conference - gcc2015.tsl.ac.uk
<img src="slides/img/gcc.png" height=350>


Note: And finally, a shameless plug for the biggest event happening at TSL this summer, the 250 attendee strong Galaxy Community Conference which brings together bench and computational scientists who use and build the Galaxy Tool that forms a large part of our bioinformatics support provision. The conference will have a very large training stream with two full days on a wide range of biologist-centric topics and some excellent speakers from the computational and biology sides including the keynote...

\sub_slide
###### GCC 2015 Keynote
#### Oliver Stegle - EBI
<img src="slides/img/stegle.png" style="border:none;border-radius:50%;background-color:white;padding:10px;height:150px;" >
###### 'Modeling molecular heterogeneity between individuals and single cells'

Note: which will be given by Oliver Stegle who will talk about his work on determining population structure in genetic association studies in individuals and single cells.

\sub_slide
#### Bioinformatics is awesome
![](slides/img/unicorn.jpg)

Note: So I hope I've convinced you we have an awesome bioinformatics team with awesome stuff going on. In the teams own words, more awesome than a cat with a golden gun riding a fire breathing unicorn.


\new_slide

<div id="titles"><div id="titlecontent">

<h2 style="text-align:center;">Acknowledgements</h2>

<h3 style="text-align:center;"> Team MacLean</h3>
<img class="center" style="border:none;shadow:none;" src="slides/img/team.png">
<h3 style="text-align:center;">Fraxinus</h3>
<p class="center">Shyam Rallapalli</p>
<p class="center">Team Cooper</p>
<p class="center">Allan Downie and Anne Edwards</p>
<p class="center">Sophien Kamoun and KamounLab</p>
<p class="center">The Genome Analysis Centre</p>
<p class="center">The Fraxinus Players</p>
<h3 style="text-align:center;">Theoretical Genomics</h3>
<p class="center">Carlos Lugo</p>
<h3 style="text-align:center;">Mutation Hunters</h3>
<p class="center">Pilar Corredor Moreno</p>
<p class="center">Ed Chalstrey</p>
<p class="center">Shyam Rallapalli</p>
<h3 style="text-align:center;">Core Awesomeness</h3>
<p class="center">Martin Page, Esq</p>
<p class="center">Christian Schudoma (not actually a pirate)</p>
<p class="center">The Late Graham Etherington</p>
<h3 style="text-align:center;">Consulting bench-bound scientists</h3>
<p class="center">CandiSNP - Jacqui &#x1f4a9; Monaghan</p>
<p class="center">SugarNet - Rosa Lozano Duran</p>
<p class="center">Kraken - Yogesh Gupta</p>

<h3 style="text-align:center;">Funding</h3>
![](slides/img/logo.gif)
![](slides/img/defra.jpg)
![](slides/img/fera.jpg)
![](slides/img/forest_research.jpg)
![](slides/img/gatsby.png)
</div></div>
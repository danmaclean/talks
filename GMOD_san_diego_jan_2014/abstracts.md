





#GMOD 2014 - San Diego

##Poster Application Abstract

GeeFu is a Ruby-on-Rails app that has genomic features as its main model and allows multiple organisms and multiple assemblies per organism to be called up and annotated, instead of just one. It runs on our bio-samtools and svgenes gems to render bam data and features,  and integrates other open source software like bio-dalliance as a portable viewport. Gee fu sits as an integration layer between other tools more suited to specific purposes, it acts as the dispatch engine for data to the GMOD project Web-Apollo genome annotation browser, as a feature linking engine for a wiki and as the sequence store for a BLAST server and also as a launcher of badge instances for Mozilla OpenBadges.

It coordinates automatic exchange and concurrency of data between the apps and a Git repo, making sure that contributions from these other tools are tracked.
It provides a RESTful interface to the repo data and still acts as a feature and meta data editor in its own right.

GeeFu provides a central way of maintaining attribution of contribution as it regularly and automatically moves data into and from the github repo from the other tools, keeping track of who provided what. 

## Talk Application Abstract

Ash dieback is a lethal disease of ash trees that is rampaging its way through Europe.  This emergent pathogen has received little study in the past and its effect threatens to overwhelm the ash population. In response to this in late 2012 we produced some initial genomics datasets and took the unusual step of releasing them to the scientific community for analysis without first performing our own. In this manner we have been able to ‘crowdsource’ analyses and bring the expertise of the community to bear on this problem as quickly as possible. In this talk I'll describe how we've started to use 'mash-ups' of GMOD and other OpenSource tools like Web Apollo, wiki engines, BLAST servers and Mozilla OpenBadges to capitalise on the crowd and build a community-centric way of generating genomic analysis.



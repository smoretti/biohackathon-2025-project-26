---
title: 'BioHackEU25 Report for Project 26: Tools to develop constraint-based models in R: adapting existing toolboxes'
title_short: 'BioHackEU25 #26: Constraint-based models in R'
tags:
  - cheminformatics
  - constraint-based models
authors:
  - name: Jesubukade Ajakaye
    affiliation: 1
    orcid: 0000-0002-8966-4422
    role: BioHacker
  - name: Mihail Anton
    affiliation: 2
    orcid: 0000-0002-7753-9042
    role: BioHacker
  - name: Iván Domenzain
    affiliation: 3
    orcid: 0000-0002-5322-2040
    role: BioHacker
  - name: Tanisha Malpani
    affiliation: 4
    orcid: ???
    role: BioHacker
  - name: Sébastien Moretti
    affiliation: 5
    orcid: 0000-0003-3947-488X
    role: BioHacker
  - name: Rahuman Sheriff
    affiliation: 6
    orcid: 0000-0003-0705-9809
    role: BioHacker
  - name: Maria Suarez-Diez
    affiliation: 7
    orcid: 0000-0001-5845-146X
    role: BioHacker
affiliations:
  - name: Federal Polytechnic Ayede, Ayede, Ogbomosho, Oyo State, NG
    ror: 03ye8kt44
    index: 1
  - name: ELIXIR Europe
    ror: 044rwnt51
    index: 2
  - name: ???
    ror: ???
    index: 3
  - name: University of Helsinki, Computational Systems Medicine, FI
    ror: 040af2s02
    index: 4
  - name: SIB Swiss Institute of Bioinformatics, Vital-IT group, Lausanne, CH
    ror: 002n09z45
    index: 5
  - name: EMBL's European Bioinformatics Institute, BioModels, UK
    ror: 02catss52
    index: 6
  - name: Wageningen University & Research, Laboratory of Systems and Synthetic Biology, NL
    ror: 04qw24q55
    index: 7
date: 7 November 2025
cito-bibliography: paper.bib
event: BH25EU
biohackathon_name: "BioHackathon Europe 2025"
biohackathon_url:   "https://biohackathon-europe.org/"
biohackathon_location: "Berlin, Germany, 2025"
group: Project 26
# URL to project git repo --- should contain the actual paper.md:
git_url: https://github.com/biohackrxiv/publication-template
# This is the short authors description that is used at the
# bottom of the generated paper (typically the first two authors):
authors_short: Jesubukade Ajakaye \emph{et al.}
---


# Introduction

As part of the BioHackathon Europe 2025, we here report on the progress of the hacking team
preparing tools to develop constraint-based models in the R language for Statistical Computing
for the Systems Biology community. This preliminary development relies on the adaptation of
existing toolboxes.

Constraint-based modeling is a framework to model reaction fluxes in genome-scale metabolic
network models. Genome scale models have uses in fundamental and applied questions relevant to
biotechnology, microbiology and biomedicine. Constraint-based modeling provides a scalable
framework to analyze large-scale models and to associate genome potential and metabolic reactions.

Currently, libraries to simulate these models are available in general-purpose languages such as
Matlab ([COBRA Toolbox](https://opencobra.github.io/cobratoolbox/stable/index.html)), Python ([COBRApy](https://opencobra.github.io/cobrapy/) 2013, last release 2023), Julia ([COBREXA](https://github.com/COBREXA/COBREXA.jl) 2025) or R
(Sybil 2013, unmaintained). There are also methods for model development and curation in Matlab
([RAVEN toolbox](https://sysbiochalmers.github.io/RAVEN/)), Python ([CarveMe](https://carveme.readthedocs.io/en/latest/) 2018, last release 2023) or Java (Merlin, KBase). However,
currently there lacks an up-to-date R implementation of methods for model development and curation.

In this project, we proposed the (re)development of an R based framework for developing and
simulating constraint-based models. We proposed to expand the Sybil library for model simulation
with the functionalities for model reconstruction and analysis available in the widely used RAVEN
toolbox in Matlab. The outcome will facilitate constraint based modelling to experimental scientists,
thereby contributing to bridge the gap between data users and data generators. It will also be
more FAIR by being usable with non-proprietary software, and align with software best practices as
collected by the [ELIXIR Tools Platform](https://elixir-europe.org/platforms/tools). We will work towards increased reproducibility by also
considering implementation of [FROG analysis](https://www.biorxiv.org/content/10.1101/2024.09.24.614797) in R. Moreover, as a tool developed by the [ELIXIR Systems
Biology Community](https://elixir-europe.org/communities/systems-biology) for the wider community, the long-term maintenance burden is spread across a wider
membership.

Two weeks before the BioHackathon, we discovered a tool in R allowing the simulation of models,
called cobrar (https://github.com/Waschina/cobrar). We have then decided to rely on the cobrar code
base to expand it. We have started a collaboration with the main cobrar developer Silvio Waschina
from the Kiel University, Germany.


# Material and Methods

The following is a brief introduction of the components, linked data sources and analysis
approaches we used.


# Results


# Discussion


# Outlook


# Acknowledgements


# References

You can use [CiTO](http://purl.org/spar/cito/2018-02-12) annotations, as explained in [this BioHackathon Europe 2021 write up](https://raw.githubusercontent.com/biohackrxiv/bhxiv-metadata/main/doc/elixir_biohackathon2021/paper.md) and [this CiTO Pilot](https://www.biomedcentral.com/collections/cito).
Using this template, you can cite an article and indicate _why_ you cite that article, for instance DisGeNET-RDF [@citesAsAuthority:Queralt2016].

The syntax in Markdown is as follows: a single intention annotation looks like
`[@usesMethodIn:Krewinkel2017]`; two or more intentions are separated
with colons, like `[@extends:discusses:Nielsen2017Scholia]`. When you cite two
different articles, you use this syntax: `[@citesAsDataSource:Ammar2022ETL; @citesAsDataSource:Arend2022BioHackEU22]`.

Possible CiTO typing annotation include:

* citesAsDataSource: when you point the reader to a source of data which may explain a claim
* usesDataFrom: when you reuse somehow (and elaborate on) the data in the cited entity
* usesMethodIn
* citesAsAuthority
* citesAsEvidence
* citesAsPotentialSolution
* citesAsRecommendedReading
* citesAsRelated
* citesAsSourceDocument
* citesForInformation
* confirms
* documents
* providesDataFor
* obtainsSupportFrom
* discusses
* extends
* agreesWith
* disagreesWith
* updates
* citation: generic citation


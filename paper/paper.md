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

As part of the BioHackathon Europe 2025, we here report...

## Meeting information

If you want to submit a preprint to BioHackrXiv, first check if your meeting is registered. You can find a list
of meetings [here](https://index.biohackrxiv.org/meetings). If your meeting is missing, please contact your meeting
organizers. The above list also provides information on the YAML fields with information about the meeting.

# Formatting

This document use Markdown and you can look at [this tutorial](https://www.markdowntutorial.com/).

## Subsection level 2

Please keep sections to a maximum of only two levels.

## Tables

Tables can be added in the following way, though alternatives are possible:

```markdown
Table: Note that table caption is automatically numbered and should be
given before the table itself.

| Header 1 | Header 2 |
| -------- | -------- |
| item 1 | item 2 |
| item 3 | item 4 |
```

This gives:

Table: Note that table caption is automatically numbered and should be
given before the table itself.

| Header 1 | Header 2 |
| -------- | -------- |
| item 1 | item 2 |
| item 3 | item 4 |

## Figures

A figure is added with:

```markdown
![Caption for BioHackrXiv logo figure](./biohackrxiv.png)
```

This gives:

![Caption for BioHackrXiv logo figure](./biohackrxiv.png)

Figures can be scaled by adding the width or height to the Markdown like this:

```markdown
![Caption for BioHackrXiv logo figure](./biohackrxiv.png){ width=50px }
```

# Other main section on your manuscript level 1

Lists can be added with:

1. Item 1
2. Item 2

# Citation Typing Ontology annotation

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


# Results


# Discussion

...

## Acknowledgements

...

## References

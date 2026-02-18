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
preparing tools to develop constraint-based models in R for the Systems Biology community.
This preliminary development relies on the adaptation of existing toolboxes.

Constraint-based modeling is a framework to model reaction fluxes in genome-scale metabolic
network models. Genome scale models have uses in fundamental and applied questions relevant to
biotechnology, microbiology and biomedicine. Constraint-based modeling provides a scalable
framework to analyze large-scale models and to associate genome potential and metabolic reactions.

Currently, libraries to simulate these models are available in general-purpose languages such as
Matlab ([COBRA Toolbox](https://opencobra.github.io/cobratoolbox/stable/) [@citation:Heirendt2019]), Python ([COBRApy](https://opencobra.github.io/cobrapy/) 2013, last release 2025 [@citation:Ebrahim2013]), Julia ([COBREXA](https://github.com/COBREXA/COBREXA.jl) 2025 [@citation:Kratochvil2025]) or R
(Sybil 2013, unmaintained [@citation:Gelius2013]). There are also methods for model development and curation in Matlab
([RAVEN toolbox](https://sysbiochalmers.github.io/RAVEN/) [@citation:Wang2018]), Python ([CarveMe](https://carveme.readthedocs.io/en/latest/) 2018, last release 2025 [@citation:Machado2018]) or Java (Merlin [@citation:Capela2022], KBase [@citation:Arkin2018]). However,
currently there lacks an up-to-date R implementation of methods for model development and curation.

In this project, we proposed the (re)development of an R based framework for developing and
simulating constraint-based models. We proposed to expand the Sybil library for model simulation
with the functionalities for model reconstruction and analysis available in the widely used RAVEN
toolbox in Matlab. The outcome will facilitate constraint based modelling to experimental scientists,
thereby contributing to bridge the gap between data users and data generators. It will also be
more FAIR by being usable with non-proprietary software, and align with software best practices as
collected by the [ELIXIR Tools Platform](https://elixir-europe.org/platforms/tools). We will work towards increased reproducibility by also
considering implementation of **FROG analysis** [@citation:Karthik2024] in R. Moreover, as a tool developed by the [ELIXIR Systems
Biology Community](https://elixir-europe.org/communities/systems-biology) [@citation:Martins2022] for the wider community, the long-term maintenance burden is spread across a wider
membership.

Two weeks before the BioHackathon, we discovered a new tool in R allowing the simulation of models,
called **cobrar** (https://github.com/Waschina/cobrar). Which calls for an assessment of its current
state and definition of new development areas.


# Material and Methods

The following is a brief introduction of the tasks, linked tools and analysis
approaches we used.

1. Collectively define project goals

   Define short term (the BioHackathon week), and long term (after the BioHackathon) goals.

2. Evaluate existing tools

   Already a number of tools exist: what are their utilities, status, advantages...

   Here is a short list:
   - https://github.com/Waschina/cobrar
   - https://bioconductor.org/packages/release/bioc/html/SBMLR.html
   - https://bioconductor.org/packages/release/bioc/html/rsbml.html
   - https://github.com/bacpop/SBMLtoOdin

3. Understand the functionalities of **cobrar**

   Functionalities and capabilities of **cobrar**: understand the
   functions that are included and evaluate how do they relate to COBRApy.

   Determine the minimal amount of additions needed to ensure basic functionality that
   serves as a basis for future incorporation of model reconstruction algorithms/frameworks.

4. Understand the model structure in **cobrar**

   Get a full understanding of the information that is kept or discarded by **cobrar**, starting from
   a model in the SBML [@citation:Keating2020] format, with R console and R studio:
   - Which fields are stored?
   - Which fields are discarded?
   - Which fields are needed to be incorporated?
   - How are fields represented in **cobrar** (variable types)?

5. Streamline operation of **cobrar** for Windows users

   Some biologists rely on Windows machines. To be able to be used by most users in the community,
   our tools have to be runnable on Windows machines.

   Some attempts have been done on Windows machines. We will try to reproduce what other developers
   have contributed in our own Windows machines.

   Document our process for reproducing them and report any missing or custom steps.

   In parallel, test cross compilation using [conda](https://conda.io) from Linux to Windows.

6. Explore reference models in **cobrar**

   Try to load, simulate and manipulate highly used models (*E. coli*, yeast-GEM, Human-GEM) using
   **cobrar** (R console and R studio):
   - Human-GEM (v1.19.0)
   - yeast-GEM (v9.0.2)
   - *E. coli* GEM
   - Model of *C. oleaginosus* included

   Detect any issues, solve and document them.

7. Integrate in Galaxy

   Discuss with Galaxy people present at the BioHackathon about how to integrate an (our) R tool in Galaxy.

8. Implement FROG in **cobrar**

   Implement FBA, FVA, gene del and rxn del using **cobrar**.

   Get the results as **OMEX** [@citation:Bergmann2014] file, if possible, for a FROG integration.

9. Test any changes / new models with GitHub actions

   Test the CODEX AI code generation tool, to create **cobrar** pull requests.

   Those pull requests cover **cobrar** unit function tests, implemented as GitHub actions.

   Evaluate those CODEX pull requests to see if they make sense, and how to correct
   and integrate them.

10. Plug-in the Gurobi solver in **cobrar**

    **cobrar** uses the GLPK solver, and provide a plugin for the CPLex solver.

    Evaluate how to add a plugin for the Gurobi solver.

11. Register in bio.tools

    Discuss with the bio.tools people present at the BioHackathon to register **cobrar** in bio.tools.

12. Integrate in Bioconductor

    Discuss with the Bioconductor people present at the BioHackathon to integrate **cobrar** in Bioconductor.


# Results

1. Collectively define project goals

   The hacking team has collectively defined the project goals, for the short term (the BioHackathon week), and for
   the long term (after the BioHackathon), integrating capabilities, availabilities, wills and choices of each member.

2. Evaluate existing tools

   Among the existing tools, some have very limited features (e.g. only load SBML files), some are not updated for a
   while, and some are dedicated to ODE models and not to genome scale models.

   [cobrar](https://github.com/Waschina/cobrar) looks to have several advantages and to be well
   maintained. We have then decided to rely on the **cobrar** code base, and to expand it. We have then started
   a collaboration with the main **cobrar** developer, Silvio Waschina, from the Kiel University, Germany.

   **cobrar** is a re-coding of the Sybil [@citation:Gelius2013] library for model simulation, as we planned to do at the start of the project.

3. Understand the functionalities of **cobrar**

   This first evaluation of **cobrar** allowed us to spot some lacking features and errors:
   - Exchange reactions functions did not work well
   - Export only to SBML. Additional JSON export would be handy (to combine with Escher or other visualizations)

   At that step, we forked the **cobrar** repository to work on branches and submit independent pull requests to Silvio.

   Silvio acted on pull requests and issues opened on the main **cobrar** repository.

4. Understand the model structure in **cobrar**

   Starting from SBML, the model structure has been evaluated in **cobrar**.

   The model structure looks complete, and fulfills all our requirements, e.g. stoichiometry in biochemical reactions.

   On the long term, we wonder if an effort should be engaged to align/harmonize names of functions between different
   cobra toolboxes.

5. Streamline operation of **cobrar** for Windows users

   Some people in the hacking team have tested available instructions to install and run **cobrar** on Windows.

   **cobrar** is pure R code, but the solver and libSBML parts are not. It was tricky to link R, **cobrar**, libSBML and the solver.

   The team succeeded and updated instructions were added in the **cobrar** repository.

   The cross compilation using conda, from Linux to Windows, failed. The conda channels look too different between Linux
   and Windows to cross compile easily.

6. Explore reference models in **cobrar**

   The load of highly used models (*E. coli*, yeast-GEM, Human-GEM) of different size and complexity showed that
   **cobrar** can deal with models very efficiently. For example, the Human-GEM model, one of the largest with 13000
   reactions, was loaded in about 13 seconds.

   While loading and testing models, some issues were found:
   - FBA says it optimizes successfully even if there is no objective function
   - *C. oleaginosus* model (included in the repository) is loaded and optimized successfully, but the reporting fails.
     Identification of Exchange reactions is based on the name "EX_" this model does not follow this convention.
   - If model file is not found, the `readSBMLmod` function makes R crash.

   Those issues were documented, reported and are now solved.

7. Integrate in Galaxy

   After talking with Galaxy people present at the BioHackathon, we learnt that a function that you wish to expose in Galaxy has certain limitations:
   - The function's arguments must include the names of its input and output files (function return values are ignored).
   - Any error conditions should be handled with stop with a useful/informative error message. The Galaxy user will see these messages if an error occurs.
   - Functions which take datasets as input should accept as arguments the filenames pointing to those datasets. The Galaxy user interface will allow the user to choose the dataset graphically.
   - Return values of functions are ignored. Function output should be written to one or more files, and the names of these files should be passed into the function as arguments.
   - Functions should be documented with a manual page. Galaxy will use this manual page to fill in relevant sections of the Galaxy XML file. The following sections of the man page are required:
      - alias
      - title
      - description
      - arguments - each argument must be documented
      - details
   (source: https://www.bioconductor.org/packages//2.11/bioc/vignettes/RGalaxy/inst/doc/RGalaxy-vignette.pdf)

   There are two options for implementation in Galaxy:
   - An interactive tool in this context is perfectly possible to have an interactive R Studio or Jupyter notebook arranged from which to run scripts, tools whatever. A possibility is to set up an environment with pre-installed **cobrar**.
   - Integration as tools: check CobraXy as it incorporates COBRApy for galaxy.

8. Implement FROG in **cobrar**

   FROG analysis is a community-driven initiative for standardizing reproducibility assessments of constraint-based and genome-scale metabolic models.

   Implementation of the FROG analysis would make it easier for users to submit their models to the [BioModels](https://biomodels.net/) repository.

   FROG analysis has been implemented. It can be called either for an R model object `ModelOrg` or for a path pointing to an SBML file.

   ```R
   library(cobrar)

   frog("iML1515.xml.gz") # for an SBML file

   # or for a "ModelOrg" object

   mod <- readSBMLmod("iML1515.xml.gz")
   frog(mod)
   ```

   Few things have to be considered for further improvements:
   - OMEX archive export is currently not implemented.
   - The metadata.json is missing the field for the sha256 checksum. This is because the R function `utils::sha256sum` was introduced in R quite recently, and it is not available for R versions < 4.5. Since we would like to make **cobrar** also available for the 'latest minus one' version of R, we decided to omit the sha256 checksum for now.
   - The example in the function documentation is not perfect. A better example has to be found.

9. Test any changes / new models with GitHub actions

   The CODEX AI code generation tool was evaluated to test expected results of **cobrar** functions. And generate automatically corresponding pull requests.

   The CODEX AI code was quite good, but needed to be rechecked and extended to fully cover the functions. But this is a good start to draft tests.

   Some tests have been fixed, mainly because toy and dead-end models were too simple.

   Other tests fail because of possible **cobrar** issues.

   All of them are now corrected and integrated in the **cobrar** distribution.

10. Plug-in the Gurobi solver in **cobrar**

    Most people in the hacking team use [Gurobi](https://www.gurobi.com/) as solver, but it is not available in the **cobrar** distribution.

    We have evaluated the current CPLex linker to convert it to Gurobi: for example, a wrapper mimicking the CPLex plugin, but using the Gurobi R package.

    Due to the lack of time, this task has been postponed.

11. Register in bio.tools

    After talking with bio.tools people present at the BioHackathon, we have added a **cobrar** entry in bio.tools.

    Sylvio took back the ownership.

12. Integrate in Bioconductor

    After talking with Bioconductor people present at the BioHackathon, a Bioconductor looks complicated for Mac and Windows OS.

    One point to keep in mind concerning portability to macOS is that brew has to be avoided. There are too many potential conflicts of binary interfaces. https://mac.r-project.org/bin/darwin20/arm64/ has GLPK and libSBML compiled for Apple Silicon Macs and these would be used if we would like to see **cobrar** in Bioconductor. An installation is possible, but people have to fiddle with Makevars a bit, and this is not for common people.


# Discussion

During the pre-sessions we had before the BioHackathon, it was quite clear that the initial idea of developing a tool for constraint-based models in R, based on Sybil, was outdated with the discovery of **cobrar**.
**cobrar** looked to cover all our basic requirements, and the BioHackathon project has been shifted to a deeper **cobrar** evaluation and testing, and an extension of its code base.
Silvio Waschina, from the Kiel University, Germany, joined remotely the project, even if too late to register, and issues, updates and reports were shared to work together.

**cobrar** was evaluated and tested on different platforms, i.e. OS and R environments. Some tests showed issues when the model file was not found, or when the model does not contain an objective function. The identification of exchange reactions has been fixed, in sync with the expected result tests drafted by an AI tool. Now, GitHub actions test automatically any modifications of basic **cobrar** functions. The Windows installation has been deeply tested, and is now formally described in the **cobrar** documentation.

**cobrar** has been registered in bio.tools, and is now integrated with FROG to ensure the reproducibility of Genome Scale Metabolic Models. The BioHackathon discussions opened the integration of **cobrar** in Galaxy in a near future, and a plan for a Gurobi solver plugin.


# Outlook

We will continue to help Silvio Waschina and his team for the development of the **cobrar** tool because the Systems Biology community needs such a tool. Some people program only in R, and **cobrar** allows to avoid jumping between tools written in different programming languages, often complicated to install and run. A wiki on the **cobrar** repository space should be deployed to share documents, ideas and feedbacks by the community.
The hacking team is now engaged in a review writing and will continue to collaborate.


# Acknowledgements

This work was performed during the ELIXIR BioHackathon Europe 2025, organized by ELIXIR in November 2025.
We thank all people we met during the BioHackathon, remotely or face to face, for fruitful discussions.


# References



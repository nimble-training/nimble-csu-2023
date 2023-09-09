# nimble-csu-2023
Materials for the NIMBLE short course at the enviBayes workshop at Colorado State University, September 18, 2023

To prepare for the workshop:

 - Install NIMBLE (see below)
 - Install additional packages (see below)
 - Download these materials (and check back before the workshop on Monday for updates)

All materials for the workshop will be in this GitHub repository. If you're familiar with Git/GitHub, you already know how to get all the materials on your computer. If you're not, simply click [here](https://github.com/nimble-training/nimble-csu-2023/archive/refs/heads/main.zip).

There is some overview information [here (https://htmlpreview.github.io/?https://github.com/nimble-training/nimble-csu-2023/blob/main/overview.html), including links to the content modules in order.

## Schedule

Modules:

1. [Introduction to NIMBLE: Basic concepts](content/introduction_to_nimble.html)
2. Comparing and customizing MCMC methods in NIMBLE
3. User-defined distributions and functions in models
4. Programming algorithms

## Help with NIMBLE

Our user manual is [here](https://r-nimble.org/html_manual/cha-welcome-nimble.html).

We have a 'cheatsheet' and a guide to converting from JAGS or WinBUGS to NIMBLE [here](https://r-nimble.org/documentation).


## Installing NIMBLE

NIMBLE is an R package on CRAN, so in general it will be straightforward to install as with any R package, but you do need a compiler and related tools on your system.  

In summary, here are the steps.

1. Install compiler tools on your system. [https://r-nimble.org/download](https://r-nimble.org/download) has more details on how to install *Rtools* on Windows and how to install the command line tools of *Xcode* on a Mac. Note that if you have packages requiring a compiler (e.g., *Rcpp*) on your computer, you should already have the compiler tools installed.

2. Install the *nimble* package from CRAN in the usual fashion for an R package. More details (including troubleshooting tips) can also be found in Section 4 of the [NIMBLE manual](https://r-nimble.org/html_manual/cha-installing-nimble.html).

3) To test that things are working please run the following code in R:

```
library(nimble)
code <- nimbleCode({
  y ~ dnorm(0,1)
})
model <- nimbleModel(code)
cModel <- compileNimble(model)
```

4) Install the `nimbleHMC` package from CRAN in the usual fashion for an R package.

If that runs without error, you're all set. If not, please see the troubleshooting tips and email nimble.stats@gmail.com directly if you can't get things going.  

In general we encourage you to update to the most recent version of NIMBLE, 1.0.1 and of nimbleHMC, 0.2.0.

## RStudio and R Markdown

We'll present most of the material from within RStudio, using R Markdown documents with embedded R code. R Markdown is an extension to the Markdown markup language that makes it easy to write HTML in a simple plain text format.  This allows us to both run the R/NIMBLE code directly as well as compile on-the-fly to an HTML file that can be used for presentation. 

Note: The files named *foo.html* have individual slides, while the files named *foo_alt.html* have the same content but all on one page.


## Accessing the materials via Git

### Within RStudio

Within RStudio go to `File->New Project->Version Control->Git` and enter:

- "Repository URL": https://github.com/nimble-training/nimble-csu-2023
- "Project Directory Name": nimble-csu-2023 (or something else of your choosing)
- "Directory": ~/Desktop (or somewhere of your choosing)

Then to update from the repository to get any changes we've made, you can select (from within RStudio):
Tools->Version Control->Pull Branches

or from the Environment/History/Git window, click on the Git tab and then on the blue down arrow.

Be warned that you probably do not want to make your own notes or changes to the files we are providing. Because if you do, and you then do a "Git Pull" to update the materials, you'll have to deal with the conflict between your local version and our version. You probably will want to make a personal copy of such files in another directory or by making copies of files with new names.

### From a terminal window

Run the following commands:

- `cd /directory/where/you/want/repository/located`
- `git clone https://github.com/nimble-training/nimble-csu-2023`

Then to update from the repository to get any changes we've made:

- `cd /directory/where/you/put/the/repository/nimble-csu-2023`
- `git pull`

# The Legal Stuff

- This material was created by the NIMBLE development team and is licensed under a Creative Commons Attribution 3.0 Unported License. You are free to use, modify, and redistribute any of this material with attribution.

- NIMBLE is/has been supported by NSF grants DBI-1147230, ACI-1550488, and DMS-1622444, with additional support provided by postdoctoral funding for D. Turek from the Berkeley Institute for Data Science and Google Summer of Code fellowships for N. Michaud (2015) and C. Lewis-Beck (2017).

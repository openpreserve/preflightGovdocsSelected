#Results of analysis GovDocs selected corpus with Apache Preflight

##About
This repo contains the output of an analysis of all *PDF* documents in the [*GovDocs selected* test corpus](http://www.openplanetsfoundation.org/blogs/2012-07-26-1-million-21000-reducing-govdocs-significantly) with the [*Preflight*](http://pdfbox.apache.org/cookbook/pdfavalidation.html) component of the [*Apache PDFBox*](http://pdfbox.apache.org/) library. Created by Johan van der Knijff, [KB / National Library of the Netherlands](http://www.kb.nl/en).

##Contents
The repo contains the following files and directories:

* **goGovdocsSelected.sh** - bash script that was used to run the analysis. The variables *validateCommand*, *countCommand* and *schema* refer to files in this [PDF policy-based validation demo](https://github.com/openplanets/pdfPolicyValidate)
* **index.csv** - comma-separated text file that links each *PDF* in *GovDocs selected* to its respective *Preflight* and *Schematron* output file. You may need to replace */usr/local/SCAPE/data* with the actual path where the *GovDocs selected* is located on your system.
* **outRaw** - this directory contains the raw *Preflight* and *Schematron* output files. Use *index.csv* (see above) to link each *PDF* to its respective  *Preflight* / *Schematron* file.
* **success.csv** - comma-separated text file that gives the outcome of the policy-based validation (*Pass* or *Fail*)
* **failed.csv** - contains text descriptions of the failed *Schematron* assertions (this is really ugly and you probably shouldn't be using this file anyway!)
* **preflightErrorCounts.csv** - comma-separated text file with the *unique*[^1] counts of each *Preflight* error (i.e. the number of *PDF*s for which each error was reported).
* **failedAssertCounts.csv** - comma-separated text file with the *unique* counts of each failed *Schematron* assertion (i.e. the number of *PDF*s for which each assertion failed).

[^1]: Here, *unique* means that if, for example, one *PDF* produced 5 instances of error "3.1.3", this only contributes an amount of 1 to the count for this error. Thus, a value of *4491* simply means that this error was reported for 4491 *PDF*s.

##More information
For a discussion of these results see [this post on the Open Planets Foundation blog]().

##License
Contents of this repo released under [CC-BY](http://creativecommons.org/licenses/by/3.0/) license.

##Funding
This work was partially supported by the [SCAPE](http://www.scape-project.eu/) Project. The SCAPE project is co-funded by the European Union under FP7 ICT-2009.4.1 (Grant Agreement number 270137).

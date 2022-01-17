# MSR_II : Data Collection
**Note: This is a reproduction project as part of the MSR course 2021/22 at UniKo, CS department, SoftLang Team**

## Names of team/members

**Team:** Romeo

**Members:** Aishwarya Saravanan, Emmanouil Georgios Lionis, Prem Kumar Karki 

## Baseline study :

**Aspect:** Mine the APIs from the repositories by using the filters specified in the thesis paper and try to reproduce the dataset generated in the paper and compare it with the original dataset produced in the thesis.

**Input data:** We will collect data from GitHub repositories in Java language which uses Apache Maven.

**Output data:** Output data will be a Dataset with the top APIs which is available for further analysis.

## Findings of replication :

**Process delta:** Our process is same as the thesis paper repository and try to produce same result as the original repository.
**Output delta:** The result which we got after the process is slightly different than the original. From total of 19911 Java repositories, We collected 4286 repositories after applying the filter with at least 100 stars, one POM file, 2 contributors and 100 commits, which is slightly more than the original repository(4018). The number of dependencies, we got 36896 where as the origianl repository had 43,998. 


## Implementation of replication with subsections as follows:

**Hardware requirements:** (incl. OS) for running your process.

**Software requirements:** regarding frameworks, tools, etc. required for running your process.

**Validation:** Any sort of advice on how to check that the output of your process makes sense.

**Data:** What input, output, or temporary data is assumed or produced by your process? 

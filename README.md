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
 
### Process delta:
 Our process is same as the thesis paper repository and try to produce same result as the original.

### Output delta:
 The result which we got after the process is slightly different than the original. From total of 19911 Java repositories, We collected 4286 repositories after applying the filter with at least 100 stars, one POM file, 2 contributors and 100 commits, which is slightly more than the original repository (4018).  We were able to collect the 2780 repositories with 36896 dependencies whereas the original paper repository had 3547 repositories with 43,998 dependencies.  We got the 191 MCR Tag contain repositories with 87 MCR dependency whereas the original repository 3532 repositories with 29005 MCR Tags. 

###Problem delta:
While doing the replication of the repository we have faced the different problem which also reason that our result is different than the original repository result.
-Permission Issue: many of the git repositories is not able to access while running process which through error. 
 <center style="padding: 40px"><img width="70%" src="https://github.com/AishwaryaSar/MSR_datacollection/blob/main/data/Image/permision.jpg" title="permision error" /> </center>
-Error while reading POM file: After the collection of repositories fit the requirement process try to collected the dependency from the POM file. During the this process error like **Unrecognised tag** in many repositories POM file. <center style="padding: 40px"><img width="70%" src="https://github.com/AishwaryaSar/MSR_datacollection/blob/main/data/Image/error2.jpg" title="Unrecognised Tag" /> <img width="70%" src="https://github.com/AishwaryaSar/MSR_datacollection/blob/main/data/Image/error3.jpg" title="Unrecognised Tag" /></center>
-response 403: We got the refuse to authorize from the most of the repositories while collecting MCR tags  from the [Maven central repository](https://mvnrepository.com/artifact/). <center style="padding: 40px"><img width="70%" src="https://github.com/AishwaryaSar/MSR_datacollection/blob/main/data/Image/connectionerror.jpg" title="Error 403" /> </center> 

 
## Implementation of replication :

###Hardware requirements: 
OS : Windows (Used for process), MscOS, Linux (any OS in this would work)
Minimum RAM : 4GB 
Minimum Storage : As the output is a collection of CSV files, 
**Software requirements:** We used the software Eclipse or any ide that can execute maven projects in java language. The Java must be the 11th edition. (Java 11). Also, there is need of a GitHub access token in the file RepositoriesPicker.java. In other words, you have to replace the USERNAME_AND_TOKEN in with your username and token.
 
**Validation:** Any sort of advice on how to check that the output of your process makes sense.
 
**Data:** What input, output, or temporary data is assumed or produced by your process?

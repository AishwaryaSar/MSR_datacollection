# MSR_II : Data Collection
**Note: This is a reproduction project as part of the MSR course 2021/22 at UniKo, CS department, SoftLang Team**
 
## Names of team/members
 
**Team:** Romeo
 
**Members:** Aishwarya Saravanan, Emmanouil Georgios Lionis, Prem Kumar Karki 
 
## Baseline study :
 
**Aspect:** Mine the APIs from the repositories by using the filters specified in the thesis paper and try to reproduce the dataset with the collected repositories. 
 
**Input data:** Collected data from GitHub repositories in Java language which uses Apache Maven. 
 
**Output data:** Dataset with the filtered repositories which is available for further analysis. 
 
## Findings of replication :
 
### Process delta:
 Process is same as described in the thesis paper repository. The same types of filters used to gather the repositories are used, as described in the thesis paper.  

### Output delta:
 ** The result which we got after the process is slightly different than the thesis paper repository. From the total of 19911 Java repositories, after applying the filter with at least 100 stars, one POM file, 2 contributors and 100 commits, we collected 4286 repositories, which is slightly more than the original results (4018).  Out of this, we were able to collect 2780 repositories with 36896 dependencies whereas the original paper repository had 3547 repositories with 43,998 dependencies.  We were able to collect 191 MCR Tag containing repositories with 87 MCR dependencies whereas the original repository had 3532 repositories with 29005 MCR Tags.  

### Problem delta:
While performing the replication of the repository we faced technical errors which is also a reason for our result being different from the original repository result.
- **Permission Issue:** Ran into authentication issues with various git repositories. As we were unable to access many repositories, our results might be different from the original described result. 
 <center style="padding: 40px"><img width="70%" src="https://github.com/AishwaryaSar/MSR_datacollection/blob/main/data/Image/permision.jpg" title="permision error" /> </center>

- **Error while reading POM file:** After the collection of repositories fit the requirement process try to collected the dependency from the POM file. During the this process error like **Unrecognised tag** in many repositories POM file. <center style="padding: 40px"><img width="70%" src="https://github.com/AishwaryaSar/MSR_datacollection/blob/main/data/Image/error2.jpg" title="Unrecognised Tag" /> <img width="70%" src="https://github.com/AishwaryaSar/MSR_datacollection/blob/main/data/Image/error3.jpg" title="Unrecognised Tag" /></center>

- **response 403:** We got the refuse to authorize from the most of the repositories while collecting MCR tags  from the .[Maven central repository](https://mvnrepository.com/artifact/). <center style="padding: 40px"><img width="70%" src="https://github.com/AishwaryaSar/MSR_datacollection/blob/main/data/Image/connectionerror.jpg" title="Error 403" /> </center> 

 
## Implementation of replication :

### Hardware requirements: 
OS : Windows (Used for process), MscOS, Linux (any OS in this would work)
Minimum RAM : 4GB 
Minimum Storage : As the output is a collection of CSV files, minimum of 500MB - 1GB should be suitable 
### Software requirements: 
We used the Eclipse IDE for processing Java files. Any IDE that can execute maven projects in Java language would be suitable for this. The version of Java must be the 11th edition (Java 11). Also, there is need for a GitHub access token in the file RepositoriesPicker.java file. In other words, one has to replace the USERNAME_AND_TOKEN in the file with the generated username and token from Github.

For running the python files we used Visual Studio Code. Any suitable IDE that can run python files, should also be suitable. (Python 3.9.6)
 
**Validation:** 
 1. The collection of repositories and analysis of dependencies step uses the Application.java, RepositoriesPicker.java, Utils.java, RepositoryManager.java, and the DependenciesManager.java. 
 2. Once the Java program is run as a Maven program with Application.java as the main class, the application starts collecting the repositories, performs analysis and produces CSV files as data output. 
 3. Based on the produced csv files, further analysis is performed using the dependencies_counter.py and utils.py files. 

Additional note : 
The processing of the java files for the collection of repositories, will take very long time(more than a day) due to crawling many repository and finding the repositories fit to requirement. To avoid oveloading the server, changes such as program sensible delay, the request which also increases the time frame of the process and assure normal dataflow in network can be made.


 **Data:** 
 
 1. The applicatin creates many log files while crawling and collecting the repositories. 
 2. The details regarding the selected repositories are generated as CSV files, which can be found under the repositories_selected folder in the data folder. 
 3. Furthermore, details regarding the repositories collected, repositories with dependencies, repositories with mcr tags, dependecies and dependeicies with mcr tags are all generated and collected as individual CSV files under the data folder. 
 4. Finally, the analysis performed on the dependecies collected, result in files that have details regarding dependencies, dependency pairs, dependecy sets, MCR tag sets, along with the similarity analysis. These CSV files can be found with the suffix of _counted_ and _similarity_ under the data folder. 


# Improvements   

After completing the assessment of the current reproducibility packages, it is possible to propose ways to increase the reproducibility of the paper. Creating improvements provides an opportunity to gain a more in-depth knowledge of the paper, including its methods, findings, and its overall contribution. In addition to this individual benefits, each contribution will be assessed by the ACRE community and can potentially be used by students and researchers around the world as an improved version of the reproducibility package for the paper.

As in the Assessment section, we recommend that you first focus on one specific output (e.g. “Table 1”). After completing the improvements to this first output, you will have a much easier time translating those improvements to other outputs.   

## Types of output-level improvements

### Add missing raw data files or meta-data (+RD) {#rd}

It is common that reproducjkhgvjhgtions packages do not include all the original [raw datasets](#describe-inputs). To obtain any missing raw data, or information about them, follow these steps:

   - 1 - Identify a specific missing file. During the [assessment stage](#assessment), you identified all data sources from the paper and appendices (column `data_source` in [this standarized spreadsheet](https://docs.google.com/spreadsheets/d/1LUIdVFH0OfR70C7z07TYeE-uWzKI_JIeWUMaYhqEKK0/edit#gid=0&range=A1)). However, some data sources (as delivered to the original investigators) might be missing one or more data files. You can sometimes find the specific name of those files by looking at the beginning of the cleaning code scripts. If you find the name of the file,  record it in the  `data_file` field of the [same spreadsheet](https://docs.google.com/spreadsheets/d/1LUIdVFH0OfR70C7z07TYeE-uWzKI_JIeWUMaYhqEKK0/edit#gid=0&range=A1) as above. If not, recorded as to “Some (or all) of the files used in the paper corresponding to the data source X”.      
   - 2 - Verify whether this file(s) can be easily obtained from the web.   
      - 2.1 - If yes: obtain the missing files and add them to the reproducibility package. Make sure to obtain permission to repost this data. See [tips for communication](#tips-for-communication) for a template email.   
      - 2.2 - If no: proceed to step 3.   
   - 3 - [Verify the ACRE database](ADD LINK) for previous attempts to contact the authors regarding this paper.  
   - 4 - Contact the original authors and kindly request the original materials. Be mindful of the authors’ time, and remember that the paper you are trying to reproduce was possibly  published at a time where standards for computational reproducibility were different. See [tips for communication](#tips-for-communication) for sample language on how to approach the authors.  
   - 5 - If the data sets are not available due to confidentiality or proprietary issues, the researcher conducting the reproduction can still improve the reproduction package by providing detailed  instructions, including contact information and possible costs, for future researchers to follow.
   
In additions to the efforts to obtain raw data, you can also contribute by obtainning missing analysis data.   

 
### Add missing analysis data files (+AD) {#ad}

[Analysis data](#describe-inputs) can be missing for two reasons: (i) raw data exists, but the procedures to transform it into analysis data are not fully reproducible, or (ii) some or all raw data is missing and some of all the analysis data is not included in the original reproduction package. To obtain any missing analysis data, follow these steps:

  - 1 - Identify the specific name of the missing data set. Typically this information can be found in some of the analysis code that calls such data in order to perform an analysis (eg `analysis_data_03.csv`).   
  - 2 - Verify that such data cannot be obtained by running the data cleaning code over the raw data.    
  - 3 - [Verify the ACRE database](ADD LINK) for previous attempts to contact the authors on this topic.    
  - 4 - [Contact the authors](#tips-for-communication) and request the specific data set.       

### Add missing analysis code (+AC) {#ac}

[Analysis code](#describe-inputs) can be added when there are analytic data files, but some or all the methodological steps are missing from the code. In this case, follow these steps:  

  - 1 - Identify the specific line/paragraph in the paper that describes the analytic step that is missing from the code (eg “we impute missing values to…,” or “we estimate this regression using a bandwidth of ...”).  
    
  - 2 - Identify the code file and the approximate line in the script where the analysis can be carried out. If no relevant code file is found, identify the location of the missing file relative to the steps in the [reproduction diagram](#diagram).   
  
  - 3 - [Verify the ACRE database](ADD LINK) for previous attempts to contact the authors on this issue.     
  
  - 4 - [Contact the authors](#tips-for-communication) nd request the specific code files.     
  
  - 5 - If no response from the authors, researchers reproducing the paper are encourage to attempt to recreate the analysis based on their interpretation of the paper, and filling in any missing piece by making explicit assumptions.   
    
### Add  missing data cleaning code (+CC) {#cc}  

[Data cleaning (processing)](#describe-inputs) code can be added when there are certain steps missing in the creation/re-coding of variables, merging, subsetting of the data sets, and other steps related to data cleaning and  processingResearchers conducting the reproduction should follow the same steps (1-5) as when adding missing analysis code.  

### Debug analysis code (DAC)  {#dac} 
  
Whenever any code is available in the reproduction package, reproducers should be able to debug those scripts. There are four types of debugging that you can add as part of the Improvements step:  

  - *Code cleaning:* instructions are simplified (e.g. by wrapping repetitive steps in a function or a loop) or redundant code is removed (eg. old code that was commented out), while keeping the original output intact.  
  - *Performance improvement:* instructions are replaced by other that perform the same tasks but take less time (eg. choosing one numerical optimization algorithm over another, but obtaining the same results).    
  - *Environment set up:* the code is modified to include correct paths to files, specific versions of software, and instructions to install missing packages or libraries.    
  - *Correcting errors:* a coding error will occur when a section in the code of the reproduction package executes a procedure that is in direct contradiction with the intended procedure expressed in the documentation (paper or comments of the code). For example, an error happens if the paper specifies that the analysis is performed on the population of males, but the code restricts the analysis to females only. Please follow the [ACRE procedure to report coding errors](ADD LINK).  


### Debug cleaning code (DCC)

Same as for analysis code, only separate for reporting purposes.  


### Reporting results    

Track all the different types of improvements implemented and record in [this standarized spreadsheet](https://docs.google.com/spreadsheets/d/1LUIdVFH0OfR70C7z07TYeE-uWzKI_JIeWUMaYhqEKK0/edit#gid=0&range=A3) of the assessment tool with the following structure:   

           Level-specific quality improvements: add data/code, debug code.

           | output_name | imprv | description_of_added_files        | lvl |
           |-------------|-------|-----------------------------------|-----|
           | table 1     | +AD   |        ADD EXAMPLES               |  5  |
           | table 1     | +RD   |        ADD EXAMPLES               |  5  |
           | table 1     | DCC   |        ADD EXAMPLES               |  5  |
           | figure 1    | +CC   |                                   |  6  |
           | figure 1    | DAC   |                                   |  6  |
           | inline 1    | DAC   |                                   |  8  |
           | ...         | ...   | ...                               | ... |  




##  Types of paper-level improvements {#paper-level}

In addition to the different levels of computational reproducibility described in the previous sections, there are at least  six additional that you can implement to improve the overall reproducibility of a paper. Such additional improvements can be applied across levels (including level 10).    

  - 1 - Set up the replication package using version control software (Git).
  - 2 - Improve documentation: add extensive comments to the code.
  - 3 - Integrate documentation with code: adapt the paper into a literate programming environment (eg: using Jupyter notebooks, RMarkdown, Stata Dynamic Doc).
  - 4 - Re-write the code from proprietary statistical software (eg Stata, Matlab) into an open-source statistical software (eg R, Python, Julia).
  - 5 - Re re-organize the reproduction materials into a set of folders and sub-folders that follow [standardized best practices](https://www.projecttier.org/tier-protocol/specifications/#overview-of-the-documentation), and add a master script that executes all the code in order and with no further modifications. [See AEA's reproduction template](https://github.com/AEADataEditor/replication-template).  
  - 6 - Set up a computing capsule that executes all the reproduction in the browser without the need to install any software. See for examples [Binder](https://mybinder.org/) and [Code Ocean](https://codeocean.com/).


### Reporting improvements  
Repoductors will be asked to provide this information in the [assessment and improvement survey](ADD LINK).   


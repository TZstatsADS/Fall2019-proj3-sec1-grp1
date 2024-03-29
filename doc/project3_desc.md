## STAT GU4243/GR5243 Fall 2019 Applied Data Science
### Project 3 Predictive analytics: model evaluation and selection

### -- for a facial emotion recognition task

In this project, we will carry out **model evaluation and selection** for predictive analytics on image data. As data scientists, we often need to **evaluate** different modeling/analysis strategies and decide what is the best. Such decisions need to be supported by sound evidence in the form of *model assessment, validation and comparison*. In addition, we also need to **communicate our decision and supporting evidence** clearly and convincingly in an accessible fashion.

#### Challenge
For this project, you will receive [a set of 2,500 facial images with 22 different emotions](https://drive.google.com/open?id=1K6KCo5fM-XfWbMamVQNuCSPUTBUuJ8nR)[require logged into Columbia LionMail in your browser]. Here is an alternative [data link](https://www.dropbox.com/s/kvi949ea1rey1d8/train_set.zip?dl=0). These two links lead to **identical** data. 

Your client is interested in creating an mobile AI program that **accurately recognizes the emotion from facial images**. 

The portability of this AI program (holding storage and memory cost) and the computational efficiency (test running time cost) are of great concern to your client. This translates to a balance between the complexity of variable/features/models used and the predictive performance. 

![image](predictiveprogram.png)

Assume that the **current practice** on your client side is just using [boosted](https://en.wikipedia.org/wiki/Boosting_(machine_learning)) [decision stumps](https://en.wikipedia.org/wiki/Decision_stump) on facial landmark features (see Tutorial for more detail). `R` pakcage [`gbm`](https://cran.r-project.org/package=gbm) can be used to implement this classifier. 

#### Evaluation criteria 
- Ease of reproducibility by the client (the instruction team)
	* are the codes for the proposed methods well annotated and documented?
	* can the analysis be re-run nearly automatically using the project's `main.rmd`.
- Level of reproducibility
	* Can client derive the same evaluation conclusion as presented in the team's final presentation?
	* How close are the reported performances (presentation and online) to the reproduced performances?
- Portability of proposed strategies
	* Computational speed for feature extraction and model training.
	* Computational speed for prediction.
	* Memory use for model training and prediction.
- Presentation and organization
	* Is the presentation convincing about the intuition of the proposed strategies?
	* Is it supported by adequate and appropriate evidence?
	* Is the GitHub organized and prepared in a way that makes it easier for readers to understand the proposed strategies and its advantages and limitations?

*(More details will be posted as grading rubrics in courseoworks/canvas)*

#### Project details

For this project, you are to carry out a business feasibility evaluation project that try to propose a **feasible** improvement over the current practice in terms of running cost (storage, memory and time) **and** prediction accuracy. 

##### Project time table.

- week 1 (Oct 9/10): introduction and project description
- week 2 (Oct 16/17): image processing and feature extraction
- week 3 (Oct 23/24): supervised learning and model assessment
- Final presentation (Oct 30/31)

##### Project learning support 

Each week, we will give a tutorial in class and having live discussion and brainstorm sessions. The instruction team will join team discussions during class and online. 


##### Final presentation
For presentation, the team should present their **proposal** for an improvement and support this proposal with evidence on 

- Performance improvement;
- Running cost tradeoff;
- Supporting evidence on why the proposed strategies make sense, such as intuitiveness of the selected features etc.

The presentation can be technical but need to be accessible to your peer students in our class. 

##### Platform requirement

Your client will evalaute your report on a single personal computer that has `R` installed and 16GB memory.  
 
+ Your feature processing needs to be reasonably efficient as you will have only 30 minutes to process 2,500 new images. 
+ Your `main.rmd` should 
	+ have a folder path as an input that point to the folder of training images. The folder will have the same structure as the training data released to you;
	+ and output a report on the performance of both the *baseline* and the *improved* models;
	+ if you use tools outside `R`, please provide detailed instruction on the installation and use of these tools. 

##### Reproducibility requirement

Each team should organize the project repo on GitHub according to the structure of the starter codes. 

```
data/
GitHub_proj/
├──doc/
├────main.RMD
├──figs/
├──lib/
├──output/
├──README.md
```
- In `data`, team members should individually save raw image data and a file that contains groundtruth labels for the images on their local computer. Currently there is a data folder with example hand-written zipcode images for the starter codes. You should **remove** it from your final repo. You shall **NOT** upload the images as these are copy-right protected materials. 
- The `doc` folder should have documentations for this project, presentation files and other supporting materials. You should have a final `main.RMD` following the template given in the starter codes. Your `main.RMD` can assume that there is a data folder of raw images outside the root with subfolders corresponding to the training set and the test set. 
- The `figs` folder contains figure files produced during the project and running of the codes. 
- (For R users) The `lib` folder contain R codes for the AI program. It should have the following files: `feature.R`, `train.R`, and `test.R`. The codes in the `lib` folder are not intended to be run directly but to be called from `main.RMD`. 
- The `output` folder is the holding place for feature extracted, other intermediate and final results.

The instructional team will download each team's GitHub repo and cross-examine each team's proposal for reproducibility on the current dataset and for reliability using a different dataset.


##### Working together
- Setup a GitHub project folder with everyone listed as contributor. Everyone clones the project locally and create a local branch. 
- The data is too big to be stored on GitHub. You can fork the repo to a local folder for this class or all your data science projects and have the data stored in "../data/" from root. Your project folder may look like

```
local proj/
├──data/
├──GitHub/
├── README
```
- The team can work with subgroups of 2-3 work together more frequently than the entire team. However, everyone should check in regularly on group discussion online and changes in the GitHub folder.  

##### Example starter codes

As example, you can find in the GitHub starter codes an example using handwritten zipcode data. We will give more examples during tutorials. 


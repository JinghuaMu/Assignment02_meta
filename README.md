# Assignment02_meta
BIOL6207 assignment2 about meta-analysis.  
## Document explanation

### OA_activitydat_20190302_BIOL3207.csv ###   
Raw data for ocean acidification research by Clark. et al  
columnHeading		description	  
-------------		-----------	  
loc                 Location, and year, where the data were collected. AIMS = Australian Institute of Marine   Science; LIRS = Lizard Island Research Station  
species		    	Species name: acantho = Acanthochromis; Ambon = Pomacentrus amboinensis; Chromis = Chromis   atripectoralis; Humbug = Dascyllus aruanus; Lemon = Pomacentrus moluccensis	  
treatment		    Elevated CO2 [CO2] (850-1,050 tm) or control [Control] (400 - 450 tm) groups  
animal_id		    Fish identity  
sl		        	Standard length of the fish in mm  
size		       	Size grouping of the fish, separated at 15 mm standard length into 'big' or 'small'  
activity	    	Number of seconds the fish was active per minute, averaged across the duration of the trial  
comment		    	Comment with notes on the origin of the data  

### clark_paper_data.csv ###
Meta-analytical data for the study by Clark. et al

### ocean_meta_data.csv ###
Raw data for meta-analysis of ocean acidification research by Clements et.al  
columnHeading		description	  
-------------		-----------	  
Study           	Code for each individual study  
Authors	            Authors of each paper  
Year (online)	    Year the final paper was made available online  
Year (print)	    Year the final paper was included in a journal volume/issue  
Title	            Title of each paper  
Journal	            Journal the paper was published in  
Pub year IF     	The journal impact factor for the year the paper was published; obtained from InCites Journal Citation Reports  
2017 IF	            The journal impact factor for 2017 (i.e., most recent journal impact factor); obtained from InCites Journal Citation Reports  
Average n       	Average sample size for the study; average of indiviudal sample sizes for the contol and experimental groups  
Effect type     	The type of effect concluded by the study regarding the effect of OA on behaviour; strong, weak, or no effect (see Supplementary Methods for details)  
Species         	The species used in each individual experiment  
Climate (FishBase)	Climatic region for each species; obtained from FishBase  
Env cue/stimulus?	Whether or not the experiment included a cue or stimulus in the experiment (olfactory, visual, itory, or physical)  
Cue/stimulus type	The type of cue or stimulus used  
Behavioural metric	The specific measure of behaviour tested  
Life stage	        Life stage of the fish tested   
ctrl.n	            Sample size of the control group  
ctrl.mean           Mean of the control group  
ctrl.var        	Measured variance of the control group  
ctrl.sd         	The standard deviation of the control group, calculated from ctrl.vartype  
oa.n	            Sample size of the experimental group  
oa.mean         	Mean of the experimental group  
oa.var          	Measured variance of the experimental group  
oa.sd	            The standard deviation of the experimental group, calculated from ctrl.vartype  

### meta_RR.csv ###
Adapted from ocean_meta_data.csv, with 79 rows of data removed
have the columns same as ocean_meta_data.csv, but add two columns:
lnRR	            Raw effect size (natural log transformed response ratio)
measure_change      Does the experiment measure change/ratio of change

## Program explanation

### Assignment2.Rmd ###
Use R markdown for data analysis and visualization, the packages used are tidyverse, flextable, metafor, janitor, ggpmisc.
- PART I: Data Processing and Analysis
The raw study data of `OA_activitydat_20190302_BIOL3207.csv` were read and cleaned, and merged with `clark_paper_data.csv` to make a data type conforming to the meta-analysis and merged into `ocean_meta_data.csv`. The merged meta-analysis data were also read to generate logarithmic corresponding ratio (lnRR) and its sampling variance, and simple image analysis was performed.
  1. Read the study raw data and clean
  2. Generate statistics and merge files
  3. Generate lnRR and sampling variance
- PART II: Meta Analysis of OA Research
This part is mainly a meta-analysis research on the influencing factors of lnRR, and draws a visual image to assist understanding. The main focus is to explore whether there are biological, methodological, and publishing practice biases in research published in the field of ocean acidification.
  4. Overall meta-analysis
  5. Analysis of biological and methodological factor
  6. Analysis of publication practices factor
  7. Conclusion

### Assignment2.html ###
The document rendered by `Assignment2.Rmd`.
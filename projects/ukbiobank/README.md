# Dissertation and Internship on the UKBiobank
Due to the nature of the dissertation and strict licensing where a lot of code/data were stored on Cluster Machines, I am not able to provide a full project with code and outputs. Instead, I will showcase what I can and contextualise it.


## Who are the UKBiobank
The UKBioBank is a charity organisation that collates medical information and supplies it to researchers to better the treatment and diagnoses of a  wide range of diseases. Between 2006 and 2010 the UKBioBank recruited over 500,000 volunteer participants between the ages of 40-69 into a longitudinal study. Upon entry to the study, a range of data was collected, and since then there have been additional datasets gathered that contain other medical-related information for the original participants 


## Nature of the dissertation
Dissertations at Newcastle University are not done in the traditional manner, they are a large project then the final document is closer to a write-up than a thesis. I chose Data Science, which was not a topic taught on the undergraduate programme, so a lot of the project was to understand the field as well as the tools and technologies needed to complete the project. [Click Here](https://github.com/SamButterfield/DissertationCodeDump/blob/master/sb_dissertation_FINAL_V3.pdf) to see my full dissertation document that was marked at 80/100 (upper first class).


## The main achievement
I produced a script that can be run on the Universities High-Performance Cluster Computer that produces an Activity Impact Score for individuals at a point in time, this was a continuous value that indicates how able they are to be active. To increase the readability and modifiability of this whole process I broke the script down  into 3 steps:

Extract Population - The population was a subset of people who exist in multiple datasets. I also did some necessary cleaning as the datasets I was working with were raw.

Extract Chapter - To assign the Activity Impact Scores I had to reduce the number of unique codes the label, I did this by exploiting the READ code systems which is used to describe health events. I migrated all versions of the read code to a version 2 which has a hierarchical relationship represented within the code itself, this means I could then truncate codes that were too detailed for this purpose (I.E a 5-byte code would differentiate which leg and bone are broken, a 4-byte code would define which leg is broken and a 3-byte code would just define broken leg). This reduced the number of different unique events from 30K+ to 215. I also extracted the events for when participants wore a high-resolution accelerometer, which is different for everyone in the population.

Assign Activity Impact Scores - this pulls everything together and produces a unique list of individuals with a score.

### [Return to the main portfolio page](/portfolio/)

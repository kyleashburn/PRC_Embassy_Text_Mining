# PRC_Embassy_Text_Mining
### \**Work in progress\**
### Text Mining Press Releases from the PRC Embassy in the UK
#### Abstract
This project is a continuation of my work pulling URLs from the wayback machine. 
I made the decision that the best course of action was to continue my work on that to see what I could manage to do in terms of extending that. My first step was to [create the functions](https://github.com/kyleashburn/PRC_Embassy_Text_Mining/blob/main/Creating%20Functions%20to%20pull%20with.ipynb) to pull the data with and [then apply it](https://github.com/kyleashburn/PRC_Embassy_Text_Mining/blob/main/Applying%20Function%20to%20data.ipynb).
In the process, I pushed that into an ndjson to store the data I was working with. 
After that, I started my [basic](https://github.com/kyleashburn/PRC_Embassy_Text_Mining/blob/main/Basic%20Data%20Exploration.ipynb) and [advanced](https://github.com/kyleashburn/PRC_Embassy_Text_Mining/blob/main/Advanced%20Exploration.ipynb) exploration of the data I pulled. However, I quickly realized I had made some mistakes in my original cleaning so I set about [cleaning it again](https://github.com/kyleashburn/PRC_Embassy_Text_Mining/blob/main/Data%20Cleaning.ipynb). 
That mistake was pulling the ambassador in office using the ambassador's about page. I realized that I needed to make an adjustment for the time where there wasn't an ambassador in office (the window of time where Ambassador Xiaoming had stepped down but Ambassador Zeguang had yet to assume office).
Once I'd cleaned it again, I set about conducting my [basic](https://github.com/kyleashburn/PRC_Embassy_Text_Mining/blob/main/Basic%20Data%20Exploration.ipynb) and [advanced](https://github.com/kyleashburn/PRC_Embassy_Text_Mining/blob/main/Advanced%20Exploration%20on%20the%20Cleaned%20Data.ipynb) exploration once again
Finally, my next steps are to work on my topic modeling of this data. 
#### Motivation
I wanted a project with a managable scale where I could work from begining to end of the text analysis process starting from data ingestion to the creation of an end data project.
This seemed to me to be the best way for me to do so. In particular, I wanted to practice working more with topic modeling and the various assumptions of different models and with pickling the resulting topic models as well as using the predicted models as attributes of the data. 
#### Results
#### Caveat
This data likely isn't exhaustive because it relies on what was found on the internet archive. Thus, it's difficult to go ahead and say that this is a fair coverage of the problem space. Howevr, it is also necccessary to say that this is likely a *good enough* representation to start analysis from. 
##### Basic Exploration
It's pretty clear from the start that the numbers of press releases aren't proportional to the size of the tenure of an ambassador. 
This isn't too surprising as some periods in time are more eventful than others. 
Looking at the low granularity and high granularity histograms for title lengths, it's quite clear that the title lengths tend to stick around 10-15 words. 
Looking at the low granularity and high granularity histograms for body lengths, it's clear the body lengths tend to be between 400 and 800 words. 
The descriptive statistics for body and title length both seem to indicate a difference across the board but until I get around to statistical significance testing, I can't be positive about this.
The frequency of releases (within the dataset at least) increased over time with a fairly low baseline both on a yearly and monthly basis. Of course, that exists with the caveat that this may not fully cover the data space here. 
Both title length and body length have increased over time with both creeping higher in the late 2010s and continuing that trend into the 2020s.


I plan to further explore this by breaking it down by ambassador at a future date. 

##### Advanced Exploration
###### Language Classification, Preprocessing, & Term Frequency
Starting with language classification, unsurprisingly for English language press releases, the language is always English according to FastText's language classifier. After cleaning and preprocessing by removing stopwords and lemmatizing words (among other things), I moved ahead by examining term frequencies.
Starting with unigrams and their frequency, we don't see anything too surprising here to a student of global affairs. Quite a bit about China and Chinese, Hong Kong, the UK. Standard terms such as international, right, law, global, government, and security. "Question" isn't too surprising as it is a common enough term that pops up in the corpus (many of the releases follow a Q&A format to a degree). While "th" clearly refers to dates (after I removed the #'s).
Moving to analyzing term frequency by ambassadorial term, we can see some interesting things. 

Looking at the term frequency under Ambassador Zeguang, we can see that there a few words where there appears to have been some pre-processing issues ("thischina" & "victimchina"). Interestingly, it also looks like a lot of the terms in the top 50 words are verbs in either the past or present tense. As I am not too familiar with press releases from embassies, it is entirely possible this is the norm. 

Looking at the term frequency under Ambassador Xiaoming, we can see that we again have words messed up by the pre-processing (or perhaps for another reason) ("compromisewithdrawal", "detectedchina" & "provincialmunicipaldistrictcounty"). However, the words here are not action words in the same way Ambassador Zeguang had them so we can say there's a qualitative difference between the messaging under these two ambassadors.

Looking at the terms when there was no ambassador in office, we can see the terms are different again. "Refutation" is a strong word and is the most frequent term. Overall, the seeming sentiment of the top terms here tend to be more negative and the words seem to be more combative. Again, we have the same issue with pre-processing ("reproachfifth"). Looking at Hong, we can guess that related to Hong Kong (as SAR likely does) but until we run the bi-gram analysis, we can't say for sure.

Overall, it is clear the terms that are most frequent with each ambassador (or when it is vacant) are quite different. While this isn't shocking, it shows the degree to which who is in a role affacts word choices (though here, one *can* make a reasonable argument for international affairs and events acting as a confounding factor). 

Pivoting to bigrams and trigrams, We can pretty clearly see that the top terms aren't too different when we include bigrams and trigrams. A few make it into there: "national security", "internal affair", "chinese embassy", "hong kong". These are of course rather obvious ones to  a student of Chinese relations. 

When examining each ambassador in turn, we see a few differences between ambassadors. 

Looking at Ambassador Zeguang's tenure, it's clear that the main focus is China, Hong Kong, and a potpourri of words relating to Chinese security concerns. 

Looking at Ambassador Xioming's tenure, it's clear that like Ambassador Zeguang's tenure, it's focused mostly on China and Hong Kong and relevant issues appearing during his tenure. 

Looking at when the ambassadorship was vacant, it's quite clear that the focus isn't too different when compared to when there is an ambassador in office. This would seem to indicate the focus of the messaging is driven by events more than anything else. 

###### Sentiment Analysis


##### Topic Modeling
Still working on this

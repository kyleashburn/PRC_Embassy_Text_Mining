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

##### Topic Modeling
Still working on this

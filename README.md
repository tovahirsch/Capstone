# Assessing Pollution in Lakes
## Table of Contents
1. [ Summary ](#summ)
2. [ Data ](#data)
3. [ Conclusions ](#conc)
4. [ Concepts & Skills Used ](#skills)
<a name="summ"></a>
## 1. Summary

One of the greatest shortcomings of our generation is the inability to ensure clean water for all humans living on this earth. It is the foundation of survival and something every person should have access to. It was with this in mind that I set out to explore this issue in the context of data science. The intention was how beneficial it would be to employ a deep neural network that can identify polluted bodies of water. Regularly accessing images through google earth would be an efficient and cost effective way to monitor water quality improvement or disintegration over time.

<a name="data"></a>
## 2. Data

The dataset was created by a combination of web scraping coordinates and extracting shape files and then accessing corresponding images through google maps API. It was then reverse geocoded to find the countries for each of the coordinates. The countries were then assigned a Water Quality Index (supplied by http://waterriskfilter.panda.org/en/CountryProfiles#1/profileDescription: A Subindex of the Environmental Performance Index (EPI)).

The coordinates (and their corresponding images), countries, and WQI made up the raw data frame for the convolutional neural network. 1300 images were brought in. The data was then split into a training and testing group.  Numerous versions of the CNN were run including utilizing the ImageDataGenerator that shifts, rotates, and transforms a single image in various ways to create several additional images for the model to study. This was especially important for a small database (like this one) to increase the data size. 
 
<a name="conc"></a> 
## 3. Conclusions
 Ultimately the models couldn’t produce conclusive results, primary concern was the balancing of the classes. The images brought in, when evaluated, had 9X clean lakes vs polluted. On such a small data set this made it almost impossible for the neural network to successfully detect the polluted lakes. Another consideration was the resolution of images that were extracted from google images, perhaps a higher resolution would reveal more nuances that could assist the CNN. 

See [Technical Report](https://github.com/tovahirsch/Capstone/blob/master/Technical%20Report.ipynb) for a walk-through of each file used in this project<br/>
1- For[Image Retrieval](https://github.com/tovahirsch/Capstone/blob/master/Image%20Retrieval%20Final.ipynb) see Image Retrieval Final.ipynb (as well as [ne_10m_lakes.xlsx](https://github.com/tovahirsch/Capstone/blob/master/ne_10m_lakes.xlsx) for original spreadsheet<br/>
2- For all classification models using the dictionary and custom generator see:<br/>
[Images_Exploration.ipynb](https://github.com/tovahirsch/Capstone/blob/master/Images_Exploration.ipynb)<br/>
[Images_Exploration_Model_2.ipynb](https://github.com/tovahirsch/Capstone/blob/master/Images_Exploration_Model_2.ipynb)<br/>
[Images_Exploration_Model_2_V2_less_params.ipynb](https://github.com/tovahirsch/Capstone/blob/master/Images_Exploration_Model_2_V2_less_params.ipynb)<br/>
[Images_Exploration_Model_2-Weights.ipynb](https://github.com/tovahirsch/Capstone/blob/master/Images_Exploration_Model_2_Weights.ipynb)<br/>
3- For model using [ImageDataGenerator](https://github.com/tovahirsch/Capstone/blob/master/Images_Exploration_Generator.ipynb) see Images_Exploration_Generator.ipynb<br/>
4- For [visual examples](https://github.com/tovahirsch/Capstone/blob/master/Images_ImageDataenerator_Preview.ipynb) of what ImageDataGenerator does, see Images_ImageDataenerator_Preview.ipynb<br/>

<a name="skills"></a>
## 4. Concepts & Skills Used
Python/ Pandas<br/>
Beautiful soup<br/>
APIs<br/>
Convolutional Neural Network<br/>
Unbalanced Classes/ Weights<br/>


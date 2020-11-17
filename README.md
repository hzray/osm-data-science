# OSM Project - Group AOLIGEI

This the repository for CMPT 353 final project with topic OSM (Group AOLIGEI)

## Getting Started

There are three parts of instructions that will get you started with our project. 

### Installing

A step by step series of examples that tell you how to get a development env running

Say what the step will be

```
Give the example
```

And repeat

```
until finished
```

End with an example of getting some data out of the system or using it for a little demo

## Part 1 - *Airbnb*  

### Code
- There are four coding files used to clean and process the data, they are included under ```DataProcessing``` folder. The raw data are stored in ```raw``` folder and processed data are generated and stored in ```processed``` folder.
- Airbnb Recommendation code is in ```AirbnbRecommendation``` folder.
- The visualizations of map and statistic result are available in  ```DataVisulization&Stats.html``` under ```DataAnalysis``` folder.


### How to run code

#### DataProcessing

1.
```
python3 geocoding-API.py
```

library: ```urlib```, ```json```

warning: this script may take one half hour to finish , and you need geocoding API key to make the request.

2.
```
python3 Airbnb_listings.py
```

library: ```nltk```, ```vaderSentiment```

3.
```
python3 van_OSM.py
```

4.
```
python3 Airbnb_info.py  
```

- all generated data are stored in ```processed``` folder.
- if you would like to rerun these files, please run in the provided order.
- input and output information are available in comment.

#### Recommendation  

1.
```
python3 AirbnbRecommend.py clock.jpg
```

library: ```GPSPhoto```

##### Input
```
clock.jpg
```

we provide a sample input file ```clock.jpg```, the photo was taken at gastown clock. Please be sure the input picture has geoinformation avilable in its EXIF data and is taken in city Vancouver.

##### Output

information of recommend airbnb

#### Data Analysis and Visulization
You can find visulization file ```DataVisulization&Stats.html``` under ```DataAnalysis``` folder. It was generated by the notebook script with the same name.





## Part 2 - *Tim Hortons*  

There are two coding files, tims\_cluster.ipynb and tims\_cluster.py for this part and they work as the same but in different formats.

### How to run the code

- Kindly change the 'choice' variable in the first line of the program to try on different Tim Hortons locations. 

- The sample folder contains the csv files that I ran the program, you should be able generate these files in the same format after you run the program. 

#### python file

```
python3 tims_cluster.py
```

#### or run it in jupyter notebook

```
jupyter notebook
```

### Input & output files
#### Input

```
Tim Hortons dataset & OSM dataset
```

#### Output

```
merge_tims.csv - dataframe merge Tim Hortons dataset & OSM dataset

```

```
knn_result.csv - the result of the KNN model
```

```
kmean_result.csv - the result of the KMEAN model
```







## Part 3 - *Chinese Restaurants*  

### There are four Python scripts:
#### Minimize_dataset.py
- takes the review dataset and read it as chunks into a Dataframe; 

##### review_restaurants.py 
- uses Post Hoc Analysis; 
- outputs a Means Comparisons table & spiffy plot of the confidence intervals of each mean

##### trim_training.py 
- transformations of the dataset for prediction
- Produce restaurants features out of tags

##### predict_review.py 
- use models to predict reviews



### How to run the code
```
cd Chinese-restaurants
```

```
# Optional: "yelp_academic_dataset_review.json" is 6 GB and the "yelp_academic_dataset_business.json" dataset is 150 MB. Download these two datasets could take long time and large disk spaces. Therefore, the result minimized_data.csv is provided in the repo to eliminate the process of running Minimize_dataset.py
# NOTE: if chose to run, please download "yelp_academic_dataset_review.json"(6 GB) and the "yelp_academic_dataset_business.json"(150 MB) from the yelp link down below
python3 Minimize_dataset.py yelp_academic_dataset_business.json yelp_academic_dataset_review.json minimized_data.csv
```

```
python3 review_restaurants.py minimized_data.csv
```

```
#Optional: the "yelp_academic_dataset_business.json" dataset is 150 MB. Download this dataset could take long time and large disk spaces. Therefore, the result trimmed.csv is provided in the repo to eliminate the process of running trim_training.py
# NOTE: if chose to run, please download the "yelp_academic_dataset_business.json"(150 MB) from the yelp link down below
python3 trim_training.py yelp_academic_dataset_business.json trimmed.csv
```

```
python3 predict_review.py
```



### Input & output files
### 1. Minimize_dataset.py 
#### Input
```
yelp_academic_dataset_business.json & yelp_academic_dataset_review.json
```


Yelp dataset: information on business units from different cities & customer reviews on Yelp for each business units

#### Output

A subset of the large review dataset in minimized_data.csv

### 2. review_restaurants.py 
#### Input
```
minimized_data.csv
```


Minimized version of the review dataset obtain from running Minimize_dataset.py

#### Output

a Means Comparisons table & spiffy plot of the confidence intervals of each mean

### 3. trim_training.py 
#### Input
```
yelp_academic_dataset_business.json
```

Yelp dataset: information on business units from different cities

#### Output
```
trimmed.csv
```

a dataset for prediction for predict_review.py

### 4. predict_review.py 
#### Input

no input file needed on commandline, the code included the "trimmed.csv" produced by the previous step


#### Output
scores of prediction on each revision







## Dataset we used

* [Tim Hortons](https://www.kaggle.com/kapastor/tim-hortons-locations) - The locations of all Tim Hortons globally.
* [Airbnb Listings and Reviews](http://insideairbnb.com/get-the-data.html) - Listings information and reviews of Airbnbs in Vancouver
* [Language Training](https://www.kaggle.com/rtatman/the-umass-global-english-on-twitter-dataset) - Used to train model that can predict language of Airbnb reviews
* [Chinese Restaurants](https://www.kaggle.com/yelp-dataset/yelp-dataset) - Used yelp_academic_dataset_business.json & yelp_academic_dataset_review.json to get information of business units and customers reviews on Yelp.com

## Authors
* **Zirui Huang** - *ziruih@sfu.ca* (Airbnb)
* **Xu Zhicheng (Max)** - *maxx@sfu.ca* (Tim Hortons)
* **Rong Li** - *rong_li_2@sfu.ca* (Restaurant)




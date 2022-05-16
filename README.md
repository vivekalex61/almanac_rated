
# Places Rated Almanac by Richard Boyer

[![MIT License](https://img.shields.io/apm/l/atomic-design-ui.svg?)](https://github.com/tterb/atomic-design-ui/blob/master/LICENSEs)

Case study of choosing a better place to live by analyzing different parameters  of places.
## Introduction 

#### Place analysis for building home
Every person has their own preferances in selecting a location for spending life or making a their dream home.
Some may prefer country side, cities, isolated areas and so on.If we have data about each place characterstics, we could analyze it and choose a place.
Here, The dataset is consist of Americas 379 metropolitan area  is rated by factors that are important to anyone considering a move.


![alt text](https://raw.githubusercontent.com/vivekalex61/almanac_rated/main/images/intro.png)

## Overview 
- Datasets and Data-Loading
- Data Preprocessing
- Model creation

### Datasets and Data-Loading

In this dataset every one of Americas 379 metropolitan areas is rated by factors that are important to anyone considering a move. Divided into nine thoroughly researched main topics, this guide derives its information as much from private sources as government sources, providing a well-rounded description of all that each metro area has to offer: ambience, housing, jobs, crime, transportation, education, health care, recreation, and climate. With a personalized quiz to help determine the most important factors of an area, this ratings sourcebook provides a wealth of information for those looking to move and the armchair traveler alike.

link : https://online.stat.psu.edu/stat505/lesson/11/11.3

1)Climate & Terrain: very hot and very cold months, seasonal temperature variation, heating- and cooling-degree days, freezing days, zero-degree days, ninety-degree days.
 
 2)Housing: utility bills, property taxes, mortgage payments.
Health Care & Environment: per capita physicians, teaching hospitals, medical schools, cardiac rehabilitation centers, comprehensive cancer treatment centers, hospices, insurance/hospitalization costs index, flouridation of drinking water, air pollution.

3)Crime: violent crime rate, property crime rate.
Transportation: daily commute, public transportation, Interstate highways, air service, passenger rail service.

4)Education: pupil/teacher ratio in the public K-12 system, effort index in K-12, accademic options in higher education.

5)The Arts: museums, fine arts and public radio stations, public television stations, universities offering a degree or degrees in the arts, symphony orchestras, theatres, opera companies, dance companies, public libraries.

6)Recreation: good restaurants, public golf courses, certified lanes for tenpin bowling, movie theatres, zoos, aquariums, family theme parks, sanctioned automobile race tracks, pari-mutuel betting attractions, major- and minor- league professional sports teams, NCAA Division I football and basketball teams, miles of ocean or Great Lakes coastline, inland water, national forests, national parks, or national wildlife refuges, Consolidated Metropolitan Statistical Area access.

7)Economics: average household income adjusted for taxes and living costs, income growth, job growth.

8)In addition latitude and longitude, population and state and case number are also given. Use principal components analysis to identify the major components of variation in the ratings amongst cities.


### Data Preprocessing
 Preprocessing of data includes two steps
 
 1)Removing unwanted columns and replace values
 
 2)Scaling of  features

### Visualization of data after the preprocessing 


#### Selected Features

![alt text](https://raw.githubusercontent.com/vivekalex61/almanac_rated/main/images/data.png)


#### Data distribution

![alt text](https://raw.githubusercontent.com/vivekalex61/almanac_rated/main/images/dist_1.png)


![alt text](https://raw.githubusercontent.com/vivekalex61/almanac_rated/main/images/dist_2.png)


#### Data corelation

![alt text](https://raw.githubusercontent.com/vivekalex61/almanac_rated/main/images/corr.png)



### Model building and training


1)Principle Component Analysis


#### 1)Principle Component Analysis

The principal components of a collection of points in a real coordinate space are a sequence of {\displaystyle p}p unit vectors, where the {\displaystyle i}i-th vector is the direction of a line that best fits the data while being orthogonal to the first {\displaystyle i-1}i-1 vectors. Here, a best-fitting line is defined as one that minimizes the average squared distance from the points to the line. These directions constitute an orthonormal basis in which different individual dimensions of the data are linearly uncorrelated. Principal component analysis (PCA) is the process of computing the principal components and using them to perform a change of basis on the data, sometimes using only the first few principal components and ignoring the rest.

PC1:


![alt text](https://raw.githubusercontent.com/vivekalex61/almanac_rated/main/images/pc1.png)

Places sorted using PC1 :


![alt text](https://raw.githubusercontent.com/vivekalex61/almanac_rated/main/images/pc1_places.png)

PC2:


![alt text](https://raw.githubusercontent.com/vivekalex61/almanac_rated/main/images/pc2.png)

Places sorted using PC2 :


![alt text](https://raw.githubusercontent.com/vivekalex61/almanac_rated/main/images/pc2_places.png)

PC3:


![alt text](https://raw.githubusercontent.com/vivekalex61/almanac_rated/main/images/pc3.png)

Places sorted using PC3:


![alt text](https://raw.githubusercontent.com/vivekalex61/almanac_rated/main/images/pc3_places.png)


Bi-plot :

![alt text](https://raw.githubusercontent.com/vivekalex61/almanac_rated/main/images/Biplot.png)


Loading plot:

![alt text](https://raw.githubusercontent.com/vivekalex61/almanac_rated/main/images/loading_plot.png)


## Results
Below are the results  got from Kmeans and PCA.

###    Interpretation from KMEANS

1,Cluster 2 has highest number of industries , vehicles,labor force , housing units,poverty rates

2,cluster 4 has highest percapita income and restaurant density

3,cluster 1 has lowest median age, Where youngsters are living

4,cluster 5 has lowest house hold income and highest median age.where old age people lives

    
###    Interpretation from PCA
PC1: This component is the measure of Labor force : 0.41 ,Healthcare: 0.40, Poverty rates: 0.40, industries: 0.40, housing units     0.40 and vehicles per house hold: .40 . Increase in  PC1 tends to increases the correlating values. PC1 describes 47% of variance.

PC2: This component has can be measure of  percapita income: -0.482,House hold income  :  -0.43 ,family income  : 0.-43 and Population density:.37 . So, we can say PC2 tells about the Bad or worst. This suggest that when pc2 increases there will will be a low income.

PC3:This component affects the Population density : 48% and restaurant density :46% also negatively affects median age. This component may say that area in PC3 have young people so, restaurant density is high.The third principal component is a measure of the age and restaurant density.

## End Notes

The model is not finetuned .

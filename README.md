![puppies](https://github.com/stevenaddison/Project-4/blob/main/images/puppybanner.jpeg?raw=true)
# Petfinder Pawpularity Prediction Using Neural Networks
Authors: Steven Addison, Angela Kim, Aisha Baitemirova-Othman


## Overview
[Petfinder.my](https://www.petfinder.my/) is Malaysia’s leading animal welfare platform, featuring over 200,000 animals with more than 56,000 happily adopted. This project analyzes photos of adoptable pets from Malaysian animal shelters found on Petfinder and designs a Deep Learning model to predict the "Pawpularity" of pet photos.


## Business Problem
They say a picture is worth a thousand words. A picture can also save a life. Hundreds of millions of stray cats and dogs suffer on the streets, live miserably in crowded shelters, or are euthanized around the world. Companion animals with attractive and high quality photos are more likely to be adopted and more likely to be adopted faster [source](https://www.tandfonline.com/doi/full/10.1080/10888705.2014.982796). We want to answer the question: what makes a good picture? After analyzing raw images and metadata to predict the “Pawpularity” of pet photos, we train and test our model on PetFinder.my's thousands of pet profiles to come up with the best recommendations on photo composition. We hope our model will help stray cats and dogs find their "furever" home faster.


## Data Understanding
The data comes from thousands of pet profiles on [Petfinder.my](https://www.petfinder.my/). The `Pawpularity` score is derived from each pet profile's page view statistics at the listing pages, using an algorithm that normalizes the traffic data across different pages, platforms (web & mobile) and various metrics. Duplicate clicks, crawler bot accesses and sponsored profiles are excluded from the analysis. All the feature metadata is explained [here](https://github.com/stevenaddison/Project-4/blob/main/data/metadata.md).


## Data Preparation & Analysis
There are 9912 images and 12 features: `Subject Focus`, `Eyes`, `Face`, `Near`, `Action`, `Accessory`, `Group`, `Collage`, `Human`, `Occlusion`, `Info`, and `Blur` . The target variable is `Pawpularity` and ranges from 1-100. There are no null values and all features have a value of 0 (no) or 1 (yes).

<img width="402" alt="Screen Shot 2022-01-05 at 21 12 43" src="https://user-images.githubusercontent.com/92397144/148322492-bc6252ac-80e5-4b51-a562-790accc1042e.png">



## Modeling & Visualizations

#### Baseline Model:

    RMSE: 21.074920522735773
    
<img width="1089" alt="Screen Shot 2022-01-05 at 15 55 50" src="https://user-images.githubusercontent.com/92397144/148295322-582f3bdd-7f85-4721-a7d8-d97e3bc0daab.png">
 
   
Some of the image augmentation techniques that we tried:
- Gaussian Blurring
- Reflection/Flip (Horizontal and Vertical)


#### ANN Model using Blurred Images:

    Blurred ANN Training Metrics:
    Loss: 470.519
    RMSE: 21.691 
    ------
    Blurred ANN Test Metrics:
    Loss: 541.464
    RMSE: 23.269
    
![image (2)](https://user-images.githubusercontent.com/92397144/148572598-4136ab99-7d42-4981-8b70-ebd5fc0b651a.png)


#### ANN Model using RGB Images:

    Fifth ANN Training Metrics:
    Loss: 429.52
    RMSE: 20.725 
    ------
    Fifth ANN Test Metrics:
    Loss: 487.163
    RMSE: 22.072
    
![image (2)](https://user-images.githubusercontent.com/92397144/148572899-7766e2d6-8d7c-414c-ac81-f7272047593d.png)


#### CNN Model using RGB Images:

    First CNN Training Metrics:
    Loss: 425.604
    RMSE: 20.63 
    ------
    First CNN Test Metrics:
    Loss: 459.965
    RMSE: 21.447
    
![image (2)](https://user-images.githubusercontent.com/92397144/148573096-b77dd549-854a-4f67-82b9-1466b4fee131.png)


## Conclusions & Recommendations
We attempted Data Augmentation but found that Blurring and Flipping the images did not improve our RMSE.

One big concern for us was that how Pawpularity was determined was unclear. There wasn't much information on the Kaggle competition description that explained how the score was created and how to interpret it. We know the scale is from 1-100, but do all the images with a score of 100 have the same amount of traffic? We think understanding how Pawpularity is scored would help us prepare the data for better model results.

As we only had three days to complete this project, this is the best we could do.


## Next Steps
First, we would look into what goes into determining `Pawpularity`. Another thing we would like to look into would be features other than photos that affect pet profile traffic such as age of the animal and time they've been up for adoption. Lastly, our knowledge of neural networks is limited, and so, given more time, we would have liked to explore further.


## <a id="Sources">Sources</a>
- [Kaggle Competition Dataset](https://www.kaggle.com/c/petfinder-pawpularity-score)
- [Photo Metadata](https://github.com/stevenaddison/Project-4/blob/main/data/metadata.md)
- [Speed of Dog Adoption: Impact of Online Photo Traits](https://www.tandfonline.com/doi/full/10.1080/10888705.2014.982796)


## Repository Structure
```
├── [data]
│    ├── [test]
│    ├── [train]
│    ├── metadata.md
│    ├── sample_submission.csv
│    ├── test.csv
│    └── train.csv
├── [images]
│    └── puppybanner.png
├── .gitignore
├── README.md
├── data_prep_notebook.ipynb
├── final_presentation.pdf
└── modeling_notebook.ipynb
```

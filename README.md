![kittens](https://github.com/stevenaddison/Project-4/blob/main/images/kittens.png?raw=true)
# Petfinder Malaysia Pawpularity Contest
Authors: Steven Addison, Angela Kim, Aisha Baitemirova-Othman


## Overview
[Petfinder.my](https://www.petfinder.my/) is Malaysia’s leading animal welfare platform, featuring over 200,000 animals with more than 56,000 happily adopted. This project analyzes photos of adoptable pets from Malaysian animal shelters found on Petfinder and designs a Deep Learning model to predict the "Pawpularity" of pet photos.


## Business Problem
They say a picture is worth a thousand words. A picture can also save a life. Hundreds of millions of stray cats and dogs suffer on the streets, live miserably in crowded shelters, or are euthanized around the world. Companion animals with attractive and high quality photos are more likely to be adopted and more likely to be adopted faster [source](https://www.tandfonline.com/doi/full/10.1080/10888705.2014.982796). We want to answer the question: what makes a good picture? After analyzing raw images and metadata to predict the “Pawpularity” of pet photos, we train and test our model on PetFinder.my's thousands of pet profiles to come up with the best recommendations on photo composition. We hope our model will help stray cats and dogs find their "furever" home faster.


## Data Understanding
The data comes from thousands of pet profiles on [Petfinder.my](https://www.petfinder.my/). The `Pawpularity` score is derived from each pet profile's page view statistics at the listing pages, using an algorithm that normalizes the traffic data across different pages, platforms (web & mobile) and various metrics. Duplicate clicks, crawler bot accesses and sponsored profiles are excluded from the analysis. All the feature metadata is explained [here](https://github.com/stevenaddison/Project-4/blob/main/data/metadata.md).


## Data Preparation & Analysis
There are 9912 images and 12 features: `Subject Focus`, `Eyes`, `Face`, `Near`, `Action`, `Accessory`, `Group`, `Collage`, `Human`, `Occlusion`, `Info`, and `Blur` . The target variable is `Pawpularity` and ranges from 1-100. There are no null values and all features have a value of 0 (no) or 1 (yes).


## Modeling & Visualizations
Some of the image augmentation techniques that we tried:
- Grayscaling
- Gaussian Blurring
- Reflection/Flip (Horizontal and Vertical)

#### Grayscaled Images:

    Grayscaled Training Metrics:
    Loss: 670.923
    Root Mean Square Error: 25.902
    Cross Validation Score: 
    ------
    Grayscaled Test Metrics:
    Loss: 709.029
    Root Mean Square Error: 26.628
    
<img width="1177" alt="Screen Shot 2022-01-05 at 14 36 08" src="https://user-images.githubusercontent.com/92397144/148286041-24ee3897-bde4-4e26-9abf-6a0f40da8b4b.png">

    
#### Grayscaled & Blurred Images:

    Grayscaled & Blurred Training Metrics:
    Loss: 494.477
    RMSE: 22.237
    Gross Validation Score: 
    ------
    Grayscaled & Blurred Test Metrics:
    Loss: 533.591
    RMSE: 23.1
    
<img width="1177" alt="Screen Shot 2022-01-05 at 14 40 37" src="https://user-images.githubusercontent.com/92397144/148286342-6e9784a3-5a68-41b6-9ccb-8128aca74a0a.png">
 
#### Grayscaled, Blurred, & Horizontally Flipped Images:

    Graycaled, Blurred, & Horizontally Flipped Training Metrics:
    Loss: 589.117
    RMSE: 24.272
    Cross Validation Score: 
    ------
    Grayscaled, Blurred, & Horizontally Flipped Test Metrics:
    Loss: 630.435
    RMSE: 25.108
    
<img width="1174" alt="Screen Shot 2022-01-05 at 14 48 30" src="https://user-images.githubusercontent.com/92397144/148287316-fd306aa0-21d8-4d4c-8351-831ded6e5386.png">

#### Grayscaled, Blurred, & Vertically Flipped Images:

    Grayscaled, Blurred, & Vertically Flipped Training Metrics:
    Loss: 602.445
    RMSE: 24.545
    Cross Validation Score: 
    ------
    Grayscaled, Blurred, & Vertically Flipped Test Metrics:
    Loss: 631.341
    RMSE: 25.127
    
<img width="1166" alt="Screen Shot 2022-01-05 at 14 54 06" src="https://user-images.githubusercontent.com/92397144/148288088-ee6ee825-f9de-4e53-8614-64fb4d1178c3.png">


## Conclusions & Recommendations
We found the `Pawpularity` score to be too vague to come to any strong conclusions. There wasn't much information on the Kaggle competition description that explained how the score was created and how to interpret it. We think understanding how `Pawpularity` is scored would help us prepare the data for better model results.


## Next Steps
First, we would look into what goes into determining `Pawpularity`. Another thing we would like to look into would be features other than photos that affect pet profile traffic such as age of the animal and time they've been up for adoption.


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
│    └── kittens.png
├── .gitignore
├── README.md
├── data_prep_notebook.ipynb
├── final_presentation.pdf
└── modeling_notebook.ipynb
```

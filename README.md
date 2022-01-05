# Petfinder Malaysia Pawpularity Contest
Authors: Steven Addison, Angela Kim, Aisha Baitemirova-Othman


## Overview
[Petfinder.my](https://www.petfinder.my/) is Malaysia’s leading animal welfare platform, featuring over 200,000 animals with more than 56,000 happily adopted. This project analyzes photos of adoptable pets from Malaysian animal shelters found on Petfinder and designs a Deep Learning model to predict the "Pawpularity" of pet photos.


## Business Problem
They say a picture is worth a thousand words. A picture can also save a life. Hundreds of millions of stray cats and dogs suffer on the streets, live miserably in crowded shelters, or are euthanized around the world. Companion animals with attractive and high quality photos are more likely to be adopted and more likely to be adopted faster [source](https://www.tandfonline.com/doi/full/10.1080/10888705.2014.982796). We want to answer the question: what makes a good picture? After analyzing raw images and metadata to predict the “Pawpularity” of pet photos, we train and test our model on PetFinder.my's thousands of pet profiles to come up with the best recommendations on photo composition. We hope our model will help stray cats and dogs find their "furever" home faster.


## Data Understanding
The data comes from thousands of pet profiles on [Petfinder.my](https://www.petfinder.my/).


## Data Preparation & Analysis
There are 9912 images and 12 features: `Subject Focus`, `Eyes`, `Face`, `Near`, `Action`, `Accessory`, `Group`, `Collage`, `Human`, `Occlusion`, `Info`, and `Blur` . The target variable is `Pawpularity` and ranges from 1-100. There are no null values and all features have a value of 0 (no) or 1 (yes).


## Modeling



## Visualizations



## Conclusions & Recommendations



## Next Steps



## <a id="Sources">Sources</a>
- [Kaggle Competition Dataset](https://www.kaggle.com/c/petfinder-pawpularity-score)
- [Photo Metadata]()
- [source](https://www.tandfonline.com/doi/full/10.1080/10888705.2014.982796)


## Repository Structure
```
├── [data]
│    ├──
│    ├── 
│    ├── 
│    ├── 
│    ├── 
│    └── 
├── [images]
├── .gitignore
├── README.md
├── data_prep_notebook.ipynb
├── final_presentation.pdf
└── modeling_notebook.ipynb
```

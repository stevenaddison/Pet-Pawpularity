## Purpose of Photo Metadata
We have included optional Photo Metadata, manually labeling each photo for key visual quality and composition parameters. These labels are not used for deriving our Pawpularity score, but it may be beneficial for better understanding the content and co-relating them to a photo's attractiveness. Our end goal is to deploy AI solutions that can generate intelligent recommendations (i.e. show a closer frontal pet face, add accessories, increase subject focus, etc) and automatic enhancements (i.e. brightness, contrast) on the photos, so we are hoping to have predictions that are more easily interpretable. You may use these labels as you see fit, and optionally build an intermediate / supplementary model to predict the labels from the photos. If your supplementary model is good, we may integrate it into our AI tools as well. In our production system, new photos that are dynamically scored will not contain any photo labels. If the Pawpularity prediction model requires photo label scores, we will use an intermediary model to derive such parameters, before feeding them to the final model.


## Photo Metadata
The train.csv and test.csv files contain metadata for photos in the training set and test set, respectively. Each pet photo is labeled with the value of 1 (Yes) or 0 (No) for each of the following features:

Focus - Pet stands out against uncluttered background, not too close / far.
Eyes - Both eyes are facing front or near-front, with at least 1 eye / pupil decently clear.
Face - Decently clear face, facing front or near-front.
Near - Single pet taking up significant portion of photo (roughly over 50% of photo width or height).
Action - Pet in the middle of an action (e.g., jumping).
Accessory - Accompanying physical or digital accessory / prop (i.e. toy, digital sticker), excluding collar and leash.
Group - More than 1 pet in the photo.
Collage - Digitally-retouched photo (i.e. with digital photo frame, combination of multiple photos).
Human - Human in the photo.
Occlusion - Specific undesirable objects blocking part of the pet (i.e. human, cage or fence). Note that not all blocking objects are considered occlusion.
Info - Custom-added text or labels (i.e. pet name, description).
Blur - Noticeably out of focus or noisy, especially for the pet’s eyes and face. For Blur entries, “Eyes” column is always set to 0.

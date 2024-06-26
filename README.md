# AI-Vs-Real-Art-Classification
A CNN based project which attempts to classify the art as AI generated or Real Art.

The dataset comprises of two classes- art images generated by AI image generation models such as DALL-E and Midjourney, and real images known to be made by humans.
The objective of this project is to classify the images as AI or Real art using image classification techniques.

### Models experimented
1. A CNN architecture defined from scratch
2. Hyper-parameter tuning of the CNN architecture to improve the model above
3. A transfer learning approach using VGG16 where we will use it in three different ways
 -  Extract features using the weights of imagenet and then feed to fully connected layers
 -  Train the VGG16 architecture from scratch on our dataset
 -  Freeze some layers of the VGG16 architecture and train the test.


### Summary of Results

| Model | Validation Accuracy|
|---|---|
|Basic CNN | 71%|
|CNN with parameter tuning| 76%|
|VGG16 with imagenet weights| 84%|
|VGG16 fully trained on this data| 91%|
|**VGG16 with transfer learning**|**90%**|

Although VGG16 that was fully trained on the data gave better validation accuracy, I decided to go with the VGG16 with transfer learning wherein I froze the first 15 layers and made the remaining ones trainable, followed by the fully connected layers. This was because the VGG16 architecture fully trained on this data was significantly overfitting and also took more training time.


| Model | Validation Accuracy | Test Accuracy|
|---|---|---|
|VGG16 with transfer learning | 92%|92%|

### Scope for improvement

The model showed some weaknesses identifying the real art from AI art. The precision and recall on AI art were both impressive (>95%). This could be due to the fact that the images generated by stable diffusion are generated from a noise signal, so maybe the model uses this as a key feature for prediction. 

So any presence of noise in the real art may cause the model to be confused. One way to resolve this is to use a de-noising model like auto-encoder prior to sending the images to the model for classification. 


## Dataset Attribution and Citation

The dataset used in this project is sourced from Kaggle:

- **Title**: AI recognition dataset
- **Author**: Nathan Koliha
- **Year**: 2024
- **Data set**: [Kaggle](https://www.kaggle.com/datasets)
- **DOI**: [https://doi.org/10.34740/KAGGLE/DSV/7501727](https://doi.org/10.34740/KAGGLE/DSV/7501727)

Please cite the dataset as:

Nathan Koliha. (2024). AI recognition dataset [Data set]. Kaggle. https://doi.org/10.34740/KAGGLE/DSV/7501727

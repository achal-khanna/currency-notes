# Currency Classification using Convolutional Neural Networks



## Introduction



This project aims to classify Indian and Thai banknotes using Convolutional Neural Networks (CNNs). The dataset includes a total of 283 images of currency notes representing Indian banknotes (10, 20, 50, 100, 200, and 500 rupees). The focus is on developing a robust model that can accurately identify various denominations.



## Dataset

The dataset is derived from the article titled **"Dataset of Indian and Thai banknotes with annotations"** by Vidula Meshram et al. (2022).

- **Authors:** Vidula Meshram, Kailas Patil, Prawit Chumchu
- **Published in:** Data in Brief (2022)
- **DOI:** [10.1016/j.dib.2022.108007](https://doi.org/10.1016/j.dib.2022.108007)
- **Dataset Details:**
  - Total Images: 3000
    - Indian Banknotes: 2000 images (including denominations of 10, 20, 50, 100, 200, 500, and 2000 rupees)
    - Thai Banknotes: 1000 images (including denominations of 20, 50, 100, 500, and 1000 Baht)
  
The images are labeled in XML format using [LabelImg](https://github.com/qaprosoft/labelImg). The final training dataset consists of 252 images after filtering out unusable ones (crumpled, folded notes, and dim-lit images).



## Data Augmentation



To enhance the model's performance and robustness, the following data augmentation techniques were applied:



- **Random Resized Crop**: Randomly crops the image to 128x128 pixels while scaling between 80% to 100%.

- **Random Horizontal Flip**: Flips the image horizontally with a probability of 0.5.

- **Random Vertical Flip**: Flips the image vertically with a probability of 0.5.

- **Random Rotation**: Rotates the image randomly by up to 45 degrees.

- **Color Jitter**: Adjusts brightness with a factor of 0.2.

- **Normalization**: The images are normalized with a mean of [0.6295, 0.5977, 0.5551] and a standard deviation of [0.2069, 0.1965, 0.2004].



## Neural Network Model



The CNN model is built using MobileNetV2 with transfer learning. The model is trained using PyTorch. The training process involves optimizing hyperparameters and employing an Adam optimizer with a learning rate of 0.005.



## Results



The model achieved an overall accuracy of **94.92%** on the test dataset. The classification report is as follows:



| Class | Precision | Recall | F1-score |
|-------|-----------|--------|----------|
| 10    | 0.8571    | 1.0000 | 0.9231   |
| 20    | 1.0000    | 1.0000 | 1.0000   |
| 50    | 0.8889    | 0.8889 | 0.8889   |
| 100   | 1.0000    | 0.9000 | 0.9474   |
| 200   | 1.0000    | 1.0000 | 1.0000   |
| 500   | 1.0000    | 0.8889 | 0.9412   |




## Usage



To run this project, follow these steps:



1. Ensure that you have the necessary libraries installed Then, install the necessary libraries by running the following command in your terminal:
   ```bash
    pip install -r requirements.txt
    ```

2. Open and run the Jupyter notebook `model.ipynb`, which contains the code for training and evaluating the CNN model.

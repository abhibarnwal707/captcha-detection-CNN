# CAPTCHA Recognition using Convolutional Neural Networks (CNN)

### Introduction:
CAPTCHAs are commonly seen as images containing text that users must type in to verify their identity before accessing certain websites. CAPTCHA stands for "Completely Automated Public Turing test to tell Computers and Humans Apart," designed to prevent bots from automatically filling out forms. However, with advancements in deep learning and computer vision, this test can be solved automatically. Convolutional Neural Networks (CNN), a powerful class of deep neural networks, can be utilized to recognize and defeat CAPTCHA by analyzing the features within these images.

### Dataset Description:
The dataset used in this project contains 1,070 PNG images of text-based CAPTCHAs. The dataset has been sourced from a research publication. Each image consists of five characters, composed of English lowercase letters and digits (0-9). For model training, 970 images were used, with the remaining 100 images reserved for testing.

### Model Development:
A Convolutional Neural Network was developed to detect and decode the CAPTCHA images. Before training, the sample dataset underwent pre-processing, followed by the construction of a 24-layer model.

#### Data Preprocessing:
The CAPTCHA images are of size 50x200 pixels. Pre-processing involved converting the images to grayscale, reducing the influence of background colors. The CAPTCHA characters are extracted from the image filenames and stored in a target array with dimensions 5x36, representing the five characters and their possible values (26 letters and 10 digits). This array is used for training the model.

#### CNN Model Architecture:
The CAPTCHA recognition model consists of 24 layers, including input, convolutional, max-pooling, dense, flatten, and dropout layers. The model has a total of 1,818,196 parameters, with 1,818,132 being trainable. After extracting features through convolution and max-pooling layers, the output is passed through batch normalization to stabilize the model, followed by flattening into a vector for further processing. The dense layers, using the ReLU activation function, train the parameters, while dropout layers help in regularization. The final dense layers, with a sigmoid activation function, output the predicted characters in the CAPTCHA.

The input image has dimensions (50, 200, 1), and the model produces five output layers, each with a dimension of 36. The Adam optimizer is employed, along with the categorical cross-entropy loss function.

### Results:
The model was trained for 60 epochs, showing a steady decrease in loss. After 60 epochs, the training loss reached 0.2391, and the loss on the test set was 2.123. 

The accuracy of the output layers after 60 epochs is as follows:
- Dense Layer 2: 98.97%
- Dense Layer 4: 97.94%
- Dense Layer 6: 92.27%
- Dense Layer 8: 89.69%
- Dense Layer 10: 92.78%

### Conclusion:
While CAPTCHAs are intended to secure websites, deep learning methods, such as CNNs, can effectively recognize and decode them. In this project, we developed a 24-layer CNN model for CAPTCHA recognition using a dataset of 1,070 CAPTCHA images. After pre-processing the images and training the model for 60 epochs, we achieved high accuracy in recognizing the CAPTCHA text. The final model successfully predicted any 5-letter CAPTCHA with satisfactory accuracy and efficiency. Future improvements can expand the model's capabilities to recognize larger and more complex CAPTCHAs containing symbols and additional noise.

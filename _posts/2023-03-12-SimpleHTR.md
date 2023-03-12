# Handwritten Text Recognition System
Handwritten Text Recognition (HTR) system implemented with TensorFlow (TF) and trained on the IAM off-line HTR dataset. The model takes images of single words or text lines (multiple words) as input and outputs the recognized text. 3/4 of the words from the validation-set are correctly recognized, and the character error rate is around 10%.

## Run demo
+ Download one of the pretrained models
    + Model trained on word images: only handles single words per image, but gives better results on the IAM word dataset
    + Model trained on text line images: can handle multiple words in one image
+ Put the contents of the downloaded zip-file into the model directory of the repository
+ Go to the src directory 
+ Go to main.py and install required packages numpy, tensorflow, editpath using pip install

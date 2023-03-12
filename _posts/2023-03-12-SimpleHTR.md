# Handwritten Text Recognition System
Handwritten Text Recognition (HTR) system implemented with TensorFlow (TF) and trained on the IAM off-line HTR dataset. The model takes images of single words or text lines (multiple words) as input and outputs the recognized text. 3/4 of the words from the validation-set are correctly recognized, and the character error rate is around 10%.

## Run demo
+ Download one of the pretrained models
    + Model trained on word images: only handles single words per image, but gives better results on the IAM word dataset
      https://www.dropbox.com/s/mya8hw6jyzqm0a3/word-model.zip?dl=1
      
    + Model trained on text line images: can handle multiple words in one image
      https://www.dropbox.com/s/7xwkcilho10rthn/line-model.zip?dl=1
      
+ Put the contents of the downloaded zip-file into the model directory of the repository
+ Go to the src directory 
+ Go to main.py and install required packages numpy, tensorflow, editpath using pip install
+ The input images, and the expected outputs are shown below when the text line model is used.

![image](https://user-images.githubusercontent.com/109460490/224541233-70854301-21b6-4890-ac05-2e0254b61cba.png)

Init with stored values from ../model/snapshot-13
Recognized: "or work on line level"
Probability: 0.6674368977546692

![image](https://user-images.githubusercontent.com/109460490/224541221-5febe748-4b36-4d29-9d31-cc81e865c387.png)

Init with stored values from ../model/snapshot-13
Recognized: "word"
Probability: 0.9806373119354248

## Unable to Recognize Every Image

![image](https://user-images.githubusercontent.com/109460490/224543868-a39a063a-316e-4da9-950f-c1e4a7a29462.png)

Init with stored values from ../model/snapshot-13
Recognized: "fnd"
Probability: 0.026317203417420387

But when resized my image according to that sample image it was nearly able to recognize
Init with stored values from ../model/snapshot-13
Recognized: "wword"
Probability: 0.6883667707443237

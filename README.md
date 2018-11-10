# Receipt_Image_Classification-
Classifying the image either as Receipt or not, based on the considered Image patterns and the Extracted text associated with the considered Image.

Algorithm of using 3 models for Classifying the Image either Receipt or not a Receipt,
```

            Models considered in Classifying :

              1)      Pattern Recognition Model,

              2)      Text Feature Extraction Model,

              3)      Receipt Classifier




```
The Algorithm is considering both Image patterns similar to Receipt image paterns and Text information in the Image of considered Image.

 - to download the pre-trained Models [Pretrained Models](https://drive.google.com/file/d/1ckskSVzzFpkaMO7VyTZo0fz_m32q_S_C/view?usp=sharing)
 - to download data sample Receipt Images data [Receipt Images](https://drive.google.com/drive/folders/1q4PjRX121lj6BGDAhnM8fh1TiC78-ylO?usp=sharing)


![alt text](https://github.com/Nagakiran1/Receipt_Image_Classification-/blob/master/Model.PNG)


**1) Image Patterns Extraction  :scissors:(Pattern Recognition Model):**


  Convolution Network of 8 layers with 2\*4 layers residual feedbacks used in remembering the Patterns  :scissors: of the Receipt Images.
  
  
  ![alt text](https://github.com/Nagakiran1/Receipt_Image_Classification-/blob/master/ConvNet1.png)
  
  - Pattern Recognition Convolution Network is built to work as two models, 

- [x] 1st Model will train on the Receipt Images with direct Classification to predict the Images with softmax Classification of Receipt Categories.
- [ ] 2nd Model is same model with last before layer as predictor which will Calculate a Embedding of specified Flatten Neurons ( The Predicted flatten Values will have Feature Information of Receipt Images ).
            
  - Convolution Last before layer Embedding Output is considered as Pattern Feature of Image.

**2) Text Feature Extraction (OCR in Extracting Text):**

Receipt text information conveys much information in classifying the Receipt, but conventional Neural Networks cannot learn on the Text features in the Image. 

So to use the Text as Features, 2 stages of processing is needed.

- !) Recognizing the Text of Receipt or any Image. Here Tesseract Optical Recognition technique is used in recognizing the text and extracting from image.
- !!) Extracted Text of Receipt and Images are fed to the Sequential LSTM Classification Network. (In classifying the Text the ).

  ![alt text](https://github.com/Nagakiran1/Receipt_Image_Classification-/blob/master/OpticalCharacterRecognition.jpg)
  
  
  ![alt text](https://github.com/Nagakiran1/Receipt_Image_Classification-/blob/master/Models/BindingBox3.jpg)

  - LSTM Sequential models is also built to work as two models, 

- [x] 1st Model will train on the Receipt text with direct Classification to classify text with softmax Classification of Receipt Categories.
- [x] 2nd Model is same model with last before layer as predictor which will Calculate a Embedding of specified Flatten Neurons ( The Predicted flatten Values will have Feature Information Text key words).
            
            
            
**3) Receipt Classifier :**

Receipt Classifier is the main model in Classifying the Image either as Receipt or not.

- The Receipt Classifier is the Neural Network of having two 1 Dimensional convolution layers( to keep rememeber the Receipt Image pattern Information) and followed by 1 LSTM layer(to keep remember the Sequence of Receipt key words). 
- Input to the Network is given by the concatenated features of Pattern information Predicted Embedding values and Text Features extraction model Embedding output.

/play rimshot
     

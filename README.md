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

**Image Patterns Extraction (Pattern Recognition Model):**


  Convolution Network of 8 layers with 2\*4 layers residual feedbacks used in remembering the Patterns of the Receipt Images.
  
  
  ![alt text](https://github.com/Nagakiran1/Receipt_Image_Classification-/blob/master/ConvNet1.png)
  
  - Same Convolution Network is built as Two models, 
            - [x]. 1st Model will train on the Receipt Images with direct Classification to predict the Images with softmax Classification of Receipt Categories.
            - [ ]. 2nd Model is same model with last before layer as predictor which will Calculate a Embedding of specified Flatten Neurons ( The Predicted flatten Values will have Feature Information of Receipt Images ).
            
  - Convolution Last before layer Embedding Output is considered as Pattern Feature of Image.

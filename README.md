# DLfinal
language detection model using VGG

PROJECT DESCRIPTION:

The goal of our project was to be able to be able to differentiate different languages. After testing both image and sound, we settled on recognizing images. From there we decided to build three types of models. A VGG trained on similar looking languages, a VGG trained of different looking languages, and a Vision Transformer. We wanted to see if a CNN would be able to catch the small differences between languages like english and spanish, as well as it would be able to notice differeneces between english and chinese, two very different looking languages. Our initial hypothesis was that the CNN would not be able to, but we theorized that a vision transformer would be better able to capture these small differences. So we additionally built a vision transformer to attempt to better classify the differences, 

INSTRUCTIONS:

First, run datageneration.ipynb to generate the data. Current script saves 5000 images of all 11 available languages. In our testing, we found that google colab doesn't have enough memory to handle more than 1000 images of 6 classes, so consider changing those parameters before running.

after the data has been generated, both the VGG an Vision Transorfmers can easily be created through their respective notebooks. 

RESULTS: 

When working with the data with vastly different scripts we obtained an accuracy of 0.95
More specifically, our model was actualyl perfect at detecting 3 of our 6 languages: Chinese, Greek, and Hebrew
The model was the worst at identifying English, incorectly classifiying english text as portugese 22 times out of the 104 instances of english text in our test set. 
When working with the data with similar scripts, out accuracy was 0.45
but this accuracy all comes from distinguishing between east asian and western scripts. The model almost excuslively predicts the output to be either english or chinese. And almost all instanced of Spanish, French, and Latin are misclssified as english. 
The same issue hold with chinese and japanese. The model predicts chinese with almost perfect accuracy, but this is useless as it also predicts all japanese images to also be chinese.

From the results of working with these two different kinds of data, we see that CNN's are very good at capturing big picture differences. But when looking at more minute differences, the model unfortunately falls short. 

After seeing the performance of CNNs, we turned to Vision Transformers to see if this could be a possible solution to our problem. Unfortunately, vision transformers needed a lot more data than google colab would be able to handle to make accurate predictions. Our performance for the vision transformer model hovered around 16%, which was around equal to a random guess between the 6 classes we were training on. 

VGG trained on good data: 

Epoch [1/10], Step [76/76], Loss: 11.2767

Accuracy of the network on the 5000 validation images: 56.90515806988353 %

Epoch [2/10], Step [76/76], Loss: 22.8624

Accuracy of the network on the 5000 validation images: 65.3910149750416 %

Epoch [3/10], Step [76/76], Loss: 0.5814

Accuracy of the network on the 5000 validation images: 80.5324459234609 %

Epoch [4/10], Step [76/76], Loss: 0.0147

Accuracy of the network on the 5000 validation images: 88.6855241264559 %

Epoch [5/10], Step [76/76], Loss: 1.6927

Accuracy of the network on the 5000 validation images: 92.67886855241265 %

Epoch [6/10], Step [76/76], Loss: 2.3883

Accuracy of the network on the 5000 validation images: 76.87188019966722 %

Epoch [7/10], Step [76/76], Loss: 1.0380

Accuracy of the network on the 5000 validation images: 93.34442595673877 %

Epoch [8/10], Step [76/76], Loss: 0.5567

Accuracy of the network on the 5000 validation images: 75.04159733777038 %

Epoch [9/10], Step [76/76], Loss: 1.1479

Accuracy of the network on the 5000 validation images: 96.1730449251248 %

Epoch [10/10], Step [76/76], Loss: 0.0181

Accuracy of the network on the 5000 validation images: 91.68053244592346 %

Accuracy: 0.9534109816971714

VGG trained on bad data: 

Epoch [1/10], Step [151/151], Loss: 1.0390 

Accuracy of the network on the 5000 validation images: 45.46211490424646 % 

Epoch [2/10], Step [151/151], Loss: 5.1321 

Accuracy of the network on the 5000 validation images: 47.210657785179016 % 

Epoch [3/10], Step [151/151], Loss: 0.9390 

Accuracy of the network on the 5000 validation images: 47.210657785179016 % 

Epoch [4/10], Step [151/151], Loss: 0.8286 

Accuracy of the network on the 5000 validation images: 47.543713572023314 % 

Epoch [5/10], Step [151/151], Loss: 0.3831 

Accuracy of the network on the 5000 validation images: 49.04246461282265 % 

Epoch [6/10], Step [151/151], Loss: 1.1070 

Accuracy of the network on the 5000 validation images: 48.8759367194005 % 

Epoch [7/10], Step [151/151], Loss: 3.5813 

Accuracy of the network on the 5000 validation images: 47.377185678601165 % 

Epoch [8/10], Step [151/151], Loss: 0.6680 

Accuracy of the network on the 5000 validation images: 47.96003330557868 % 

Epoch [9/10], Step [151/151], Loss: 3.0120 

Accuracy of the network on the 5000 validation images: 48.37635303913405 % 

Epoch [10/10], Step [151/151], Loss: 0.6886 Accuracy of the network on the 5000 validation images: 46.960865945045796 %

Accuracy: 0.49834958458245826

Vision Transformer trained of "good" data:

Number of train samples:  151
Number of test samples:  38
Epoch:  0 | train loss: 1.8689 | test accuracy: 0.16
Epoch:  0 | train loss: 1.7995 | test accuracy: 0.22
Epoch:  0 | train loss: 1.7874 | test accuracy: 0.16
Epoch:  1 | train loss: 1.7953 | test accuracy: 0.22
Epoch:  1 | train loss: 1.8238 | test accuracy: 0.09
Epoch:  1 | train loss: 1.8066 | test accuracy: 0.16
Epoch:  2 | train loss: 1.8117 | test accuracy: 0.16
Epoch:  2 | train loss: 1.7954 | test accuracy: 0.03
Epoch:  2 | train loss: 1.7779 | test accuracy: 0.19
Epoch:  3 | train loss: 1.8012 | test accuracy: 0.12
Epoch:  3 | train loss: 1.7737 | test accuracy: 0.28
Epoch:  3 | train loss: 1.7888 | test accuracy: 0.19
Epoch:  4 | train loss: 1.7848 | test accuracy: 0.25
Epoch:  4 | train loss: 1.7984 | test accuracy: 0.16
Epoch:  4 | train loss: 1.7957 | test accuracy: 0.12
Epoch:  5 | train loss: 1.8011 | test accuracy: 0.16
Epoch:  5 | train loss: 1.7978 | test accuracy: 0.16
Epoch:  5 | train loss: 1.7850 | test accuracy: 0.28
Epoch:  6 | train loss: 1.8085 | test accuracy: 0.09
Epoch:  6 | train loss: 1.7824 | test accuracy: 0.12
Epoch:  6 | train loss: 1.8521 | test accuracy: 0.06
Epoch:  7 | train loss: 1.7918 | test accuracy: 0.12
Epoch:  7 | train loss: 1.8518 | test accuracy: 0.12
Epoch:  7 | train loss: 1.7743 | test accuracy: 0.44
Epoch:  8 | train loss: 1.8010 | test accuracy: 0.12
Epoch:  8 | train loss: 1.7905 | test accuracy: 0.12
Epoch:  8 | train loss: 1.8007 | test accuracy: 0.09
Epoch:  9 | train loss: 1.8052 | test accuracy: 0.12
Epoch:  9 | train loss: 1.7625 | test accuracy: 0.28
Epoch:  9 | train loss: 1.7918 | test accuracy: 0.25

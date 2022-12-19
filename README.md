# DLfinal
language detection model using VGG
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

Results:
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

Accuracy: 0.49834958458245826

Vision Transformer trained of "good" data:


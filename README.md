### CNN for binary classification between Ferrari and Porsche car images
Really just trying my hands out on CNNs, Quite fun ;)

- Trained on a GTX 1660 Super 6GB 
- 400 images of Porsche
- 500 images of Ferrari
- 900 total images
- 70% for training 
- 20% for validation
- 10% for testing 

### First Attempt:
![](https://github.com/Developerr86/FirstCNN/blob/21e910f2c1a7248a89b2eca19966b8cb26fde137/readme/Screenshot%20from%202025-05-17%2011-58-01.png)
![](https://github.com/Developerr86/FirstCNN/blob/21e910f2c1a7248a89b2eca19966b8cb26fde137/readme/res1.png)
- Model shows signs of Overfitting

### Attempt 2
- Adding Dropout layer 40% and L2 Regularisation 0.0001
![](https://github.com/Developerr86/FirstCNN/blob/21e910f2c1a7248a89b2eca19966b8cb26fde137/readme/Screenshot%20from%202025-05-17%2012-08-41.png)
![](https://github.com/Developerr86/FirstCNN/blob/21e910f2c1a7248a89b2eca19966b8cb26fde137/readme/res2.png)
- Slight Improvement but overfitting still exists

### Attempt 3
- Droput 50% and L2 Regularisation 0.01
![](https://github.com/Developerr86/FirstCNN/blob/21e910f2c1a7248a89b2eca19966b8cb26fde137/readme/res3.png)
- Accuracy decreased from 99 to 83 but no more overfitting now

### Attempt 4
- Adding another dense layer of 64 neurons
![](https://github.com/Developerr86/FirstCNN/blob/21e910f2c1a7248a89b2eca19966b8cb26fde137/readme/Screenshot%20from%202025-05-17%2012-21-06.png)
![](https://github.com/Developerr86/FirstCNN/blob/21e910f2c1a7248a89b2eca19966b8cb26fde137/readme/res4.png)
- Its even worse now, accuracy drops to 80%

### Attempt 5
- Removing the newly added dense layer, L2 regularisation changed to 0.001 and changing the 3rd Convolution layer’s filters from 16 to 32
![](https://github.com/Developerr86/FirstCNN/blob/21e910f2c1a7248a89b2eca19966b8cb26fde137/readme/Screenshot%20from%202025-05-17%2012-25-40.png)
- Model size increased significantly (doubled) from 14MB to 28MB
![](https://github.com/Developerr86/FirstCNN/blob/21e910f2c1a7248a89b2eca19966b8cb26fde137/readme/res5.png)
![](https://github.com/Developerr86/FirstCNN/blob/21e910f2c1a7248a89b2eca19966b8cb26fde137/readme/res5acc.png)
- But now the model performs much better
- Accuracy is 96%

### Evaluating
![](https://github.com/Developerr86/FirstCNN/blob/21e910f2c1a7248a89b2eca19966b8cb26fde137/readme/Screenshot%20from%202025-05-17%2012-50-34.png)
![](https://github.com/Developerr86/FirstCNN/blob/21e910f2c1a7248a89b2eca19966b8cb26fde137/readme/Screenshot%20from%202025-05-17%2013-08-51.png)
![](https://github.com/Developerr86/FirstCNN/blob/21e910f2c1a7248a89b2eca19966b8cb26fde137/readme/Screenshot%20from%202025-05-17%2013-09-52.png)
- Red and Yellow are very prominent colors on a ferrari and must be preserved , OpenCV’s BRG channel must be converted to RGB to maintain colors
![](https://github.com/Developerr86/FirstCNN/blob/21e910f2c1a7248a89b2eca19966b8cb26fde137/readme/Screenshot%20from%202025-05-17%2013-12-38.png)
![](https://github.com/Developerr86/FirstCNN/blob/21e910f2c1a7248a89b2eca19966b8cb26fde137/readme/Screenshot%20from%202025-05-17%2013-15-01.png)
- Low quality images perform better on classification (these were less than 300x300 px images)

# [Kaggle] Digit Recognizer
> MNIST ("Modified National Institute of Standards and Technology") is the de facto “hello world” dataset of computer vision. Since its release in 1999, this classic dataset of handwritten images has served as the basis for benchmarking classification algorithms. As new machine learning techniques emerge, MNIST remains a reliable resource for researchers and learners alike.  

In this competition, our goal is to correctly identify digits from a dataset of tens of thousands of handwritten images.

## Results & Ranking

My best entry (using LeNet v2 described below) scored an accuracy of 99.485% on the test set with a worldwide rank of 420. 

## Models

### [LeNet-5] Original Architecture

ConvNet --> Pool --> ConvNet --> Pool --> (Flatten) --> FullyConnected --> FullyConnected --> Softmax 

#### Results

**epochs** - 30  
**loss** - 0.0016  
**train_accuracy** -  0.9998  
**val_loss** -  0.0412  
**val_accuracy** - 0.9905  

##### Highest Dev Set Accuracy Obtained - 99.05%

***

### [LeNet-5 v1] Modified Architecture

ConvNet --> **ConvNet** --> Pool --> **(Dropout)** --> ConvNet --> Pool --> **(Dropout)** --> (Flatten) --> FullyConnected --> FullyConnected --> Softmax 

#### Results

**epochs** - 30  
**loss** - 0.0319  
**train_accuracy** -  0.9918  
**val_loss** -  0.0327  
**val_accuracy** - 0.9929  

##### Highest Dev Set Accuracy Obtained - 99.29%

***

### [LeNet-5 v2] Modified Architecture

ConvNet --> **ConvNet** --> **BatchNorm** --> Pool --> **(Dropout)** --> ConvNet --> **ConvNet** --> **BatchNorm** --> Pool --> **(Dropout)** --> (Flatten) --> **FullyConnected** --> **BatchNorm** --> FullyConnected --> **BatchNorm** --> FullyConnected --> **BatchNorm** --> Softmax 

#### Results

**epochs** - 30  
**loss** - 0.0113  
**train_accuracy** - 0.9966  
**val_loss** -  0.0176   
**val_accuracy** - 0.9957    

##### Highest Dev Set Accuracy Obtained - 99.57%

***

### References

* **Yassine Ghouzam**, PhD - Parameters for Data Augmentation using Image Data Generator, Variable Learning Rate using ReduceLROnPlateau (https://www.kaggle.com/yassineghouzam/introduction-to-cnn-keras-0-997-top-6)

* **Taavish Thaman** - LeNet-5 Keras (https://github.com/TaavishThaman/LeNet-5-with-Keras)

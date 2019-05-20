# Neural Network Basics
## Machine Learning Datasets

* The file ```API Accessible Classification Datasets.ipynb``` gives a scoop on real world classification datasets that are available through the Keras and Sklearn API
* ```synthetic_classification_datasets.ipynb``` gives an idea about how to create synthetic classification datasets using the sklearn API

## Multiclass oversampling and undersamping

* The file ```Multiclass oversampling and undersamping.ipynb``` gives a brief on oversampling and undersampling techniques to handle imbalanced classes

## Visualization

* The file ```Basic Matplotlib Tutorial.ipynb``` teaches data visualization with Matplotlib. Follow along and feel free to try in your own.

![Basic Plot](https://github.com/R-Suresh/Neural_Network_Basics/blob/master/images/basic.jpg)
![Advanced Plot](https://github.com/R-Suresh/Neural_Network_Basics/blob/master/images/advanced.jpg)


## Choosing Optimal model features

* The file ```Basic Feature Selection Sklearn.ipynb``` illustrates this process.
   * Sklearn library is used for the feature selection on a custom dataset
   * Stay tuned for a Botura based feature selection

## Choosing optimum model hyperparameters 

### Manual

* The file ```Basic MNIST Feed Forward NN (MLP).ipynb``` shows a two layer Feed Forward (FF) Neural Network (NN).

| Dataset        | Accuracy           |
| ------------- |:-------------:|
| MNIST | 98.02%      |

| Hyperparameter        | Technique used           |
| ------------- |:-------------:|
| Weight initializer      | Xavier Uniform |
| Activation  | Relu      |
| Optimizer | rmsprop      |
| Regularization | None      |
| Loss function | kullback_leibler_divergence      |

Maybe put loss curves and model architecture here

### Automated

* The Ski-kit Learn API has grid Search that builds and evaluates models with different parameter values as specified in the grid.
* This is illustrated in ```Grid Search.ipynb```

## Score Card

The same architecture as in ```Basic MNIST Feed Forward NN (MLP).ipynb``` was used with the below changes and below results.

| Weight Init        | Epochs        | Loss function       | Optimizer        | Activation        | Batch Size        | Regularization        | Accuracy           |
| ------------- |:-------------:|:-------------:|:-------------:|:-------------:|:-------------:|:-------------:|:-------------:|
| None | 20      | categorical_crossentropy      | rmsprop      | relu      | 256      | None      | 98.20 |
| None | 20      | kullback_leibler_divergence      | rmsprop      | relu      | 256      | None      | 98.02 |
| Xavier Uniform (glorot_uniform) | 20      | kullback_leibler_divergence      | rmsprop      | relu      | 256      | Dropout(0.5); Dropout(0.5)  | 98.43 |
| Xavier Uniform (glorot_uniform) | 20      | kullback_leibler_divergence      | Adam      | relu      | 256      | Dropout(0.5); Dropout(0.5)     | 98.51 |
| Xavier Uniform (glorot_uniform) | 20      | kullback_leibler_divergence      | Adam      | relu      |  300      |kernel_regularizer=regularizers.l2(0.01); kernel_regularizer=regularizers.l2(0.01) | 96.83 |
| Xavier Uniform (glorot_uniform) | 20      | kullback_leibler_divergence      | Adam      |  relu | 300    |activity_regularizer=regularizers.l1(0.01); activity_regularizer=regularizers.l1(0.01) | 11.35 |
| Xavier Uniform (glorot_uniform) | 20      | kullback_leibler_divergence      | sgd      |  relu | 256    |Dropout(0.5); Dropout(0.5) | 93.43 |
| Xavier Uniform (glorot_uniform) | 20      | categorical_crossentropy      | Adam      |  relu | 256    |Dropout(0.5); Dropout(0.5) | 93.32 |
| **Xavier Uniform (glorot_uniform)** | 20      | **kullback_leibler_divergence**      | **Adamax**      |  relu | 256    |**Dropout(0.5); Dropout(0.5)** | **98.59** |
| Xavier Uniform (glorot_uniform) | 20      | kullback_leibler_divergence      | Adamax      |  relu | 256    |Dropout(0.6); Dropout(0.6) | 98.18 |
| Xavier Uniform (glorot_uniform) | 20      | kullback_leibler_divergence      | Adamax      |  relu | 256    |Dropout(0.55); Dropout(0.55) | 98.39 |
| Xavier Uniform (glorot_uniform) | 20      | kullback_leibler_divergence      | nadam      |  relu | 256    |Dropout(0.5); Dropout(0.5) | 98.25 |

## Dataset Augmentation Techniques

* The file ```Image Dataset Augmentation.ipynb``` visualizes how to augment your image dataset by considering the MNIST dataset and a single image. Such Augmentation would 
   * Increase the size of your dataset preventing overfitting to a certain degree
   * Make more robust
* The Keras ImageDataGenerator is used.
   * This accepts transformations to apply on the image like rotation angle, etc
   * It generates the images at run/training time and feeds the images to the model itself
   * Although this increase traning time a little it reduces memory requirements








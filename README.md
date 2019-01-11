# Neural Network Basics
Choosing optimum model hyperparameters 

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

## Final Score Card

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








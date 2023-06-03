# Learning_1DCNN
To learn and leave my learning about 1DCNN in my path

# Base 1DCNN model that i'm considering 
      layers.Conv1D(filters=64, kernel_size=3, activation='relu'),
      layers.MaxPooling1D(pool_size=2),
      layers.Dropout(0.5),
      layers.Conv1D(filters=128, kernel_size=3, activation='relu'),
      layers.MaxPooling1D(pool_size=2),
      layers.Flatten(),
      layers.Dense(latent_dim, activation='relu'),
 why am i not using gradually decreasing units like simple dnn check the things to consider for the documentation.
 
 # Why
Kernel size: A kernel size of 3 is used in the Conv1D layers. This size is commonly used for 1D convolutional operations and can effectively capture local patterns and dependencies within the sequence. Smaller kernel sizes allow the model to capture fine-grained details, while larger kernel sizes can capture broader patterns. You can experiment with different kernel sizes to find the optimal choice for your specific task.

Units: In the suggested model, 64 units are used in the first Conv1D layer, and 128 units are used in the second Conv1D layer. The number of units determines the capacity and complexity of the layer. Increasing the number of units allows the model to learn more complex patterns and capture more high-level features. However, it's important to strike a balance to avoid overfitting, especially with limited data. You can adjust the number of units based on the complexity of your task and available computational resources.

# Jun 3 2023 -1:02
Filters: The number of filters in the Conv1D layers determines the number of patterns the model can learn. I selected 64 filters in the first Conv1D layer and 128 filters in the second Conv1D layer to capture a wide range of patterns in the input data.

Kernel Size: The kernel size determines the size of the sliding window used for convolution. I chose a kernel size of 3, which allows the model to capture local patterns and relationships within a small window of neighboring data points.

Activation Function: ReLU (Rectified Linear Unit) activation function is used in the Conv1D layers to introduce non-linearity and enable the model to learn complex patterns. It helps the model capture both positive and negative features in the data.

Pooling: MaxPooling1D layers are added after each Conv1D layer to downsample the output and reduce the spatial dimensions. This helps in extracting the most important features while reducing the computational complexity of the model.

Flatten: The Flatten layer is used to convert the 3D output from the Conv1D layers into a 1D vector that can be fed into the Dense layers.

Dense Layers: I added two Dense layers after flattening the output. The first Dense layer has 256 units, which allows the model to learn higher-level representations and capture more abstract features. The second Dense layer with a single unit and sigmoid activation function is used for binary classification.

Dropout: Dropout regularization is applied after the first Dense layer with a dropout rate of 0.5. It helps in reducing overfitting by randomly disabling 50% of the units during training, forcing the model to learn more robust features.

Compilation: The model is compiled with binary cross-entropy loss, which is suitable for binary classification problems. The Adam optimizer is used to optimize the model parameters, and accuracy is chosen as the evaluation metric.

The parameter selection process involved considering the complexity of the input data, the desired model capacity, and avoiding overfitting. By gradually increasing the number of filters and units in the model, we can capture more intricate patterns and achieve higher model capacity. Dropout regularization is included to prevent overfitting, and appropriate activation functions are chosen to introduce non-linearity.

To further increase accuracy, you can consider:

Adding more Conv1D layers or increasing the number of filters to capture more detailed patterns.
Adjusting the kernel size to match the scale of patterns you expect in the data.
Experimenting with different network architectures, such as adding recurrent layers (e.g., LSTM) for capturing temporal dependencies.
Applying data augmentation techniques to increase the diversity and size of the training dataset.
Fine-tuning hyperparameters, such as learning rate, batch size, or dropout rate, through systematic experimentation and validation.

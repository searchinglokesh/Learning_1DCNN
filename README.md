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

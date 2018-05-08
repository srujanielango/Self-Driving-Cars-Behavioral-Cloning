# Self driving car simulation using behavioral cloning

Adopted model architecture from Nvidia's self-driving car paper, 

link: https://images.nvidia.com/content/tegra/automotive/images/2016/solutions/pdf/end-to-end-dl-using-px.pdf

Drive.py collects video input from 3 cameras, steering angle, brake, acceleration and speed information by driving a car simulator (unity 3D) around a track multiple times. Recorded input data is stored in driving_log.csv. This input is fed into CNN model and the model trained with input data is stored as .h5 file.

Model.py has the CNN model with the architecture - 9 layered (1 normalization layer, 5 convolution layers, 3 fully connected layers). First three convolutional layers are strided and 2x2 stride and 5x5 kernel. The last two convolutional layers are not strided ones and have a 3x3 kernel size.

The trained model .h5 file is fed back to the simulator and is used to drive the car autonomously aorund the track. 

Utils.py contains functions for loading image, resizing it, flipping and adjusting brightness, generating batches to feed into the model



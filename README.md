# Semantic Segmentation
### Overview
The goal of this project is to label the pixels of a road in images using a Fully Convolutional Network (FCN).

### Build the Neural Network

The NN is based on the network depicted in Fully Convolutional Networks for Semantic Segmentation by Jonathan Long, Even Shelhamer, and Trevor Darrel. Following is the architecture.

![nn](/nn.JPG)

All code is in main.py. 

The function load_vgg() loads the pretrained VGG16 model and returns its input, keep probability, layer 3, layer 4 and layer 7.

The function layers() defines the network.

The function optimize() reshapes the output and labels, then uses a standard cross entropy loss function and Adam Optimizer.

The function train_nn() trains the neural network and print out the loss during training like following.

![log](/log.JPG)

### Neural Network Training

On average, the model decreases loss over time. It starts with very high loss like 1.48, and decrease greatly to 0.17 at the end of epoch 1. It continues to decrease and reach ~0.03 in the middle (epoch 30), and finally gets 0.007 (epoch 55).

The number of epoch and batch size is set to 55 and 6. Other combinations like 60:5, produces similar results. Fewer epochs, such as 30, does not reach the lowest loss.

The project labels most pixels of roads close to the best solution. The images of latest run is included in folder /1532344864.3118956. Following is some samples.

![um_000006](/1532344864.3118956/um_000006.png)



![um_000013](/1532344864.3118956/um_000013.png)



![uu_000006](/1532344864.3118956/uu_000006.png)



![uu_000089](/1532344864.3118956/uu_000089.png)



![uu_000098](/1532344864.3118956/uu_000098.png)

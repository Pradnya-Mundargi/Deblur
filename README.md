# Neural Network for Image Deblur 

This Project attempts to correct the Blur caused by motion of a camera in a stationary scene.

### __Model Details__:
The model has the typical architecture of a GAN consisting of a generator and a discriminator. The generator, which is also the delurring model, has multiple finer to coarser layers, similar to a gaussian optimising network. Each scale consists of a convolution block, followed by 19 resblocks and another convolutional layer in the end. The last image in each layer is upsampled and concatenated with the input image at the next scale. Being a multi scaling model, images were scaled to 124×124, 64×64,32×32. <br>
The discrimminator has 8 convolutional layers, followed by a fully connected layer and gives an output of either ’blur’ or ’not blur’ using a sigmoid activation function. <br>
The activation function within each layer is the Leaky Relu.<br>
PSNR was used as a loss function.<br>

### __Training Details__:
The model was implemented in Tensor-Flow 2, with NVidia Tesla K80 GPU for training. The GOPRO dataset was used for training as well as testing our model.

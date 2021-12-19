

## Convolutional neural network

- Categorization, detection and segmentation
- Categorization -> choose the what but not the where
- Detection/Localization -> define the image region, what and where
- Semantic segmentationh, assign one label to each pixel, the what an where (pixel wise)


### Categorization
- Why is it difficult?
- Intra-class variability, hay muchas clases que clasificar
- Inter-class variability, dentro de una clase, hay muchas cosas distintas
- Incluso para una sola cosa, tanto el punto de vista de la camara, como la iluminacion pueden cambiar
- no solo, sino occlusion(oclusion), clutter(desorden), deformation(deformaciones)

### CNN
- Deep, feed-forward network with convolutional layers
- Polling layers
- Fully connected layers
Una red neural convolucional, es una red profunda, en la que se le dan las cosas de antemano, con capas convolucionales, así se crea un
set de layers, conectadas

#### Ingredientes
- GPU-powered libraries
- GPU
- Training data

#### Layers: convolution
- 2D Convolutional layer
- FIlter size
- Number of filters
- Stride el kernel lo podemos mover de 1 en 1 o de mas en mas, eso lo especificamos con stride
- Padding; aumentar la imagen en padding pixeles, valid no paddign, same pad que el output sea igual que el input
- Activation: ReLu -> Rectified linear unit, cogemos el mayor o 0 si es negativo
               - Sigmoide  1/(1+e^(-x))
- Polling reduces size of input, max pooling, average pooling, pool size, stride
- layers, dense, fully connected layer, parameters, number of units, and activation
- Layers output, dese layer with softmax activation, as many units as categories
- softmax -> funcion que nos da la probabilidad de que una clase sea la correcta, para ello, y a partir de una serie de outputs de la
              capa anterior, se computa, e^elemento/sum(e^los otros elementos), esto se hace en la ultima capa, en las otras, normalmente,
              iria la sigmoide o relu (rectified linear unit)

### Sequential model
- Si combinamos lo anterior, tenemos bastantes filtros 2d de convolucion, a los que hacemos un pooling de valor maximo.
- Y tenemos muchas fully connected layers que van disminuyendo el tamaño, al final tenemos una layer con softmax
- Modelo sequencial ,labels, one-hot vector encoding, que relaciona la salida con su encoding, clase 1 es -> [0,1,0,0]
- Modelo tiene que ser compilado, el proceso de compilado, necesita 3 parametros, optimizer, loss and metrics
  - Optimizer, controla el ratio de aprendizaje y se ajusta mediante backpropagation
  - Loss -> target function to be minimized -> categorical_crossentropy
  - metrics: accuracy

### Training, data batch
- Sample = image
- Gradient step: model is updated after each batch
- Epoch, lo que tarda en ver todo el batch de samples






# Block 3

- histogram is invariant to rotations
- We can split the image into regions and compute the histogram of each region

Vector histogram = 
 --------------------------------------------------------------------------------
|         h1           |              h2              |             h3           |
 ---------------------------------------------------------------------------------
 
 Tenemos 2 banderas y queremos compararlas, podemos ver el hstograma, pero si son similares colores pero rotados no podemos, por eso queremos el histograma por seccions,
 
 # descriptor. Statistic mean, variance, entropy 
 
 ## 1st approach:
 - A descriptor is a vector of number with the statistics of the picture 

## 2nd approach:
- Compute de gradient, that have orientation and magnitude. For each pixel compute the gradient and compute a histogram of orientations

## Shape descriptors
Image moments, An image moments of order i, j (Mij) a sum over all the possible pixels and compute the coordinates and the intensisty value at that possition


M00 = ExEy I(x, y)
M01 = Ex Ey 1*y*I(x, y)

M10 = ------>
      ------->
      
      
      
      
      
      
      
      
    ___________________-
    
    
# 15/11/2021
  
## Practica teoria
   
- Based on optical flow. 
Third  type of segmentation, low level feature, kind of descriptor, represent motion.

Possible application. Blur background in videocalls

- Basic method:
1. Compute optical flow between sequential frames
2. For each pixel, compute magnitude of optical flow
3. Normalize OF magnitude in [0, 1]
4. If Mag(x,y) > T, then (x,y) is foreground

Segmentation, decision per pixel -> background vs foreground
Color -> single image
Image difference and optical flow -> videos
Noise reduction techniques
   
## Theory


Si queremos un sistema que sea capaz de clasificar una imagen necesitamos algo, que nos de la semantica de la imagen. Así debe de habr algo en medio que nos de esto.
Dadas un conjunto de descryptors de imagen, como podemos seàrar un avion de una moto, así necesutamos un algoritmo u algo, que sea capaz de aprender.
Para ello, introducimos el concepto de machine learning.

Que es machine learning? 
- Campo de la computer science que da a los ordenadores la habilidad de aprender sin estar explicitamente programados. Esto va en contra de aplicar reglas. 
- Metodos:
 - Arboles de decision
 - Redes baesianas
 - Redes neuronales
 - Algoritmos geneticos
 
 Concepto de classificacion.
 proceso general en relacion a la categorizacion, el proceso necesita entender, reconocer, y diferenciar los ideas y objetos que queremos.
 Qué necesitamos para realizar la clasificacion:
 - Dataset: contains samples and labels, Para cada sample tenemos una label:
      S1 -> 1
      S2 -> 2
      S3 -> 3
      .
      .
      .
      .
      
  Splitrs: Training to learn parameters of the model (classifier)
  
  En nuestro dataset, una parte se usa para entrenar, y la otra para tune los hyperparameters e.g: k in kNN.
  Hyperparameters, un parametro que nosotros como progrmamadores necesitamos experimentar para conocer.
  
  Test, como de bien funciona nuestro coso y eso.
  Imagina que tenenmos un detector de faces, este se entrena con unas caras, pero que funcione con todas las demás tambien, para ello el test. Y saber si podemos reconocer las cosas y en el tanto por ciento que se puede.
  
  - Accuracy, how often the classifier correct prediction:
  Acc = correct/total * 100
  
  - Confusion matrix, con la precision no sabemos en que grado falla nuestro sistema, para eso, para saber la distribucion de los errores, usamos la confusion matrix, con un conjunto de filas y columnas, tenemos las test labels and the predict labels, y hacemos una tabla, así sabemos las que teoricamente eran de una clase, y despues acabaron siendo de esa clase, o si al final terminaron siendo de otra clase y viceversa. En la diagonal de la matrix, tenemos la cantidad total de clasificaciones corectas. Así qie tenemos nuestro clasifier, cual es el mejor, pues no solo tenemos que fijarnos en las buenas, sino que tambien en las que no han sido stimadas correctamente. Para saber estp, tenemos que normalizar, dada la matriz con valores absolutos, obtener una matriz con valores relativos. Para tener un solo parametro que lo exprese, haremos la media de la diagonal, para saber la precision media de nuestro sistema con las clases proporcionadas.

- Un clasificador simple, tenemos un conunto de entrenamiento, imagina que queremos separar personas de los demás, en este caso, tenemos people contra lo demás. Una de las cosas que podemos usar es cimpute el histograma de gradientes para cada smaple. y después podemos computar la distancia entre los targets y los training samples.
Compute ka dustabcua ebtre ek target y el training sample, chi squared, buscar.

Tenemos la distriucion de las personas y la distribucion del fondo. Para saberlo, miramos los vecinos mas cercanos, pero cual cogemos el mas cercano los 3, 4, 5 mas cercanos, para eso tenemos que poner a los hyperparametes.

Tipos de clasificadores, supervisados vs semi-supervised vs unsupervised. Do we have label for all trainining samples -> supervise, some labels for some sample -> semi-supervised, we dont have any labels -> unsupervised.

Classifer populares:
- Support Vector Machine
- Boosting
- Decision trees
- Neural network ( es algo que usaremos al final del block que es relacionado con convolutional neural network, lo veremos despues con mas detalle)

En opencv, tenemos ya esto hecho, Así que necesitamos poder obtener buenos descriptores. clase padre, cv::ml::StatModel, most importatn method for us:
- isTrained()
- train(trainSmples, ROW_SAMPLE, labels)
- predict (testSamples, predictions)
- getVarCount() //Debugging, nos da la longitud de las variables de los descriptors.

- Lest focus on the svm. Basicamente, la idea es la siguiente, esta es la distribucion de los samples, para separarla, debemos computar la linea que separa mejor la distancia entre las  2, esta linea tiene que estar en la mayor distancia de las 2 (slide, samples not simple (SVM)), son binaty classifier, solo podemos clasificar 2 cosas. Cuál es el hyperparametro que podemos separar aquí, el margen, parametr

Imagina separar algo así

    *
 *  .  . *
 * . .    *
   * *

Es imposible dibujar una linea que separe los . de los *

- La idea es encontrar un espacio dimensional superior, que podemos avanzar los . y poner un plano entre estos y los *.

Tenemos varios tipos de kernel:
- Linear
- Polinomico
- Radial basis
- Sigmoid

Choice depends on the problem.

## Pedestrian detector.
- Features: histogram of gradientes
- Given a dataet, split into:
 - Training .> learn SVM parameters
 - Validation -> tune hyper-parameters (e.g margin) 


  
  

 






   

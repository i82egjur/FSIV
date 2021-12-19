
## Machine Learning For Computer Vision

- Hasta ahora, tenemos la imagen, el descriptor, y sabemos lo que queremos, que falta?
- Como separamos automaticamente, aviones de motos por ejemplo? -> Learning

## Que es el machine learning?
- Wikipedia lo define como un subcampo de la ciencias de la computacion, que de acuerdo a Arthur Samuel en 1959, le da a los ordenadores
  la capacidad de aprender sin ser explicitamente programados.

- Enfoques:
  - Arboles de decision
  - Artificial neural networls
  - Redes bayesianas
  - Algoritmos geneticos

- Concepto de la classificacion
  - Según wikipedia, classiciacion es un proceso general relacionado con la cotegorizacion, el proceso en el cual, ideas y objetos son
    reconocidos, diferenciados y comprendidos.
  - Ingredientes de la clasificacion.
  - Dataset: Con las imagenes y etiquetas acerca de la categoria del sample.
  - Splits (Divisiones):
    - Training: Para aprender los parametros de un modelo
    - Validacion: Para sintonizar hyperparametros
    - Test para predecir rendimiento a la hora del despliegue
  - Metricas:
    - Precision: Como de amenudo hace una prediccion correcta:
      - Acc = correct/total*100
    - Confusion matrix: Muestra detalles sobre correctas e incorrectas clasificaciones para cada categoria, hay que normalizarla, haciendola
                        en porcentajes, la media de la diagonal -> es la media de la precision
                        
- Clasificadores populares:
  - Tipos de clasificadores:
    - Supervisados vs semi-supervisados vs sin supervisar
      - Dependiendo si tenemos etiquetas para todos los samples
    - Dentro de los supervisados: Tenemos Support Vector Machines, Boosting, Decision Trees, Neural Networks
  - En opencv, el machine learning hereda de la clase cv::ml::StatModel, dentro, elegimos ciertos metodos, 
  - isTrained -> devuelve si un modelo esta o no entrenado,
  - train entrenar, a partir de un conjunto de samples,  layout (ROW/COL_SAMPLE, cada sample de entrenamiento es una fila/columna de samples)  ,obtiene las respuestas asociadas a los samples, 
  - predict(testSamples, predictions), predice a partir de los samples cosas,
  -  getVarCount obtiene un numero de variables en samples de entrenamiento
  -  Dentro de los clasificadores populares: Tenemos, svm, boosting y los arboles de decision

  - SVM, Support Vector Machines, 
    - SVM es un clasificador linear que busca categorizar los samples en clases separadoas por un hyperplano, para ello, busca
      que el hyper plano que genere deje el mayor margen posible. Aunque puede ser que las clases no sean lineales, por tanto
      se busca mediante un kernel, añadir una profundida que haga posible el hyperplano. Hay varios tipos de kernels, lineal, 
      polinomial, base radial, sigmoide. La eleccion depende del problema. Se puede hacer en multiclase, C1 vs {c2, c3}
      
      






















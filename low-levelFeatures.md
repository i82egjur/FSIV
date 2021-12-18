## LOW LEVEL FEATURES

- Una feature (caracteristica), es una pieza de informacion que es relevante para resolver una determinada tarea.  
- Hay varios tipos, caracteristicas basadas en el gradiente, en la deteccion de bordes, flujo optico (este nos da el patron de movimiento producido por el movimiento relativo entre un observador y una escena)
  - Basadas en el gradiente:
   - Buscamos un cambio direccional en la intensidad de una imagen. Esto se puede hacer mediante convolucion, aplicando el filtro de sobel o
     laplacian of gaussian
  - Basadas en la Cannuy deteccion de bordes (Canny edge detector)
    - Se nos presenta un problema y es que no es tan facil saber si algo es o no un borde. Para ello, usamos el algoritmo de canny
      este es uno de los más famosos para la deteccion de bordes. Sus pasos principales son:
      - Edge enhancing (Resaltar los bordes)
      - Non-maxima suppresion
      - Hysteresis
      
      - Edge enhancing:
        - Suavizamos la imagen mediante el filtro derivativo de gauss, para obtener las componentes horizontal y vertucal del gradiente y obtenemos
          la magnitud y direccion del gradiente, asi creamos un par de imagenes em magnitud y ed direccion. 
       
      - Non-maxima suppresion:
        - El objetivo es a partir de la imagen con la magnitud del gradiente, que puede contener bordes de mas de un pixel, pues queremos 
          afinar todos los bordes para que sean un pixel de gordos, para ello seguimos los siguientes pasos.
          - Descretizamos el gradiente en las 4 direcciones principales 0º, 45º, 90º, 135º

- Optical flow:
  - El flujo óptico, se utiliza para ver un patron de movimiento aparente de un objeto, en una foto, hay pixeles fijos y otros en movimiento, 
    para ver esto, para cada pixel, calculamos la direccion de movimiento, esto tiene muchas aplicaciones, como la video vigilancia.
  - La primera cosa que debemos de comprender es que el flujo optico es un vector, y por tanto tiene un modulo, direccion y sentido.
  - Para calcularlo, existen varios algoritmos, entre otros, esta el de Lucas-kanade.
    - Algoritmo de lucas-kanade, este se basa en tres suposiciones. 
      - El brillo no cambia entre frames
      - Entre frames el movimiento de los objetos no va a ser muy grando
      - Coherencia spacial, los puntos vecinos pertenecen a la misma superficio y tienen movimiento similar
      - I(x(t), t) = I(X(t+dt), t + dt)
      

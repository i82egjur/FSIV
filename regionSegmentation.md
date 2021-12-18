


- Que es la segmentacion?
- Definir automaticamente regiones de interes para nuestro problema.
- Esto lo podemos hacer, basandonos en la diferencia entre imagenes, en el color, o en el flujo optico.

- diferencia entre imagenes
-  La primera opcion, basada en la diferencia entre imagenes, es calcular la diferencia en valor absoluto entre un frame y el siguiente,
   para cada pixel, se hace un threshold, y dependiendo si esta diferencia es mayor o menor que un threshold, será o no un pixel de foreground o de 
   background. Esta es muy sensible a ruido, así que aplicamos una operacion de apertura y cerrado. para reducir el ruido.
   
 - La segunda opcion es mediante un modelo de aprendizaje del fondo así, si queremos saber si es de foreground o de background, lo restamos
   y buscamos una salida.
   Para esto, cogemos unos X frames de entrada, calculamos para cada pixel, su media y desviacion tipica, con esto, para saber si un pixel
   es de fondo o de frente, restamos el pixel de la imagen con el de la misma posicion en la media, y si la represemtacion en valor absoluto
   de este es mayor que un parametro K por la desviacion tipica, este será de frente. El problema es que despues habrá que actualizarlo para cada
   T frames, para ello, para cada pixel:
   new_model = alfa * old model +(1-alfa)*new model
   
- Segmentacion basada en colores
  - Buscamos seleccionar un grupo de pixeles cuyo color esta incluido en un set de interest 

- Basada en el flujo optico
   - Vemos el cambio de una imagen a traves del tiempo
   - Metodos basicos:
    - Calculamos el flujo optico entre una secuencia de frames: t-1 con t
    - Para cada pixel, calculamos la magnitud del flujo optico
    - Normalizamos el flujo optico en [0, 1]
    - Si la magnitud(y, x) > T, entonces (y, x) es de frente
    - Resumen, calculamos el movimiento para cada pixel, si se ha movido, pos no es de fonod.

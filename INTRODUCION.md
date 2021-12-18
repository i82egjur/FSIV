

## ENTENDIMIENTO DE IMAGEN

- Nuestro objetivo es enseñar a ordenadores a descubrir automaticamente objectos en imagenes.
- El problema es como podemos describir una imagen, ya que para un ordenador, una imagen no es mas que una matriz de numeros
- Para describir la imagen, utilizamos los "_descriptors_".
  - Descriptors:
    - Hay varios tipos, descriptores de color, textura y forma:
      - Colour descriptors:
        - Antes de ello, nos prguntamos que es el color, este es una percepcion humana, los objetos de por sí no tienen color, 
          la luz se refleja sobre los objetos y dependiendo de si estos la reflejan, la absorben y en que grado, tendran un color u otro.     
        - Encontramos dos modelos, luz aditiva (cuando los componentes de la luz se unen, sale la luz blanca) o pigmentos substractivos(al sumar pigmentos, sale el negro):
        - Dentro del color, tambien encontramos espacios de color, entre otros el 
          -  Rgb que los divide en red gren and blue 
          -  HSV/HSL, que los divide en hue tono, saturation, value/lightness      
          -  Una vez que conocemos esto, creamos nuestro descriptor de color, usando histogramas para la distribucion del color.
          -  El problema de los histogramas es que es invariante a las rotaciones, por ello, podemos crear el histograma por secciones de una 
             imagen. 
       - Texture descriptors:
        -  La textura de una imagen, nos da informacion sobre la disposicion espacial de las intensidades de una imagen.
        -  Un descriptor, es un vector con las estadisticas de una imagen, media, varianza, entropia, higher order
        -  Por ejemplo, un buen descriptor, sería calcular el gradiente, que tiene orientacion y magnitud, para cada pixel, calcular este 
           gradiente y calculamos despues el histograma de las orientaciones
      - Shape descriptors:
        - El descriptor de la imagen, puede hacerse como el momento de la imagen, este se ve como una media ponderada de las intensidades 
          de un pixel o una funcion de estos momentos, elegidos para tener alguna propiedad o interpretacion atractiva          

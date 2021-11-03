

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

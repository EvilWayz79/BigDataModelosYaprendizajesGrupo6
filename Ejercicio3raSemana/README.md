Ejercicio grupo 6 MNIST Fashion


Este dataset es un conjunto de datos de 60000 imágenes en escala de grises de 28x28, adicional contiene un conjunto de prueba de 10000 imágenes.

PROCEDIMIENTO

Iniciamos cargando el conjunto de datos utilizando keras y posterior a ello se realiza el preprocesamiento de datos para las redes neuronales. Mostramos la imagen en escala de grises.
Utilizamos una dimensión extra al final de cada imagen, convirtiendo así la forma de las imágenes de (28, 28) a (28, 28, 1). Posterior imprimimos la forma de los datos de entrenamiento y prueba para verificar que tengan las dimensiones correctas.
A continuación, convertir vectores de clase en matrices de clases binarias y definimos un modelo de red neuronal convolucional utilizando Keras.
A partir de ello empezamos la fase de entrenamiento durante el número especificado de épocas, utilizando los datos de entrenamiento y validación proporcionados. La validación se utiliza para monitorear el rendimiento del modelo en un conjunto de datos que no se utiliza para el entrenamiento y puede ayudar a detectar el sobreajuste.
Por último, evaluamos el rendimiento del modelo en el conjunto de datos de prueba mediante una matriz de confusión y repetimos el procedimiento con el Train.

FUNCION DE CADA CAPA

1.	keras.Input(shape=input_shape): Esta es la capa de entrada del modelo, donde input_shape especifica la forma de los datos de entrada. Por ejemplo, si input_shape es (28, 28, 1), significa que las imágenes de entrada son de 28x28 píxeles en escala de grises.

2.	layers.Conv2D(32, kernel_size=(3, 3), activation="relu"): Esta es una capa convolucional con 32 filtros de tamaño 3x3. Utiliza la función de activación ReLU.

3.	layers.MaxPooling2D(pool_size=(2, 2)): Capa de max-pooling para reducir el tamaño espacial de la salida de la capa convolucional. Utiliza una ventana de pooling de tamaño 2x2.

4.	layers.Conv2D(64, kernel_size=(3, 3), activation="relu"): Otra capa convolucional con 64 filtros de tamaño 3x3 y ReLU como función de activación.

5.	layers.MaxPooling2D(pool_size=(2, 2)): Otra capa de max-pooling para reducir aún más el tamaño espacial de la salida de la capa convolucional.

6.	layers.Flatten(): Esta capa se utiliza para aplanar la salida de la capa anterior para que pueda ser alimentada a una capa densa.

7.	layers.Dense(64, activation='relu'): Capa densa con 64 unidades y función de activación ReLU.

8.	layers.Dropout(0.2): Capa de dropout para regularización, que ayuda a reducir el sobreajuste al apagar aleatoriamente algunas de las neuronas durante el entrenamiento.

9.	layers.Dense(num_classes, activation="softmax"): Capa de salida con num_classes unidades y función de activación softmax, que se utiliza para la clasificación multiclase. Cada unidad en esta capa representa la probabilidad de que la entrada pertenezca a una de las clases.


ANALISIS MATRIZ DE CONFUSION

* ACCURACY TEST

En el conjunto de datos de prueba se ha obtenido una pérdida de aproximadamente 0.2554 y una precisión de aproximadamente 0.9074. Estos valores indican el desempeño del modelo en datos que no ha visto durante el entrenamiento. Una pérdida más baja y una precisión más alta son indicativos de un mejor rendimiento del modelo.

* ACCURACY TRAIN
En el conjunto de datos de entrenamiento y se ha obtenido una pérdida de aproximadamente 0.2554 y una precisión de aproximadamente 0.9074. Es importante observar cómo se desempeña el modelo tanto en el conjunto de datos de entrenamiento como en el conjunto de datos de prueba para evaluar su rendimiento general y detectar posibles problemas de sobreajuste.


    | Label | Description |
    |:-----:|-------------|
    |   0   | T-shirt/top |
    |   1   | Trouser     |
    |   2   | Pullover    |
    |   3   | Dress       |
    |   4   | Coat        |
    |   5   | Sandal      |
    |   6   | Shirt       |
    |   7   | Sneaker     |
    |   8   | Bag         |
    |   9   | Ankle boot  |

MATRIZ DE CONFUSION EN TRAINING

    | 0 | 5518 | 1    | 91   | 79   | 9    | 0    | 292  | 0    | 10   | 0    |
    |:-:|---------------------------------------------------------------------|
    | 1 | 2    | 5931 | 2    | 50   | 6    | 0    | 7    | 0    | 2    | 0    |
    | 2 | 67   | 4    | 5565 | 30   | 180  | 0    | 149  | 0    | 5    | 0    |
    | 3 | 95   | 17   | 46   | 5585 | 127  | 0    | 128  | 0    | 2    | 0    |
    | 4 | 5    | 3    | 298  | 112  | 5369 | 0    | 209  | 0    | 4    | 0    |
    | 5 | 0    | 0    | 0    | 0    | 0    | 5942 | 0    | 44   | 1    | 13   |
    | 6 | 692  | 8    | 536  | 78   | 374  | 0    | 4299 | 0    | 13   | 0    |
    | 7 | 0    | 0    | 0    | 0    | 0    | 16   | 0    | 5915 | 0    | 69   |
    | 8 | 16   | 0    | 19   | 6    | 15   | 5    | 14   | 2    | 5923 | 0    |
    | 9 | 0    | 0    | 0    | 0    | 0    | 11   | 0    | 146  | 0    | 5843 |
    | - | 0    | 1    | 2    | 3    | 4    | 5    | 6    | 7    | 8    | 9    |
        

Los resultados tienen sentido, por ejemplo el valor 6 representa a camiseta y guarda las siguientes relaciones con las otras prendas de vestir

      CODIGO  NOMBRE        COINCIDENCIAS 
    |   0   | T-shirt/top | 692
    |   1   | Trouser     | 8
    |   2   | Pullover    | 536
    |   3   | Dress       | 78
    |   4   | Coat        | 374
    |   5   | Sandal      | 0
    |   6   | Shirt       | 4299
    |   7   | Sneaker     | 0
    |   8   | Bag         | 13
    |   9   | Ankle boot  | 0



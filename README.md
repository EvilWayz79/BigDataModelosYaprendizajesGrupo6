# BigDataModelosYaprendizajesGrupo6
# ----------------------------------- #
Grupo 6 Maestria UIDE
# ----------------------------------- #

Integrantes
# ----------------------------------- #

# Lili Amán
# Santiago Borja
# Renato Jacome
# Rubén Recalde

# ----------------------------------- #

# OJO el archivo de training por restricciones de tamaño de GitHub fue recortado en 10k Líneas

# ----------------------------------- #

Paso 1:
Obtener los datos:
mediante las librerias basicas: pandas
train_data=pd.read_csv("mnist_train.csv")
test_data=pd.read_csv("mnist_test.csv")

# ----------------------------------- #

Paso 2:
Exploracion de los datos:
train_data.info()
#el resultado me indica que tiene 60,000 filas y 785 columnas, todas con valores enteros de 64 bits, y ocupa alrededor de 359.3 megabytes de memoria en tu sistema.

# ----------------------------------- #

test_data.info()
#la interpretación de los resultados me indica que DataFrame contiene 10,000 muestras, cada una representada por 785 características (784 para los valores de los píxeles y 1 para la etiqueta). El DataFrame utiliza aproximadamente 59.9 megabytes de memoria en tu sistema.

# ----------------------------------- #
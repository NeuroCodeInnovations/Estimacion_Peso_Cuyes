# Estimación del peso del cuy utilizando ResNet50

Se muestra una breve descripción de los códigos implementados para el proyecto en Colab

-> Data_Augmentation : 
   Código para realizar un aumento de las imagenes realizando rotaciones y aplicando un efecto blur

-> ResNet50_Estimacion_Cuyes : 
   Códigos para realizar transfer learning de la arquitectura ResNet50. Se modifica el modelo para regresión.

   _1 : Primer resultado
       * No aplicamos Data Augmentation al dataset
       * Utilizamos la media y desviación estandar de ImageNet.
       * Hiperparámetros: LR = 0.001, Epocas = 3

   _2 : Segundo resultado
       * Aplicamos Data Augmentation al dataset
       * Calculamos la media y desviación estandar del dataset.
       * Hiperparámetros: LR = 0.001, Epocas = 5

   _3 : Tercer resultado
       * Aplicamos Data Augmentation al dataset
       * Calculamos la media y desviación estandar del dataset.
       * Hiperparámetros: LR = 0.001, Epocas = 5, Scheduler (patience = 3)

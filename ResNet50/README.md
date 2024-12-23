# Estimación del peso del cuy utilizando ResNet50

Se muestra una breve descripción de los códigos implementados para el proyecto en Colab


# Índice

1. [Data_Augmentation](#dataaugmentation)
2. [ResNet50_Estimacion_Cuyes](#resnet50estimacioncuyes)
   1. [Primer Resultado](#primerresultado)
   2. [Segundo Resultado](#segundoresultado)
   3. [Tercer Resultado](#tercerresultado)


#Data_Augmentation :  
   Código para realizar un aumento de las imagenes realizando rotaciones y aplicando un efecto blur

#ResNet50_Estimacion_Cuyes :  
   Códigos para realizar transfer learning de la arquitectura ResNet50. Se modifica el modelo para regresión.

##_1 : Primer resultado  
       * No aplicamos Data Augmentation al dataset  
       * Utilizamos la media y desviación estandar de ImageNet.  
       * Hiperparámetros: LR = 0.001, Epocas = 3  

##_2 : Segundo resultado  
       * Aplicamos Data Augmentation al dataset  
       * Calculamos la media y desviación estandar del dataset.  
       * Hiperparámetros: LR = 0.001, Epocas = 5  

##_3 : Tercer resultado  
       * Aplicamos Data Augmentation al dataset  
       * Calculamos la media y desviación estandar del dataset.  
       * Hiperparámetros: LR = 0.001, Epocas = 5, Scheduler (patience = 3)  

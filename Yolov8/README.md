# Estimación y Detección del peso del cuy utilizando ResNet50

Se muestra una breve descripción de los códigos implementados para el proyecto en Colab

## Data_Augmentation   
   Presentado en "DataAugmentation.md", en esta carpeta se muestran los links para acceder a las imágenes luego de aplicar transformaciones como rotaciones, reflejar y/o desenfoque.
   
## YOLO - Etiquetado y Entrenamiento   
   Códigos utilizados para el pseudoetiquetado y el entrenamiento del modelo de detección de cuyes:

   ### Etiquetado
       * Carpeta: PDSEI_Etiquetado_v1
       * Descripción: Mediante el uso de GroundingDino se generó un cuadro delimitador para las imágenes de entrenamiento y test, las cuales se encuentran dentro del archivo "BoundingBoxes.md".
       
   ### Entrenamiento del modelo
       * Carpeta: PDSEI_Etiquetado_v1 
       * Descripción: Se utilizó Yolov8 con la siguiente configuración: model.train(data='/content/drive/MyDrive/PDSEI/DataTrain/data.yaml', epochs = 30, batch = 64, imgsz = 640, device = 'cuda')
                      Para lo cual se utilizó las imagenes generadas en el Data_Augmentation. Los resultados del entrenamiento se encuentran en Entrenamiento_Yolov8.md
       * Resultados: Los mejores resultados durante el entrenamiento se encuentran en la carpeta "best.pt"
## YOLO Detect
  Utilizando GroundingDino para generar los cuadros delimitadores, se obtuvo el número de píxeles contenido dentro de este BoundingBox, en donde se filtró (considerando como referente 1.1 veces el valor de la mediana), obteniendo de esta forma un determinado número de píxeles para cada cuy, los cuales se dividieron entre su peso y se obtuvo un factor, al cual se le aplicó la mediana, y se obtuvo un factor general de 0.21215699704044025 gramos/pixeles.
  (Cabe mencionar que inicialmente se realizaron los filtros aplicando la media aritmética y la moda estadística, en donde se obtuvo un factor de 0.16315519540868295, esto se encuentra comentado dentro del código de PDSEI_Etiquetado_v1)
  ### Código:
      PDSEI_Etiquetado_v1
  ### Resultados:
      En "resultados1.txt" se muestra tanto el id del cuy como el peso real, peso estimado y el RMSE de cada id.
  ## YOLO Segment
  Utilizando Supervision y los cuadros delimitadores, se obtuvo el número de píxeles contenido dentro de la máscara de segmentación, en donde se filtró (considerando como referente 1.1 veces el valor de la mediana), obteniendo de esta forma un determinado número de píxeles para cada cuy, los cuales se dividieron entre su peso y se obtuvo un factor, al cual se le aplicó la mediana, y se obtuvo un factor general de 0.30078200402462574 gramos/pixeles.
  (Cabe mencionar que inicialmente se realizaron los filtros aplicando la media aritmética y la moda estadística, en donde se obtuvo un factor de 0.22083622891943683, esto se encuentra comentado dentro del código de Segmentacion)
  ### Código:
      Segmentacion
  ### Resultados:
      En "resultados.txt" se muestra tanto el id del cuy como el peso real, peso estimado y el RMSE de cada id.

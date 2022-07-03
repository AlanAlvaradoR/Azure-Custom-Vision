# Azure-Custom-Vision
Entrenamiento de una custom Vision de Azure 

![Logo de Custom Vision](https://github.com/AlanAlvaradoR/Azure-Custom-Vision/blob/main/imagenes/CVision.jpg)

## Requisitos

- Cuenta de [Azure](https://portal.azure.com/) con suscripción activa
- Computadora con Windows, Linux o MacOs

---------------------------------------------------------

## Pasos

1. Se inicia sesión en la página de [Custom Vision de Azure](https://www.customvision.ai/)

2. Se crea una nueva Nuevo Proyecto.

3. Se llenan los apartados de Nombre y descripción, después se da click en "Crear nuevo" en el apartado de recursos. Se desplegará otra pestaña.

4. Se le coloca un nombre, se selecciona la suscripción, grupo de recursos (si no se despliga ninguno es necesario crear un nuevo grupo de recursos nuevo desde el [Portal de Azure](https://portal.azure.com/) antes de seguir), después en el apartado de "tipo" se tienen 3 opciones:

    - **CognitiveServices** : Entrenamiento y predicción
    - **Custom/Vision Training** : Solo para entrenamiento
    - **Custom/Vision Predictions** : Solo para predicción
    
  Se selecciona Cognitive Services en esta ocasión ya que se entrenará y hará predicción.
  Después se selecciona la región y tipo de costo y se da click en "Crear recurso"
  
5. Volverá al menú de apartados inicial, ahora en recurso seleccionamos el que acabamos de crear. Se desplegarán más opciones.

6. Se selecciona el tipo de proyecto:

    - **Classificication**: Se dan varias imagenes de muestra dando una parámetro de qué es lo que hay en todas esas imagenes (Por ejemplo: fotos de un planeta) (Decirle a la IA qué es TODA LA IMAGEN)
    - **Object Detection**: Dentro de una imagen con distintos elementos, se indica por medio de un recuadro qué es un objeto en específico, así se podrá detectar ese mismo objeto dentro de otras imagenes que contengan más cosas aparte del objeto.
    
7. Se selecciona el tipo de clasificación:

    - **MultiLabel**: Darle imagenes con diferentes cosas dentro de las mismas.
    - **Multiclass**: Darle varias imagenes diferentes de # una misma cosa.
    
    En este caso se usará Multiclass.
    
8. En dominio se selecciona General [A2] ya que es el más reciente. Se puede usar alguno de los otros si lo que se desea identificar de la imagen coincide con el dominio, por ejemplo, ya hay un dominio en especifico para detectar comida, paisajes, etc. (Las versiones Compact estan optimizadas para dispositivos móviles, lo que las hace más rápidas y ligeras)

9. Se da click en "Crear proyecto".

10. Ahora se procede a descargar imagenes de los objetos o cosas que queremos clasificar, en este caso, si se quieren detectar cosas del espacio, se pueden descargar varias fotos de planetas, varias fotos de galaxias, varias fotos de nebulosas, varias fotos de meteoritos, etc.

11. Una vez con las fotos descargadas, se vuelve al recurso de Custom Vision y se da click en "Agregar imagenes".

12. Se seleccionan todas las imagenes de un objeto (por ejemplo, todas las fotos de una galaxia) y se suben, después en el parte inferior en "Tags" se coloca el nombre del objeto. Se debe ver parecido a esto:

![Imagen Subida Galaxias](https://github.com/AlanAlvaradoR/Azure-Custom-Vision/blob/main/imagenes/CVision.jpg)

10. Se da click en "subir imagenes" y después en "listo".

11. Deben aparecer las imagenes que subiste de fondo. Ahora se da click en "agregar imagenes" y se repite el proceso de subirlas y darle un nombre a otro objeto. Este proceso se repite hasta que se suban las fotos y se clasifiquen todos los objetos que se requieran.

12. Una vez terminadas de subir la fotos, es necesario también usar un "Tag negativo". Este tag es para indicar cosas que se parecen a las que queremos predecir, pero no nos interesan o podrian hacer que la IA se confundiera fácilmente. En este caso, si se tienen los Tags de: nebulosa, planeta y galaxia, es necesario agregar **por lo menos** un tag negativo de "estrella" ya que es algo con lo que puede confundir y no nos interesa que identifique. Para hacerlo, se descargan imagenes del objeto del tag negativo y se suben al igual que las otras, solo que al ponerle el "Tag" se da click en el espacio y se selecciona la opción de "Negativo".

13. Una vez agregado el tag negativo, se da click en el botón superior verde de "Train".

14. Se pedirá especificar el tipo de entrenamiento:

    - Quick Train: Entrenamiento rápido y con menos exactitud
    - Advanced Training: Entrenamiento con duración establecida por el usuario y más preciso
    
    En este caso se selecciona "Quick Train" para no perder tanto tiempo y se click en "Train".
    
 15. Abrirá una ventana donde indica el progreso en el entrenamiento. Se espera hasta que termine.

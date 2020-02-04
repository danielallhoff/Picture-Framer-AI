# Frame-Pictures

## Introducción
Este proyecto surge como una verdadera necesidad de los negocios que venden diferentes tipos de cuadros y encuadran imágenes. De forma sencilla, para que un cliente pueda decidir entre uno u otro, se coge únicamente las esquinas del cuadro y se comparan entre sí.
Mediante la utilización de Deep Learning, integrado en una aplicación móvil, es posible realizar una foto, elegir un cuadro y aplicarlo a la imagen. De esta forma es posible de verlo de forma completa y rápida, aportando valor al negocio.

En este caso, para facilitar un poco el problema he elegido un único diseño de cuadro aplicable. Se podría usar otros diseños con facilidad añadiendolo como condición una label(que indica que tipo de cuadro se va a aplicar) junto a la técnica del transfer learning: no necesitaríamos tantos datos como al principio.

## Detalles
Para esta tarea, se ha usado el modelo pix2pix que es una red condicional generativa adversaria(conditional Gan, cGan) usada en tareas de Images Translation. Necesita de gran cantidad de parejas de fotos, lo cuál es realmente complicado si se realiza a mano con una camára. Por tanto, se han realizado de forma simulada en el programa de desarrollo de videojuegos Unity. Eso ha permitido generar cientos de ejemplos que le permite a la red aprender la transformación de una imagen sin cuadro a otra con cuadro.

En concreto, en esta simulación se han modificado ángulo y distancia a la imagen, incluso cambios de tamaño del cuadro para que sea capaz de generalizar correctamente. Para probarla y probar si lo ha conseguido correctamente, he realizado una foto real: una imagen con un fondo real.



## Problemas
Al principio, al entrenar un buen rato, no he conseguido recibir buenos resultados. Parece que entre el overfitting que se ha producido y la poca variabilidad de fondo/imagen(he usado al principio únicamente 10 imágenes para el fondo y 10 para la imágen aproximadamente) no he conseguido obtener buenos resultados: en imágenes artificiales no vistas funcionaba correctamente, pero al pasar al mundo real tenía problemas.
 


# Frame-Pictures

## Introducción
Este proyecto surge como una verdadera necesidad de los negocios que venden diferentes tipos de cuadros y encuadran imágenes. De forma sencilla, para que un cliente pueda decidir entre uno u otro, se coge únicamente las esquinas del cuadro y se comparan entre sí.
Mediante la utilización de Deep Learning, integrado en una aplicación móvil, es posible realizar una foto, elegir un cuadro y aplicarlo a la imagen. De esta forma es posible de verlo de forma completa y rápida, aportando valor al negocio.

## Detalles
Para esta tarea, se ha usado el modelo pix2pix que es una red condicional generativa adversaria(conditional Gan, cGan) usada en tareas de Images Translation. Necesita de gran cantidad de parejas de fotos, lo cuál es realmente complicado si se realiza a mano con una camára. Por tanto, se han realizado de forma simulada en el programa de desarrollo de videojuegos Unity. Eso ha permitido generar cientos de ejemplos que le permite a la red aprender la transformación de una imagen sin cuadro a otra con cuadro.

En concreto, en esta simulación se han modificado ángulo y distancia a la imagen, incluso cambios de tamaño del cuadro para que sea capaz de generalizar correctamente.

## Problemas

Un problema ha sido la dificultad de que el generador del pix2pix sea capaz de converger a un loss bajo. Esto se debe a qué el discriminador ha convergido rápidamente a un valor de pérdida cercano a 0, imposibilitando al generador engañar al discriminador. Para solventar esto, se ha añadido a la entrada del discrimador un ligero ruido que conforme avanza el aprendizaje se reduce. Además, se ha añadido ruido en las etiquetas(label noise) con un 5% al discriminador, junto a un suavizado. 
Todos estos trucos los he extraído de: https://github.com/soumith/ganhacks/blob/master/README.md


## Resultados

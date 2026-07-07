# Clasificador de Animales con CNN

Implementación de una Red Neuronal Convolucional (CNN) con Keras para clasificar imágenes de 8 categorías de animales: Aves, Carpinchos, Elefantes, Gatos, Monos, Suricatas, Perros y Sapos.

---

## Contenido

- Preparación y división del dataset (80/20)
- Arquitectura V1: filtros crecientes 32→64→128→128 (~2.6M parámetros)
- Arquitectura V2: filtros constantes 32 (~619K parámetros)
- Análisis de overfitting y comparativa entre arquitecturas
- Prueba de predicción con imagen externa

## Conclusión principal

Ambas arquitecturas alcanzaron ~99% de accuracy en entrenamiento y ~59% en validación. La reducción del 75% en parámetros no mejoró la generalización, lo que indica que el cuello de botella es el tamaño y variedad del dataset, no la complejidad del modelo.

## Dataset

Las imágenes están disponibles en Google Drive. Para ejecutar el notebook es necesario agregar el acceso directo a Drive siguiendo las instrucciones de la sección 0.

## Tecnologías

Python · TensorFlow · Keras · NumPy · Matplotlib

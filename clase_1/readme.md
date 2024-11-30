# Detección de Manos con MediaPipe

Este proyecto utiliza la librería **MediaPipe Hands** para detectar y rastrear en tiempo real las manos y sus puntos clave (landmarks) en un video capturado por la cámara web.

## ¿Qué hace el código?

1. **Captura de Video**:  
   Utiliza la cámara web del usuario para obtener un flujo de video en tiempo real.

2. **Detección de Manos**:  
   Detecta hasta dos manos en cada cuadro del video, identificando 21 puntos clave (landmarks) por mano.

3. **Visualización**:  
   - Dibuja los puntos clave y las conexiones de las manos sobre un lienzo (`canvas`).  
   - Resalta la punta del dedo índice con un círculo amarillo.  
   - Si se está apuntando se cambia el círculo a azul. 

4. **Cálculos Vectoriales**:  
   - Calcula vectores entre puntos clave de la mano.  
   - Analiza las orientaciones mediante el coseno entre vectores para determinar relaciones geométricas entre los dedos.

---

## Condiciones para Cambiar el Círculo a Azul
El código analiza la posición y orientación de los dedos usando cálculos vectoriales. Se determina que el usuario está "apuntando" con el dedo índice si:

1. **El índice está extendido**:  
   El dedo índice apunta hacia adelante, mientras que los otros dedos (medio, anular y meñique) están doblados hacia la palma.

2. **Orientación relativa de los dedos**:  
   La orientación del índice (representada por el vector **B**) debe estar opuesta a la de los otros dedos (**C**, **D**, y **E**), lo que implica que el índice está alineado y los otros dedos no.



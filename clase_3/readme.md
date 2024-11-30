# Descripción del Código

Este código realiza las siguientes tareas:

## 1. Redimensionar Imágenes

- Las imágenes en la carpeta `input_folder` (en este caso, `/content/gatos`) se redimensionan a un tamaño de **128x128 píxeles**.
- Las imágenes redimensionadas se guardan en la carpeta `output_folder` (en este caso, `/content/cats_resized`).

## 2. Cargar y Configurar el Modelo de Detección

- Se configura el modelo **Grounding DINO** para detectar objetos en las imágenes utilizando un texto descriptivo. El texto utilizado para la detección es **"cat"** (`TEXT_PROMPT`).
- El modelo se carga desde **Hugging Face** utilizando la función `hf_hub_download`.

## 3. Predicción y Anotación

- Se realiza la **predicción** sobre las imágenes redimensionadas para obtener las cajas de los objetos detectados (en este caso, los gatos).
- Las imágenes se **anotan** con las cajas de predicción utilizando el modelo **Grounding DINO**.

## 4. Generación de Etiquetas YOLO

- Las cajas de predicción se convierten al formato **YOLO**, que incluye:
  - La clase del objeto (en este caso, siempre **0** para "cat").
  - El centro de la caja.
  - Las dimensiones normalizadas de la caja.
- Las etiquetas generadas se guardan en la carpeta `output_labels_folder` (en este caso, `/content/cat_yolo_labels`).

## 5. Aplicación de Máscaras

- Utilizando el modelo **Segment Anything (SAM)**, se generan y aplican **máscaras** a las imágenes detectadas.
- Las máscaras se aplican sobre las imágenes anotadas para resaltar los objetos detectados (en este caso, los gatos).

## 6. Guardado de Imágenes Anotadas

- Las imágenes anotadas con las máscaras aplicadas se pueden **visualizar** y **guardar** en formato **RGBA**.

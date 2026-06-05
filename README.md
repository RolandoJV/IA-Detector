# 🛣️ Detección Automática de Grietas en Carreteras con CNN

**Seminario Práctico — Introducción a las Redes Neuronales**  
**Asignatura:** Inteligencia Artificial II  
**Universidad de Oriente — Facultad de Ingeniería en Telecomunicaciones, Informática y Biomédica**  
**Carrera:** Ingeniería Informática | **Curso:** 2025–2026

---

## 👥 Integrantes

- Francis Alejandro Liranza Liranza
- Rolando Javier Villa Rodríguez
- Alejandro Manuel Tamayo Morales

---

## 📌 Descripción

Sistema de visión por computadora que detecta automáticamente la presencia de **grietas en superficies de concreto** mediante una Red Neuronal Convolucional (CNN) entrenada con aprendizaje supervisado.

El modelo clasifica imágenes en dos categorías:
- ✅ **Negative** — superficie sin grietas
- 🔴 **Positive** — superficie con grietas

---

## 🧠 Arquitectura del Modelo

Red Neuronal Convolucional (CNN) personalizada construida con TensorFlow/Keras:

```
Input (224×224×3)
    → Conv2D(32) + ReLU → MaxPooling2D
    → Conv2D(64) + ReLU → MaxPooling2D
    → Conv2D(128) + ReLU → MaxPooling2D
    → Flatten
    → Dense(128) + ReLU + Dropout(0.5)
    → Dense(1) + Sigmoid
```

---

## 📂 Dataset

**Surface Crack Detection Dataset** — disponible públicamente en Kaggle.

```
CrackDataset/
├── Positive/     # ~10,000 imágenes con grietas
└── Negative/     # ~10,000 imágenes sin grietas
```

🔗 [Surface Crack Detection — Kaggle](https://www.kaggle.com/datasets/arunrk7/surface-crack-detection)

---

## ⚙️ Preprocesamiento

| Etapa | Detalle |
|---|---|
| Redimensionamiento | 224 × 224 píxeles |
| Normalización | Valores de píxeles ÷ 255 → rango [0, 1] |
| División | 80% entrenamiento / 20% validación |
| Data Augmentation | Flip horizontal, zoom 10% |

---

## 🛠️ Tecnologías Utilizadas

- Python 3
- TensorFlow / Keras
- NumPy
- Matplotlib
- Google Colab (entorno de ejecución con GPU)

---

## 🚀 Cómo Ejecutar

### 1. Abrir en Google Colab
[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1SnJfP5hskcQbgn6wJH9FSzQ1asCjA4fG?usp=drive_link)

### 2. Dataset en Google Drive
El dataset y el modelo entrenado están disponibles aquí:  
🔗 [Google Drive — Archivos del Proyecto](https://drive.google.com/drive/my-drive)

### 3. Estructura esperada en Drive
```
MyDrive/
└── CrackDataset/
    ├── Positive/
    └── Negative/
```

### 4. Ejecutar las celdas en orden
1. Montar Google Drive
2. Preprocesamiento y generadores de datos
3. Definir arquitectura CNN
4. Entrenar el modelo
5. Guardar modelo (`modelo_grietas.keras`)
6. Visualizar resultados

---

## 📊 Resultados

| Parámetro | Valor |
|---|---|
| Épocas entrenadas | 15 |
| Arquitectura | CNN personalizada |
| Problema | Clasificación binaria |
| Optimizador | Adam |
| Función de pérdida | Binary Crossentropy |
| Métrica | Accuracy |

---

## 📁 Estructura del Repositorio

```
├── modelo_grietas.keras       # Modelo entrenado
├── crack_detection.ipynb      # Notebook principal
├── resultados_modelo.png      # Gráficas de entrenamiento
└── README.md
```

---

## 📖 Referencias

- LeCun, Y. et al. — *Gradient-Based Learning Applied to Document Recognition* (1998)
- Vaswani, A. et al. — *Attention Is All You Need* (2017)
- Hochreiter & Schmidhuber — *Long Short-Term Memory* (1997)
- Dataset: [Surface Crack Detection — Kaggle](https://www.kaggle.com/datasets/arunrk7/surface-crack-detection)

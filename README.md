# Filtro de UD LAS PALMAS

Este proyecto emplea el modelo **MTCNN** para la detección de rostros y la superposición de imágenes para crear un filtro interactivo. Coloca una bufanda en el cuello y marcas de colores debajo de los ojos en los rostros detectados. Si la persona abre la boca, se añade un escudo con un texto sobre la cabeza y un efecto de confeti que cae desde la parte superior de la pantalla. El confeti incrementa su velocidad conforme desciende, creando un efecto dinámico y festivo.

## Tabla de Contenidos

- [Preparación del entorno](#preparación-del-entorno)
- [Proceso de Detección y Efectos](#proceso-de-detección-y-efectos)
- [Ejemplo](#ejemplo)

## Preparación del entorno

### 1. Crear y activar el entorno
Para comenzar, crea un entorno con Python 3.9 y actívalo:
```bash
conda create --name face_effects python=3.9.5
conda activate face_effects
```

### 2. Librerías a instalar:
Este proyecto depende de las siguientes librerías. Puedes instalarlas con pip:

```bash
pip install opencv-python
pip install mtcnn
pip install numpy
```

### 3. Descargar imágenes necesarias
Asegúrate de contar con las imágenes necesarias para el proyecto. Estas deben estar ubicadas en la carpeta `images/` en el mismo directorio donde se encuentra el script. Las imágenes necesarias son:
- `pinturacara1.png`: Marca de color para el ojo izquierdo.
- `pinturacara2.png`: Marca de color para el ojo derecho.
- `bufanda.png`: Imagen de la bufanda.
- `escudo.png`: Imagen del escudo.

### 4. Configuración de la cámara
Este proyecto captura video en tiempo real desde la cámara. Asegúrate de tener una cámara conectada a tu dispositivo antes de ejecutar el código.

## Proceso de Detección y Efectos

### 1. Detección de Rostros
El modelo **MTCNN** detecta los rostros en cada fotograma del video capturado por la cámara. Los puntos clave del rostro (ojos, nariz, boca) son utilizados para determinar la ubicación de las marcas de colores y la bufanda.

### 2. Superposición de Imágenes
- **Marcas de colores debajo de los ojos**: Se superponen imágenes de marcas de colores en los lugares correspondientes debajo de los ojos de las personas detectadas.
- **Escudo en la cabeza**: Si la boca de la persona está abierta, se coloca un escudo sobre la cabeza de la persona.
- **Bufanda en el cuello**: Se coloca una bufanda debajo de la cara, en el cuello.

### 3. Efecto de Confeti
El confeti es generado en posiciones aleatorias en la parte superior de la pantalla. Cada partícula de confeti tiene una velocidad inicial aleatoria, y a medida que desciende por la pantalla, su velocidad incrementa. El confeti se dibuja detrás de la bufanda y el escudo para simular un efecto de celebración.

## Ejemplo
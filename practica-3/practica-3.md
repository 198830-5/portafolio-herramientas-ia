
# AVANCE 1 DE PROYECTO INTEGRADOR

## Fase 1: Ficha de especificación

# ClipQuest
### Buscador de escenas en grabaciones de videojuegos

---

## Datos del equipo

**Grupo:** B1  
**Equipo:** 1

| Nombre completo            | Matrícula |
| -------------------------- | --------- |
| Diego Isaac Rico Hernández |           |
| César Iván Macías Anguiano |           |
| Ernesto Tehuintle Ramírez  |           |
| Sebastián Garcia Vargas    |           |

**Fecha de entrega:** viernes 25 de septiembre de 2026

---

# Ficha de especificación de ClipQuest

## 1. Caso de uso

Jugadores y creadores de contenido necesitan localizar escenas sin revisar toda su partida. El usuario cargará un video de hasta cinco minutos y escribirá una descripción breve en inglés. Recibirá marcas de tiempo y vistas previas de los momentos visualmente más relacionados para facilitar su edición.

## 2. Modelo abierto elegido

| Dato                                 | Respuesta                                                                           |
| ------------------------------------ | ----------------------------------------------------------------------------------- |
| Identificador y liga                 | [openai/clip-vit-base-patch32](https://huggingface.co/openai/clip-vit-base-patch32) |
| Tarea que resuelve (pipeline tag)    | `zero-shot-image-classification`                                                    |
| Número de parámetros                 | Aproximadamente 151.28 millones [2].                                                |
| Licencia                             | MIT, según el repositorio oficial [3].                                              |
| Limitación declarada por sus autores | Dificultades para distinguir categorías muy específicas y contar objetos [1].       |

Elegimos CLIP porque compara texto e imágenes sin entrenamiento adicional. Extraeremos fotogramas y los ordenaremos por similitud con la consulta. El prototipo se limitará a un videojuego y elementos visibles; no interpretará jugadas completas. Usaremos consultas en inglés y validaremos los resultados con grabaciones del juego, conforme a las limitaciones de su Model Card [1].

## 3. Viabilidad de hardware

**Memoria mínima:**

151,280,000 × 2 bytes = 302,560,000 bytes ≈ 0.303 GB en FP16.

Colab asignó una Tesla T4 con 15,360 MiB de VRAM total y 14,913 MiB libres al consultar.

Ejecutaremos en Colab con GPU, con margen para pesos y operaciones adicionales. Procesaremos fotogramas en lotes pequeños para controlar la memoria.

## 4. Un riesgo ético

**Privacidad:** las grabaciones pueden mostrar conversaciones o datos personales. Usaremos videos propios o autorizados, eliminaremos los archivos temporales al terminar y no publicaremos las grabaciones en el repositorio.

## Fuentes

 [Model Card de CLIP en Hugging Face.](https://huggingface.co/openai/clip-vit-base-patch32)

[Keras: parámetros de CLIP ViT Base Patch32.](https://keras.io/keras_hub/api/models/clip/clip_backbone/)

[ Repositorio oficial y licencia de CLIP.](https://keras.io/keras_hub/api/models/clip/clip_backbone/)

---

## 5. Evidencia






![Pasted image](20261104173810.png)

![Pasted image](20261104173702.png)



<div dir="rtl">

# 🤖 AI Melli — Inteligencia Artificial Nacional

**Una herramienta basada en GitHub Actions para generar imágenes y texto con IA — gratis, sin necesidad de clave API, sin servidor, sin restricciones. Solo haz un fork y úsala.**

---

## 🌐 ¿Cómo funciona?

Las GitHub Actions se ejecutan en los servidores de alto rendimiento de GitHub. Este proyecto aprovecha esta capacidad para generar imágenes y textos profesionales con IA sin necesidad de ningún hardware o clave API:

* **Para generación de imágenes:** El flujo de trabajo toma tu prompt, lo pasa a un script de Python, el script descarga la imagen del servicio de generación de imágenes por IA y la commita directamente a tu repositorio — lista para descargar desde GitHub.
* **Para generación de texto:** El flujo de trabajo envía el prompt a un modelo de lenguaje de IA, guarda el texto generado y lo hace push a tu repositorio.
* **Para generación de imágenes inteligente:** Primero envía tu prompt (incluso si está en persa) a un modelo de lenguaje de IA para optimizarlo — traducción al inglés, adición de detalles de iluminación, estilo, composición y calidad — y luego genera la imagen con el prompt mejorado.

No es necesario instalar ningún software en tu dispositivo. No se necesita ninguna clave API. Todo se ejecuta en la nube de GitHub y es completamente gratis.

---

## ✨ Características

| Característica                                    | Descripción                                                                                                                                                                                                  |
| ----------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 🎨 **Generación de imágenes**                        | Crea imágenes con 8 modelos de IA diferentes — desde fotos realistas hasta anime, 3D y estilo oscuro. Dimensiones personalizables, cantidad deseada (hasta 10) y seed ajustable.                                                                   |
| 📝 **Generación de texto**                          | Genera texto con modelos GPT, Mistral, Llama y Claude. Ajusta la temperatura, el mensaje del sistema y la salida en Markdown.                                                                                                        |
| 🧠 **Generación de imágenes inteligente**                 | Escribe el prompt en persa, la IA lo optimizará automáticamente — traducción al inglés, adición de detalles de estilo y calidad — y luego generará la imagen con una calidad muy superior.                                              |
| 🖼️ **Galería HTML automática**                  | Tras generar las imágenes, se crea una página de galería elegante con tema oscuro que incluye el prompt original, el prompt mejorado, el modelo, la fecha y todas las imágenes generadas.                                                      |
| 📦 **Carga al repositorio**                | Los archivos se commitan y hacen push directamente a tu repositorio. Luego puedes descargarlos desde GitHub.                                                                                                           |
| 🚀 **Carga en GitHub Releases**           | Si los archivos son voluminosos, puedes subirlos como un Release para facilitar la descarga.                                                                                                              |
| 🚫 **Eliminación de marca de agua**                      | Función para eliminar automáticamente la marca de agua de las imágenes generadas.                                                                                                                                                         |
| 💰 **Completamente gratis**                      | Sin necesidad de clave API, sin servidor, sin coste. Solo necesitas una cuenta de GitHub.                                                                                                                                |

---

## 🚀 Primeros pasos

### Paso 1 — Haz un Fork

Haz clic en el botón **Fork** en la parte superior de la página para que el repositorio se copie a tu cuenta de GitHub.

### Paso 2 — Habilita los permisos de escritura para Actions

Los flujos de trabajo necesitan permisos para commitar los archivos generados en tu repositorio:

۱. En tu repositorio fork, ve a **Settings** ⚙️.
۲. Desde el menú izquierdo, navega a **Actions → General**.
۳. Bajo la sección **"Workflow permissions"**, selecciona **"Read and write permissions"**.
۴. Haz clic en **Save**.

> **Además**, bajo la sección **"Actions permissions"**, asegúrate de que **"Allow all actions and reusable workflows"** esté seleccionado.

> 💡 **Nota de seguridad:** Dado que este fork te pertenece a ti, otorgar permisos de escritura a tus propios flujos de trabajo es completamente seguro.

### Paso 3 — Ejecuta un flujo de trabajo

۱. Ve a la pestaña **Actions** en tu repositorio.
۲. Selecciona el flujo de trabajo deseado desde la lista de la izquierda (por ejemplo, «Generación de imágenes», «Generación de texto» o «Generación de imágenes inteligente»).
۳. Haz clic en **Run workflow**.
۴. Ingresa los parámetros necesarios (como el prompt, el modelo, las dimensiones de la imagen, etc.).
۵. Haz clic en el botón verde **Run workflow**.

Una vez finalizada la ejecución, los archivos generados estarán visibles en tu repositorio. Luego podrás descargarlos directamente desde GitHub.

---

## 📋 Flujos de trabajo

### 🎨 Generación de imágenes (Image Generation)

Genera imágenes directamente con IA. Escribe el prompt en inglés y selecciona el modelo deseado.

| Entrada              | Descripción                          | Predeterminado       |
| ------------------- | ------------------------------ | ------------- |
| **prompt**          | Prompt para generación de imagen             | —             |
| **negative_prompt** | Qué elementos NO deben aparecer en la imagen      | Vacío          |
| **model**           | Modelo de IA                         | `flux`        |
| **width**           | Ancho de la imagen (píxeles)              | `1024`        |
| **height**          | Alto de la imagen (píxeles)           | `1024`        |
| **num_images**      | Número de imágenes (1 a 10)          | `1`           |
| **seed**            | Seed de la imagen (vacío = aleatorio)       | Vacío          |
| **nologo**          | Eliminar marca de agua                   | `true`        |
| **upload_method**   | Método de carga (repositorio o release)      | `repository`  |

### 📝 Generación de texto (Text Generation)

Genera texto con IA. Ideal para escribir artículos, historias, código, resúmenes y cualquier otro tipo de texto.

| Entrada              | Descripción                          | Predeterminado       |
| ------------------- | ------------------------------ | ------------- |
| **prompt**          | Prompt para generación de texto               | —             |
| **model**           | Modelo de IA                         | `openai`      |
| **temperature**     | Nivel de creatividad (0 a 1.5)         | `0.8`         |
| **system_message**  | Rol e instrucción de la IA                 | Guía general |
| **upload_method**   | Método de carga (repositorio o release)      | `repository`  |

### 🧠 Generación de imágenes inteligente (Smart Image Generation)

¡La mejor opción! Escribe el prompt en **cualquier idioma**. La IA primero lo optimizará y luego generará la imagen.

| Entrada              | Descripción                          | Predeterminado       |
| ------------------- | ------------------------------ | ------------- |
| **prompt**          | Prompt (en persa o inglés)       | —             |
| **negative_prompt** | Qué elementos NO deben aparecer en la imagen      | Vacío          |
| **model**           | Modelo de imagen AI                  | `flux`        |
| **enhance_model**   | Modelo de texto para mejorar el prompt      | `openai`      |
| **width**           | Ancho de la imagen (píxeles)              | `1024`        |
| **height**          | Alto de la imagen (píxeles)           | `1024`        |
| **num_images**      | Número de imágenes (1 a 10)          | `1`           |
| **seed**            | Seed de la imagen (vacío = aleatorio)       | Vacío          |
| **upload_method**   | Método de carga (repositorio o release)      | `repository`  |

> 💡 **Recomendación:** Si tu prompt está en persa, usa definitivamente el modo «Generación de imágenes inteligente». El resultado será mucho mejor porque la IA traduce y optimiza el prompt automáticamente.

---

## 🎨 Modelos de imagen

| Modelo              | Descripción                                  |
| ---------------- | -------------------------------------- |
| `flux`           | Modelo principal — mejor equilibrio entre calidad y velocidad  |
| `turbo`          | Alta velocidad — ideal para generación rápida          |
| `flux-realism`   | Imágenes realistas y naturales           |
| `flux-cablyai`   | Estilo exclusivo CablyAI                        |
| `flux-anime`     | Estilo anime y manga                     |
| `flux-3d`        | Imágenes 3D y renderizados                 |
| `flux-pro`       | Máxima calidad posible                  |
| `any-dark`       | Estilo oscuro y dark                      |

## 📝 Modelos de texto

| Modelo       | Descripción                |
| --------- | -------------------- |
| `openai`  | Modelo GPT              |
| `mistral` | Modelo Mistral          |
| `llama`   | Modelo Llama            |
| `claude`  | Modelo Claude           |

---

</div>

## 📁 Estructura del repositorio

```
ai_melli/
├── .github/
│   └── workflows/                # Flujos de trabajo de GitHub Actions
│       ├── image-generation.yml       # Generación de imágenes
│       ├── text-generation.yml        # Generación de texto
│       └── smart-image-generation.yml # Generación de imágenes inteligente
├── output/                      # Carpeta de salida — archivos generados
└── README.md
```

<div dir="rtl">

---

## ⚙️ Detalles técnicos

### Generación de imágenes

El flujo de trabajo primero crea un archivo JSON con la configuración (prompt, modelo, dimensiones, etc.) usando `jq`. Luego se ejecuta un script de Python que descarga la imagen desde la API de generación de imágenes mediante `urllib.request`. El uso de Python en lugar de `curl` directo permite procesar correctamente caracteres especiales en el prompt (como comillas, barras invertidas y símbolos de dólar). El script tiene hasta 2 reintentos y, si el tamaño del archivo es inferior a 500 bytes, volverá a intentarlo.

### Generación de texto

Similar a la generación de imágenes, la configuración se convierte a JSON con `jq` y el script de Python la envía a la API de texto. La respuesta JSON se analiza y el texto extraído se guarda en un archivo Markdown.

### Generación de imágenes inteligente

Este flujo de trabajo tiene dos etapas. Primera etapa: el prompt del usuario (en cualquier idioma) se envía a un modelo de lenguaje de IA para optimizarlo — traducción al inglés, adición de detalles de iluminación, composición, estilo y calidad. Segunda etapa: el prompt mejorado se utiliza para generar la imagen. El resultado final tiene una calidad muy superior en comparación con el prompt original.

### Galería HTML

Tras generar las imágenes, se crea una página HTML con tema oscuro que incluye toda la información (prompt original, prompt mejorado, modelo, fecha, conteo de éxitos/fallos) y las miniaturas de todas las imágenes. Las imágenes se muestran en una cuadrícula responsiva.

---

## 🔄 Actualización a la nueva versión

Para sincronizar tu fork con los últimos cambios del repositorio original, haz clic en el botón **Sync fork** en la página principal de tu repositorio en GitHub.

---

## 🤝 Contribuir

¿Tienes una idea para una nueva funcionalidad? Abre un [Issue](https://github.com/amirabolfazle/ai_melli/issues) y comparte tu sugerencia.

---

## ⚠️ Descargo de responsabilidad

Este proyecto está diseñado para uso personal y educativo. Los usuarios son responsables de cumplir con los términos de servicio de los servicios que utiliza esta herramienta, así como de respetar las leyes de su país.

---

## ⭐ Apoyo

Si esta herramienta te resultó útil, apóyame dándole una estrella ⭐ — ¡ayuda a que otros encuentren el proyecto!

</div>

<a href="https://www.star-history.com/?repos=amirabolfazle%2Fai_melli&type=date&legend=top-left">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/chart?repos=amirabolfazle/ai_melli&type=date&theme=dark&legend=top-left" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/chart?repos=amirabolfazle/ai_melli&type=date&legend=top-left" />
   <img alt="Star History Chart" src="https://api.star-history.com/chart?repos=amirabolfazle/ai_melli&type=date&legend=top-left" />
 </picture>
</a>

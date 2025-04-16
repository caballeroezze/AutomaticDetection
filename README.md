# Análisis automático de observaciones clínicas con IA (Gemini API)

Este proyecto permite detectar menciones a **medicamentos o monodrogas** en observaciones clínicas escritas en **texto libre**, aunque estén mal escritas, abreviadas o con lenguaje informal.

Usa la **API gratuita de Gemini (Google Generative AI)** junto con Python y Excel para automatizar un proceso que normalmente sería manual y lento.

---

## Objetivo

A partir de un archivo Excel con observaciones clínicas, identificar aquellas que mencionan medicamentos y extraer esa información junto con el ID del parte de enfermería y la internación.

---

## Estructura esperada del archivo de entrada (`observaciones.xlsx`)

| ParteEnfermeriaID | InternacionID | Observaciones                              |
|-------------------|----------------|--------------------------------------------|
| 1234              | 4567           | Se aplicó insl rápida antes del desayuno.  |

---

## ⚙️ Tecnologías utilizadas

- Python 
- Google Generative AI API (Gemini 2.0 Flash)
- Pandas
- tqdm (barra de progreso)
- openpyxl

---

## Cómo usar

### 1. Clonar este repositorio

```bash
git clone https://github.com/tuusuario/observaciones-clinicas-gemini.git
cd observaciones-clinicas-gemini
```

### 2. Instalar dependencias

```bash
pip install -r requirements.txt
```

> Asegurate de tener Python 3.9+ y Jupyter Notebook (opcional)

### 3. Configurar tu clave API

Obtené tu API key gratuita desde:  
🔗 https://aistudio.google.com/app/apikey

Pegala en el archivo `main.py` o `notebook.ipynb`:

```python
API_KEY = "TU_CLAVE_API"
```

### 4. Colocar el archivo de entrada

Asegurate de que tu Excel se llame `observaciones.xlsx` y tenga las columnas mencionadas.  

### 5. Ejecutar el script o notebook

```bash
python main.py
```

O corré la notebook paso a paso.

---

##  Salida

Se genera un archivo llamado `drogas_detectadas.xlsx` con:

| ParteEnfermeriaID | InternacionID | Observacion                               | MedicamentosDetectados |
|-------------------|----------------|-------------------------------------------|-------------------------|
| 1234              | 4567           | Se aplicó insl rápida                     | Insulina                |

---

## Características

-  Reconocimiento semántico: detecta drogas con errores de escritura (ej: *"insl" → Insulina*)
-  Procesamiento por bloques (agrupado)
-  Control de uso: respeta los límites de la API gratuita
-  Barra de progreso con `tqdm`
-  100% offline excepto llamadas a la API

---

## Notas

- El modelo usado es `gemini-2.0-flash`, compatible con la API gratuita
- El script maneja 2.600+ observaciones en aproximadamente 1 hora
- No se requiere cuenta paga

---

##  Agradecimientos

Este proyecto fue creado como solución real para automatizar tareas de análisis clínico en contexto hospitalario.  
Inspirado por la necesidad de resolver problemas sin presupuesto, usando IA generativa gratuita.

---

##  Contacto

Si querés usar este proyecto, adaptarlo o colaborar:

📧 caballeroezze@gmail.com  
💼 [[LinkedIn](https://linkedin.com/in/esteban-ezequiel-caballero)
🐍 [@tuGitHub](https://github.com/caballeroezze)

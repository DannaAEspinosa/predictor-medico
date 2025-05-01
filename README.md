# 🩺 Predictor Médico – Proyecto MLOps

Este proyecto implementa un pipeline básico de MLOps que simula un sistema de predicción médica. A través de una interfaz web, el usuario puede ingresar tres valores clínicos (numéricos) y obtener un diagnóstico simulado, usando una lógica simple contenida en un archivo Python. La solución está empaquetada y desplegada usando Docker.

---

## 📌 Objetivo

Simular un modelo de predicción de enfermedades comunes y huérfanas a partir de tres síntomas, como parte de una práctica de desarrollo de pipelines MLOps end-to-end.

---

## 🚀 Instrucciones

### 1. Clona este repositorio

```bash
git clone https://github.com/DannaAEspinosa/predictor-medico.git
cd predictor-medico
```

### 2. Construye la imagen Docker

Asegúrate de tener Docker instalado y ejecutándose:

```bash
docker build -t predictor-medico .
```

### 3. Ejecuta el contenedor

```bash
docker run -p 5000:5000 predictor-medico
```

La aplicación estará disponible en:

```
http://localhost:5000
```

---

## 🧪 Uso de la aplicación

1. Abre la página web.
2. Ingresa **tres valores numéricos** que representan síntomas.
3. Haz clic en **"Predecir"**.
4. Obtendrás un resultado con el estado estimado:

- `NO ENFERMO`
- `ENFERMEDAD LEVE`
- `ENFERMEDAD AGUDA`
- `ENFERMEDAD CRÓNICA`

---

## 🧠 Lógica de predicción (modelo simulado)

```python
def predecir_estado(valores):
    if not isinstance(valores, list) or len(valores) != 3 or not all(isinstance(v, (int, float)) for v in valores):
        return "ENTRADA INVÁLIDA"

    suma = sum(valores)
    if suma <= 100:
        return "NO ENFERMO"
    elif suma <= 200:
        return "ENFERMEDAD LEVE"
    elif suma <= 300:
        return "ENFERMEDAD AGUDA"
    else:
        return "ENFERMEDAD CRÓNICA"
```

---

## 📁 Estructura del proyecto

```
predictor-medico/
├── app.py                  # App principal con Flask
├── predictor.py            # Lógica del modelo
├── requirements.txt        # Dependencias del proyecto
├── Dockerfile              # Imagen Docker
├── templates/
│   └── index.html          # Interfaz web
└── static/
    └── style.css           # Estilos CSS
```

---

## ✅ Requisitos

- Docker
- Navegador web

---

## Hecho por:

Danna Espinosa
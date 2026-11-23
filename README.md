# GuardIA · Inteligencia artificial

| Módulo | Función | Puerto de revisión |
| --- | --- | --- |
| `guardia_ai/` | Detección de personas en video con YOLOv8 y OpenCV. | 8000 |
| `ml_service/` | Clasificación de riesgo con los modelos entrenados incluidos. | 8001 |

## Detección de personas

Consulta [la guía del servicio](guardia_ai/README.md) para usar Python 3.11 con cámara o archivo de video. Para ejecutar el servicio desde Docker, usa la raíz de esta rama:

```bash
docker build -t guardia-deteccion ./guardia_ai
docker run --rm -p 127.0.0.1:8000:8000 guardia-deteccion
```

Comprueba `GET http://localhost:8000/health`. El peso `yolov8n.pt` forma parte del contexto de compilación.

## Clasificación de riesgo

Crea un entorno virtual con Python 3.11 y actívalo. Instala las dependencias y ejecuta FastAPI desde `ml_service/`:

```bash
cd ml_service
python -m pip install -r requirements.txt
python -m uvicorn api:app --host 127.0.0.1 --port 8001
```

Abre `http://127.0.0.1:8001/docs` para consultar y probar los endpoints. El puerto 8001 permite ejecutar los dos servicios a la vez. Los modelos se entrenaron con scikit-learn 1.6.1. El script `train_models.py` genera los modelos a partir del dataset sintético descrito en [README_ML.md](ml_service/README_ML.md).

# Observabilidad e Infraestructura de Datos: Monitoreo Correlacional en Tiempo Real

## 📌 Descripción del Proyecto
Este repositorio documenta el diseño e implementación de un sistema de **Observabilidad y Monitoreo Correlacional** para infraestructura de servicios y procesos en tiempo real. Utilizando **Grafana** como capa de visualización y **Prometheus** como motor de métricas de telemetría, el cuadro de mando permite evaluar de forma continua el rendimiento de aplicaciones, detectando picos de demanda, anomalías en consumo de memoria y variaciones en la carga de procesamiento.

El objetivo principal de esta arquitectura es proporcionar a los equipos de TI y datos una herramienta visual estandarizada para garantizar la alta disponibilidad y la estabilidad operativa de los servicios.

---

## 🛠️ Stack Tecnológico
* **Visualización & Dashboards:** Grafana
* **Recolector de Métricas & Telemetría:** Prometheus (PromQL)
* **Métricas Evaluadas:** HTTP Requests Rate, System Memory Usage (MiB), CPU Process Utilization

---

## 📊 Arquitectura del Dashboard y Análisis de Métricas

El panel de control está estructurado estratégicamente para correlacionar tres dimensiones de infraestructura clave sobre la misma ventana de tiempo:

### 1. Flujo de Tráfico Web (Peticiones HTTP / seg)
* **Métrica:** `req/s` (Frecuencia de peticiones web).
* **Propósito:** Monitorear el volumen de entradas e interacciones en la aplicación. Permite identificar incrementos repentinos de tráfico a horas específicas (por ejemplo, los picos observados a partir de las `08:00`).

### 2. Uso de Memoria RAM en Tiempo Real
* **Métrica:** `MiB` (Mebibytes consumidos).
* **Propósito:** Supervisar la huella de memoria del proceso. Facilita la detección de picos de consumo repetitivos o inusuales (como las elevaciones registradas cerca de las `04:00`, `06:00` y `08:00`) para evaluar posibles necesidades de escalamiento o liberación de recursos.

### 3. Consumo de CPU de la Aplicación
* **Métrica:** Escala normalizada de procesamiento (`Prometheus Process`).
* **Propósito:** Analizar la variabilidad en el procesamiento en función de la carga operativa general del sistema, registrando las oscilaciones de uso continuo a lo largo de la jornada.

---

## 💡 Criterios de Diseño y Buenas Prácticas Aplicadas

1. **Estandarización de Unidades:** Conversión y formateo explícito de métricas crudas a unidades estándar entendibles por la industria (`req/s`, `MiB`).
2. **Identificación Cromática:** Asignación de colores diferenciados por tipo de recurso (Azul: Tráfico/Red, Amarillo: Memoria/RAM, Verde: Procesamiento/CPU) para reducir el tiempo de interpretación ejecutiva.
3. **Mantenimiento y Modulabilidad:** Organización limpia mediante filas (*Rows*) dentro de un dashboard centralizado de infraestructura.

---

## 📁 Estructura del Repositorio
```text
grafana-observability-portfolio/
│
├── README.md                      <-- Documentación técnica del proyecto
└── img/                           <-- Capturas de pantalla de los paneles
    ├── flujo_trafico_web.png
    ├── uso_memoria_ram.png
    └── consumo_cpu.png
```

---

> **Nota de Confidencialidad y Seguridad:** La información, imágenes y configuraciones mostradas en este repositorio corresponden a plantillas anonimizadas y métricas genéricas de telemetría con fines exclusivamente demostrativos de portafolio técnico, cumpliendo con las políticas de seguridad y privacidad de la información.

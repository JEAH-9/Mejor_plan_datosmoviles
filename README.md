# 📊 Análisis de Ingresos por Planes de Prepago – Megaline

## 📌 Descripción del Proyecto

Este proyecto analiza el comportamiento de 500 clientes del operador de telecomunicaciones **Megaline** durante el año 2018, con el objetivo de determinar cuál de sus dos planes de prepago — **Surf** o **Ultimate** — genera mayores ingresos promedio.

El departamento comercial busca esta información para optimizar la asignación del presupuesto publicitario y enfocar las campañas en el plan más rentable.

El análisis incluye procesamiento de datos, cálculo de ingresos mensuales por usuario, análisis exploratorio y pruebas estadísticas de hipótesis.
---
## 🎯 Objetivos del Análisis

- Calcular el ingreso mensual por usuario considerando excedentes.
- Analizar el comportamiento de consumo (llamadas, SMS y datos) por plan.
- Comparar los ingresos promedio entre Surf y Ultimate.
- Evaluar si existen diferencias significativas en ingresos por región (NY-NJ vs otras).
- Validar los resultados mediante pruebas estadísticas.
---
## 📂 Datos Utilizados

El análisis se realizó utilizando cinco tablas:

### 1️⃣ users
Información demográfica y del plan del usuario:
- `user_id`
- `age`
- `city`
- `plan`
- `reg_date`
- `churn_date`

### 2️⃣ calls
- `call_date`
- `duration` (minutos)
- `user_id`

### 3️⃣ messages
- `message_date`
- `user_id`

### 4️⃣ internet
- `session_date`
- `mb_used`
- `user_id`

### 5️⃣ plans
- `usd_monthly_fee`
- `minutes_included`
- `messages_included`
- `mb_per_month_included`
- `usd_per_minute`
- `usd_per_message`
- `usd_per_gb`

---

## ⚙️ Reglas de Facturación Importantes

- Las llamadas se redondean individualmente al minuto superior.
- Los datos móviles se redondean al total mensual en GB (1 GB = 1024 MB).
- Los excedentes se cobran según las tarifas del plan correspondiente.

---

## 🛠 Metodología

### 1️⃣ Preparación de Datos

- Conversión de tipos de datos (fechas y numéricos).
- Revisión y limpieza de valores inconsistentes.
- Cálculo de métricas mensuales por usuario:
  - Total de minutos
  - Total de SMS
  - Total de datos (GB)
- Cálculo de ingresos mensuales:
  - Cálculo de excedentes
  - Aplicación de tarifas adicionales
  - Suma de cuota mensual

---

### 2️⃣ Análisis Exploratorio (EDA)

Se analizaron por plan:

- Promedio mensual de minutos
- Promedio mensual de SMS
- Promedio mensual de datos
- Distribuciones mediante histogramas
- Media, varianza y desviación estándar

---

### 3️⃣ Pruebas Estadísticas

Se evaluaron dos hipótesis principales:

#### Hipótesis 1:
- **H0:** El ingreso promedio de los planes Surf y Ultimate es igual.
- **H1:** El ingreso promedio difiere entre planes.

#### Hipótesis 2:
- **H0:** El ingreso promedio en el área NY-NJ es igual al de otras regiones.
- **H1:** El ingreso promedio es diferente.

Se utilizó una prueba t para muestras independientes con un nivel de significancia α = 0.05.

---

## 📊 Resultados Clave

- Se identificaron diferencias en patrones de consumo entre ambos planes.
- Los usuarios de Surf presentan mayor probabilidad de exceder límites.
- El plan que genera mayor ingreso promedio fue determinado mediante prueba estadística.
- Se evaluó si la región influye significativamente en los ingresos.

(Ver notebook para resultados detallados y valores p.)

---

## 📈 Tecnologías Utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- SciPy
- Jupyter Notebook

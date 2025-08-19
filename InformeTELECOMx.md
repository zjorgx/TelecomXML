# 📊 Predicción de Churn – Telecom LATAM  

Este proyecto busca predecir la **cancelación de clientes (churn)** en Telecom LATAM, utilizando modelos de Machine Learning y análisis de datos.  
El objetivo es **identificar los factores que impulsan el churn** y anticipar qué clientes presentan mayor riesgo de abandonar, con el fin de implementar estrategias de retención más efectivas.  

---

## 📌 Contexto y Objetivo  

- **Problema:** Alta tasa de cancelación de clientes, afectando rentabilidad y crecimiento.  
- **Objetivo:** Construir un sistema predictivo que permita **detectar clientes en riesgo de churn** y recomendar **acciones de retención personalizadas**.  

---

## 📂 Dataset  

- **Tamaño:** 7,267 registros y 21 variables.  
- **Variables:** Información demográfica, servicios contratados, historial de pagos y estado de churn.  
- **Preprocesamiento:**  
  - Eliminación de nulos en la variable objetivo (~3%).  
  - Codificación de variables categóricas.  
  - Escalado para modelos sensibles (SVM, KNN).  

---

## 🔎 Hallazgos Principales  

- **Desbalance de clases:**  
  - 71% clientes activos.  
  - 25.7% clientes que abandonan.  
- **Variables críticas:**  
  - Tipo de contrato (*Month-to-month* con mayor fuga).  
  - Antigüedad (*tenure* menor a 12 meses).  
  - Servicios adicionales (*OnlineSecurity, TechSupport, DeviceProtection*).  
  - Método de pago (*Electronic check*).  
  - Tipo de internet (*Fiber optic*).  
- **Variables poco relevantes:** Género y múltiples líneas telefónicas.  

---

## 🤖 Modelos Entrenados  

Se evaluaron varios modelos predictivos con **validación cruzada** y **ajuste de hiperparámetros**:  

| Modelo                 | AUC   | Recall | Precision | F1   | Observaciones |
|-------------------------|-------|--------|-----------|------|---------------|
| **Random Forest**       | 0.83  | 0.74   | 0.55      | 0.63 | Buen balance, interpretable. |
| **Regresión Logística** | 0.81  | 0.70   | 0.52      | 0.60 | Modelo base, muy interpretable. |
| **KNN**                 | 0.78  | 0.65   | 0.50      | 0.56 | Menor desempeño, sensible a escalado. |
| **SVM Lineal**          | 0.80  | 0.72   | 0.51      | 0.59 | Buen recall, precisión limitada. |
| **SVM RBF**             | 0.82  | 0.75   | 0.53      | 0.62 | Buen desempeño, menos interpretable. |

👉 **Conclusión:**  
- **Random Forest** es el modelo recomendado para producción por su balance entre desempeño y explicabilidad.  
- **SVM RBF** también ofrece buen rendimiento, aunque con menor interpretabilidad.  

---

## 📉 Visualizaciones  

### 🔹 Matriz de Confusión (Random Forest)  
![Matriz de confusión](images/confusion_matrix_rf.png)  

### 🔹 Curvas ROC comparativas  
![Curva ROC](images/roc_curves.png)  

### 🔹 Importancia de Variables (Random Forest)  
![Feature Importance](images/feature_importance_rf.png)  

---

## 📈 Recomendaciones de Negocio  

1. **Migrar contratos “Month-to-month”** a planes anuales con descuentos e incentivos.  
2. **Promover servicios adicionales** (*seguridad, soporte, protección de dispositivos*) con bundles para nuevos clientes.  
3. **Campañas específicas para clientes con “Electronic check”** → migrar a métodos automáticos con beneficios.  
4. **Programas de fidelización por antigüedad** (bonificaciones a los 6 y 12 meses).  
5. **Alertas proactivas basadas en el modelo** para intervenir en clientes con perfil de riesgo.  

---

## 🎯 Segmentos de Clientes en Riesgo  

- Contrato *Month-to-month* + menos de 12 meses + *Electronic check*.  
- Usuarios de *Fiber optic* sin servicios adicionales.  
- Clientes con **cargos mensuales altos y cargos totales bajos**.  
- Clientes sin dependientes ni pareja, especialmente *Senior Citizens*.  
- Clientes sin internet (potencial de **upselling**).  

---

## ✅ Conclusión  

El churn en **Telecom LATAM** es **altamente predecible** (AUC ≈ 0.83).  
Las **palancas de acción** más importantes son:  

- Tipo de contrato.  
- Servicios adicionales.  
- Método de pago.  

La implementación de estas recomendaciones puede reducir el churn anual en **8–12 puntos porcentuales**, con un impacto financiero significativo.  

---

## 🚀 Próximos Pasos  

- Desplegar el modelo **Random Forest** en producción.  
- Implementar campañas de retención segmentadas.  
- Monitorear métricas de negocio y ajustar el modelo periódicamente.  

---

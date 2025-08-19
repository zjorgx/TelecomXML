# 📊 Predicción de Churn – Telecom X  

## 📑 Descripción del Proyecto  
Este proyecto tiene como objetivo **predecir la cancelación de clientes (churn) en la empresa Telecom X**, utilizando técnicas de **Machine Learning** aplicadas a un dataset de clientes.  

El churn es uno de los principales desafíos en la industria de telecomunicaciones, ya que afecta directamente la rentabilidad. Con modelos predictivos robustos, se busca identificar clientes en riesgo de abandono y diseñar estrategias de retención efectivas.  

---

## 🎯 Objetivos  
- Analizar los factores que influyen en el churn de clientes.  
- Construir y comparar modelos de clasificación para predecir churn.  
- Identificar segmentos de clientes con mayor riesgo.  
- Generar recomendaciones de negocio para reducir la fuga de clientes.  

---
## 📊 Dataset  

- **Registros:** 7,267 clientes  
- **Variables:** 21 (demográficas, servicios, métodos de pago, historial de facturación y churn)  
- **Variable objetivo:** `Churn` (1 = cliente se da de baja, 0 = cliente permanece)  

**Hallazgos clave:**  
- 71% clientes permanecen, 25.7% churn, 3% registros eliminados por vacíos.  
- **Factores críticos:** contrato mensual, tenure < 12 meses, uso de "Electronic check", falta de servicios de seguridad/soporte, internet "Fiber optic".  
- **Factores poco relevantes:** género y múltiples líneas.  

---

## 🤖 Modelos Entrenados  

| Modelo                  | AUC  | Recall | Precision | F1   | Observaciones |
|-------------------------|------|--------|-----------|------|---------------|
| Random Forest           | 0.84 | 0.76   | 0.56      | 0.64 | Buen balance entre desempeño e interpretabilidad |
| XGBoost                 | 0.85 | 0.82   | 0.54      | 0.64 | Mejor desempeño global |
| Red Neuronal (MLP)      | 0.84 | 0.83   | 0.49      | 0.60 | Útil, pero menos interpretable |

👉 El **XGBoost** fue el modelo con mejor desempeño global, aunque Random Forest resulta más interpretable para el negocio.  

---

## 🧩 Metodología  

1. **Preparación de datos**  
   - Limpieza de nulos, codificación de variables categóricas y escalado.  
   - Balanceo de clases con técnicas de sobremuestreo.  

2. **Selección de variables**  
   - Análisis de correlación.  
   - Importancia de variables con Random Forest y XGBoost.  

3. **Modelado**  
   - Regresión Logística  
   - KNN  
   - SVM (lineal y RBF)  
   - Random Forest  
   - XGBoost  
   - Red Neuronal (MLP)  

4. **Evaluación**  
   - Métricas: Accuracy, Recall, Precision, F1, AUC-ROC.  
   - Validación cruzada y ajuste de hiperparámetros (GridSearch).  

---

## 💡 Recomendaciones de Negocio  

- Migrar clientes de **contratos mensuales** a planes anuales con incentivos.  
- Promover **servicios adicionales** (seguridad, soporte, protección de dispositivos).  
- Incentivar el cambio de **Electronic check** a pagos automáticos.  
- Implementar un **programa de fidelización por antigüedad** (6 y 12 meses).  
- Activar **alertas proactivas** en clientes de alto riesgo (tenure bajo, contrato M2M, método de pago riesgoso).  

---

## 📌 Conclusión  

El churn en Telecom X es **altamente predecible** con AUC de hasta **0.85 (XGBoost)**.  
Las variables más influyentes (tipo de contrato, servicios extra y método de pago) representan palancas de acción directa para el negocio.  

La implementación de estas estrategias puede reducir el churn anual en **8-12 puntos porcentuales**, con un impacto financiero significativo.  

---

## 🚀 Próximos Pasos  

- Desplegar el modelo XGBoost en producción.  
- Integrar alertas automáticas en el CRM.  
- Ejecutar campañas de retención segmentadas en el próximo trimestre.  

---

## 🛠️ Tecnologías Utilizadas  

- Python (pandas, numpy, scikit-learn, imbalanced-learn)  
- XGBoost  
- Matplotlib, Seaborn (visualización)  


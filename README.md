# Reducción de Falsos Positivos en Clasificación Binaria de Fraude

## Descripción del proyecto

Este repositorio contiene el desarrollo de la **Parte A** del Trabajo Teórico-Práctico 1 del Convenio PLUS TI – Universidad del Valle.

El objetivo específico de esta parte del proyecto es diseñar, implementar y evaluar estrategias para la **reducción de falsos positivos** en un modelo de clasificación binaria de fraude.

La variable objetivo del problema es:

is_fraud

con dos posibles clases:

True  = transacción fraudulenta
False = transacción legítima

El problema principal abordado es que, en escenarios de detección de fraude, un modelo puede detectar una cantidad considerable de fraudes pero generar demasiadas alertas falsas. Esto provoca fatiga operativa, pérdida de confianza en el sistema y mayor carga de revisión manual.

Por esta razón, el enfoque del proyecto no se centra únicamente en maximizar métricas generales como AUC-ROC o accuracy, sino en reducir la proporción de falsos positivos dentro de las alertas generadas.

Objetivo de la Parte A

El objetivo específico trabajado en este repositorio es:

Reducir la cantidad de falsos positivos generados por un modelo de clasificación binaria de fraude, manteniendo una detección de fraude igual o superior al 90%.

La métrica principal utilizada para evaluar este objetivo fue:

**FP Ratio = FP / (TP + FP)**

donde:

FP = falsos positivos
TP = verdaderos positivos

Esta métrica representa la proporción de alertas generadas por el modelo que realmente corresponden a falsos positivos.

## Dataset

El dataset utilizado corresponde a transacciones sintéticas de tarjetas de crédito de un banco de Bolivia con clientela VIP.

## Características generales del dataset:

- Transacciones legítimas y fraudulentas.
- Periodo cubierto: enero 2025 a junio 2025.
- Aproximadamente 100,000 transacciones.
- 5,000 clientes.
- 67 variables originales.
- Formato basado en ISO 8583.
- Variable objetivo: is_fraud.

## Interpretación de resultados

El modelo seleccionado reduce de forma significativa la cantidad de falsos positivos frente al modelo base. Aunque el FP Ratio absoluto sigue siendo elevado, la mejora obtenida representa una reducción importante en la carga operativa de revisión de alertas.

Un punto importante observado es que el modelo base puede obtener un AUC ligeramente superior, pero esto no implica que sea mejor para el objetivo asignado. En este proyecto, el objetivo no era maximizar AUC, sino reducir falsos positivos manteniendo una detección mínima del 90%.

Por esta razón, el modelo cost_sensitive fue considerado superior desde una perspectiva operacional.

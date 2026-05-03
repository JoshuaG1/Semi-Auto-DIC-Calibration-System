# Sistema Mecatrónico para Automatización de Calibración DIC

Este proyecto consiste en el desarrollo de un sistema mecatrónico diseñado para automatizar la rutina de calibración de cámaras en equipos de **Correlación Digital de Imágenes (DIC)**. El objetivo principal es reducir el error humano y aumentar la repetibilidad del proceso, logrando precisiones por debajo del límite de **0.04 píxeles** exigido por los estándares de medición.

## 🚀 Características Principales

El dispositivo cuenta con **3 grados de libertad (DoF)** para orientar los paneles de calibración de forma precisa:
* **Inclinación (Eje Y):** Logra hasta 40° respecto a la vertical mediante un servomotor.
* **Rotación (Eje X):** Giro de hasta 360° sobre el propio eje del panel.
* **Posicionamiento Lateral (Eje Z):** Desplazamiento para orientar el panel hacia la cámara izquierda o derecha.

## 🛠️ Hardware y Componentes

La arquitectura electrónica está basada en una gestión de potencia eficiente para evitar ruidos electromagnéticos en la lógica de control.

### Componentes Electrónicos
* **Microcontrolador:** Arduino Mega 2560.
* **Actuadores:** * Motor a pasos Nema 17 (Eje Z) con controlador A4988.
    * Motor a pasos 28BYJ48 (Eje X) con controlador ULN2003.
    * Servomotor MG996R de alto torque (Eje Y).
* **Interfaz:** Pantalla LCD I2C 16x2 y botones físicos (NEXT, BACK, RESET).
* **Alimentación:** Fuente de 12Vdc con reguladores conmutados Step-Down (LM2596S) para derivar líneas de 9V y 5V.

### Estructura Mecánica
* **Diseño:** Modelado en Fusion 360 con un enfoque modular.
* **Fabricación:** Piezas estructurales impresas en 3D (PLA) y carcasa principal de acrílico de 20x10x7 cm para protección e inspección visual.

## 💻 Control y Software

El sistema opera mediante una **máquina de estados secuencial** desarrollada en Arduino IDE. La rutina está programada para ejecutar automáticamente los pasos necesarios del software DIC a partir del paso 4 (tras el posicionamiento inicial).

### Interfaz de Usuario
1.  **NEXT:** Avanza al siguiente paso de la rutina.
2.  **BACK:** Regresa al paso anterior para correcciones.
3.  **RESET:** Devuelve el sistema a la posición de origen.

## 📊 Resultados y Validación

El sistema fue validado en la Unidad de Materiales del **Centro de Investigación Científica de Yucatán (CICY)**, obteniendo los siguientes resultados:
* **Precisión:** Se alcanzó consistentemente una desviación de calibración **menor a 0.04 píxeles**.
* **Eficiencia:** Reducción significativa del tiempo de preparación y eliminación de la dependencia de la pericia manual del operador.

---
**Desarrollado por:** Br. Joshua Emmanuel Góngora Álvarez  
**Asesor:** Dr. Francis Avilés Cetina  
**Institución:** Centro de Investigación Científica de Yucatán, A.C. (CICY)

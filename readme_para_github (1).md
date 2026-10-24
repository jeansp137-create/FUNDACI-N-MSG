# Análisis Orientado a Objetos — Fundación MSG (MSGF)

Este repositorio contiene los modelos de análisis orientado a objetos desarrollados en el marco del Proceso Unificado de Ingeniería de Software para el caso de estudio de la Fundación MSG (MSG Foundation). El objetivo principal es documentar el proceso de diseño iterativo e incremental mediante la elaboración de diagramas UML elaborados en draw.io.

## Contexto del Proyecto

La Fundación MSG es una organización dedicada a la gestión de fondos para facilitar el acceso a vivienda mediante créditos hipotecarios e inversiones financieras. A medida que el sistema evoluciona, se incorporan nuevas líneas de impacto social, requiriendo adaptar los modelos arquitectónicos y conceptuales del software.

El modelado se divide en dos grandes momentos de desarrollo:

1. **Gestión Hipotecaria e Inversiones (Iteración 1):** Administración de hipotecas para familias cualificadas, estimación semanal de fondos disponibles, gestión de activos e informes financieros.

2. **Incorporación de Becas-Crédito (Iteración 2):** Gestión de aportes anuales destinados a becas de estudio otorgadas semestralmente. Incluye el seguimiento académico de los estudiantes para determinar la condonación total o parcial de la deuda o el cobro de la matrícula según su rendimiento.

## Objetivos de Aprendizaje

* Aplicar las disciplinas de Elicitación de Requerimientos y Análisis Orientado a Objetos (AOO) según el Proceso Unificado.

* Comprender el impacto de los cambios de alcance en los artefactos de software a través del modelado iterativo e incremental.

* Identificar la estructura y responsabilidad de las Clases Entidad, Límite (Boundary) y Control (Control) aplicando el patrón ECB (Análisis de Robustez).

* Analizar el comportamiento dinámico del sistema mediante Diagramas de Máquinas de Estado.

## Estructura del Repositorio

```text
MSGF-Analysis/
├── .gitignore
├── README.md
├── ITERACIÓN1/
│   ├── DIAGRAMA DE CASOS DE USO MSGF.drawio
│   ├── DIAGRAMA DE CLASES LÍMITE Y CONTROL MSGF.drawio
│   ├── DIAGRAMA DE CLASES MSGF.drawio
│   └── DIAGRAMA DE MÁQUINAS DE ESTADO MSGF (1).drawio
└── ITERACIÓN2/ACTUALIZACIÓN Iteration2-becaCrédito/
    ├── MSGF - DIAGRAMA DE CASOS DE USO.drawio
    ├── MSGF - DIAGRAMA DE CLASES (1).drawio
    ├── MSGF - DIAGRAMA DE CLASES LÍMITE Y CONTROL.drawio
    ├── MSGF - DIAGRAMA DE MÁQUINA DE ESTADOS.drawio
    ├── LÉAME.md
    └── becaCrédito description.md
```

## Artefactos Desarrollados

### Iteración 1: Requerimientos Base

En esta fase inicial se modela el núcleo de operación de la fundación enfocado en hipotecas e inversiones:

| Artefacto | Descripción | Archivo |
| ----- | ----- | ----- |
| **Casos de Uso** | Delimitación del alcance general del sistema y los actores involucrados. | `ITERACIÓN1/DIAGRAMA DE CASOS DE USO MSGF.drawio` |
| **Clases Entidad** | Identificación del modelo del dominio (hipotecas, inversiones, egresos, etc.). | `ITERACIÓN1/DIAGRAMA DE CLASES MSGF.drawio` |
| **Máquina de Estados** | Representación del comportamiento dinámico y ciclo de vida del sistema. | `ITERACIÓN1/DIAGRAMA DE MÁQUINAS DE ESTADO MSGF (1).drawio` |
| **Clases Límite y Control** | Definición de interfaces de usuario y componentes controladores de lógica. | `ITERACIÓN1/DIAGRAMA DE CLASES LÍMITE Y CONTROL MSGF.drawio` |

### Iteración 2: Extensión Becas-Crédito

Se actualizan los modelos de la iteración anterior para incorporar el flujo de becas condonables:

* **Casos de Uso:** `ITERACIÓN2/ACTUALIZACIÓN Iteration2-becaCrédito/MSGF - DIAGRAMA DE CASOS DE USO.drawio`  
  Inclusión de actores e interacciones para el registro de aportes y gestión de becas.

* **Clases Entidad:** `ITERACIÓN2/ACTUALIZACIÓN Iteration2-becaCrédito/MSGF - DIAGRAMA DE CLASES (1).drawio`  
  Incorporación del modelo de datos para estudiantes, matrículas y estado de becas.

* **Clases Límite y Control:** `ITERACIÓN2/ACTUALIZACIÓN Iteration2-becaCrédito/MSGF - DIAGRAMA DE CLASES LÍMITE Y CONTROL.drawio`  
  Se mantiene un nivel de granularidad arquitectónica alto (*coarse-grained*). En lugar de multiplicar la cantidad de clases límite y de control para cada subproceso de becas, se generaliza la responsabilidad en la clase de control `Update of MSG App data` para concentrar la lógica de cálculo y actualización global.

* **Máquina de Estados:** `ITERACIÓN2/ACTUALIZACIÓN Iteration2-becaCrédito/MSGF - DIAGRAMA DE MÁQUINA DE ESTADOS.drawio`  
  Actualización de los estados del sistema para contemplar la transición de las becas-crédito.

* **Documentación Adicional:** `LÉAME.md` y `becaCrédito description.md` con las especificaciones detalladas del requerimiento de la iteración.

## Herramientas y Metodología

* **Lenguaje de Modelado:** UML 2.x

* **Herramienta de Diagramación:** draw.io (diagrams.net)

* **Metodología:** Proceso Unificado de Ingeniería de Software (RUP/UP) - Enfoque orientado a objetos

* **Texto de Referencia:** *Classical and Object Oriented Software Engineering* (Stephen R. Schach)
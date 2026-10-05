# Mapa Terapéutico: Epilepsia Mioclónica Pediatría

> **Dashboard Clínico Interactivo y Sistema Analítico de Decisión para la Titulación de Antiepilépticos y Cannabinoides Pediátricos**
>
> *Versión 1.0 (Refactorización Integral e Interfaz Web Progresiva)*

---

## 📋 Índice
1. [Visión General del Proyecto](#-visión-general-del-proyecto)
2. [Caso Clínico y Contexto Farmacológico](#-caso-clínico-y-contexto-farmacológico)
3. [Algoritmos y Formulación Matemática](#-algoritmos-y-formulación-matemática)
   - [3.1 Esquema Posológico Ponderado por Kilogramo](#31-esquema-posológico-ponderado-por-kilogramo)
   - [3.2 Algoritmo de Titulación Semanal y Proyección de THC](#32-algoritmo-de-titulación-semanal-y-proyección-de-thc)
   - [3.3 Descarboxilación Térmica y Análisis de Extractos BHO](#33-descarboxilación-térmica-y-análisis-de-extractos-bho)
   - [3.4 Antropometría Pediátrica Estimada](#34-antropometría-pediátrica-estimada)
4. [Arquitectura del Dashboard Interactivo](#-arquitectura-del-dashboard-interactivo)
   - [Módulo 1: Esquema Actual Ponderado](#módulo-1-esquema-actual-ponderado)
   - [Módulo 2: Propuesta de Titulación de CBD](#módulo-2-propuesta-de-titulación-de-cbd)
   - [Módulo 3: Matriz de Interacciones y Laboratorios](#módulo-3-matriz-de-interacciones-y-laboratorios)
   - [Módulo 4: Monitor Semiológico y Triaje de Alarma](#módulo-4-monitor-semiológico-y-triaje-de-alarma)
   - [Módulo 5: Explorador Auditado de Evidencia Científica](#módulo-5-explorador-auditado-de-evidencia-científica)
   - [Módulo 6: Calculadora Analítica BHO / Concentrados](#módulo-6-calculadora-analítica-bho--concentrados)
   - [Módulo 7: Ruta Crítica Algorítmica](#módulo-7-ruta-crítica-algorítmica)
5. [Guía de Uso para Cuidadores y Profesionales](#-guía-de-uso-para-cuidadores-y-profesionales)
6. [Despliegue y Mantenimiento en GitHub Pages](#-despliegue-y-mantenimiento-en-github-pages)
7. [Descargo de Responsabilidad Médica](#-descargo-de-responsabilidad-médica)

---

## 🎯 Visión General del Proyecto

El **Mapa Terapéutico para Epilepsia Mioclónica Pediatría** es una aplicación web clínica monolítica, reactiva e interactiva, diseñada para brindar claridad matemática, rigor científico y seguridad asistencial a familias y equipos de neuropediatría.

El dashboard resuelve la complejidad intrínseca de la **politerapia antiepiléptica combinada con fitocannabinoides** (CBD y THC), permitiendo:
* Simular esquemas posológicos exactos por kilogramo de peso corporal.
* Auditar concentraciones reales frente a hipótesis de frasco.
* Proyectar curvas de titulación gradual de cannabinoides con cuantificación de exposición diaria a THC.
* Evaluar interacciones farmacocinéticas en el citocromo P450 (CYP2C19, CYP3A4).
* Ofrecer triaje de seguridad semiológica en tiempo real.
* Consultar evidencia científica graduada (Niveles I a V) con DOI verificado y PubMed.

---

## 🏥 Caso Clínico y Contexto Farmacológico

* **Paciente Modelo:** Pediátrico de 6 años, peso basal 26 kg, talla 111 cm, diagnóstico de **Epilepsia Mioclónica Refractaria / Encefalopatía Epiléptica**.
* **Tratamiento de Base Combinado:**
  1. **Clonazepam (Kriadex):** Benzodiazepina agonista alostérico del receptor GABA-A.
  2. **Levetiracetam (Tamlet-S):** Ligando de la proteína de vesículas sinápticas SV2A.
  3. **Topiramato (Topamax):** Bloqueador de canales de Na⁺ dependientes de voltaje, modulador GABA-A y AMPA/kainato, e inhibidor de anhidrasa carbónica.
  4. **CBD (RH Oil 5):** Cannabidiol en vehículo graso no estandarizado (hipótesis analítica: 21 mg/mL).
  5. **Cina 0/1:** Preparación homeopática (sin evidencia en epilepsia; no sustituye fármacos).

---

## 🧮 Algoritmos y Formulación Matemática

### 3.1 Esquema Posológico Ponderado por Kilogramo

La dosis administrada expresada en mg/kg/día se calcula como:

$$\text{Dosis Ponderada } \left(\frac{\text{mg}}{\text{kg}\cdot\text{día}}\right) = \frac{\text{Toma Diaria Total (mg)}}{\text{Peso Corporal (kg)}}$$

Para formulaciones líquidas en gotas o mililitros:

$$\text{Masa CBD Diaria (mg)} = \text{Volumen Diario (mL)} \times \text{Concentración } (\text{mg/mL})$$

*Donde:*
$$\text{Volumen Diario (mL)} = (\text{mL Toma Mañana} + \text{mL Toma Noche})$$

### 3.2 Algoritmo de Titulación Semanal y Proyección de THC

Para un esquema de escalado semanal con dosis inicial $D_0$, incremento semanal $\Delta D$ y dosis meta $D_{\text{meta}}$ (en mg/kg/día):

$$D_{\text{semana } n} = \min\left(D_0 + (n - 1) \cdot \Delta D,\; D_{\text{meta}}\right)$$

La masa total diaria de CBD prescrita es:

$$\text{CBD Diario (mg)} = D_{\text{semana } n} \times \text{Peso (kg)}$$

El volumen requerido por toma (para esquema de 2 tomas diarias equilibradas $\times 2$) con concentración de frasco $C_{\text{CBD}}$ (mg/mL):

$$\text{Volumen por Toma (mL)} = \frac{\text{CBD Diario (mg)}}{2 \times C_{\text{CBD}}}$$

La acumulación diaria de **THC residual** ($M_{\text{THC}}$, mg/día) con concentración $C_{\text{THC}}$ (mg/mL):

$$M_{\text{THC}} = \left(\frac{\text{CBD Diario (mg)}}{C_{\text{CBD}}}\right) \times C_{\text{THC}}$$

$$\text{Exposición Ponderada THC} = \frac{M_{\text{THC}}}{\text{Peso (kg)}} \quad \left(\frac{\text{mg}}{\text{kg}\cdot\text{día}}\right)$$

### 3.3 Descarboxilación Térmica y Análisis de Extractos BHO

En extractos artesanales o concentrados botánicos (p. ej. *Lemon KSH*), los cannabinoides se encuentran originalmente en forma ácida (THCA y CBDA). La descarboxilación térmica libera CO₂, convirtiéndolos en sus formas neutras biológicamente activas (THC y CBD).

#### Factor Estequiométrico de Descarboxilación ($F_{\text{decarb}} = 0.877$):
Representa la relación entre las masas moleculares de la forma neutra y la forma ácida:

$$F_{\text{decarb}} = \frac{\text{PM}_{\text{CBD}}}{\text{PM}_{\text{CBDA}}} = \frac{314.46 \text{ g/mol}}{358.47 \text{ g/mol}} \approx 0.877$$

#### Concentración Total Activa en Extracto ($C_{\text{activo}}$, mg/mL):

$$C_{\text{extracto}} = \frac{\text{Masa Muestra Extracto (g)} \times 1000 \text{ mg/g}}{\text{Volumen Final Dilución (mL)}}$$

$$\% \text{CBD}_{\text{total}} = \left(\% \text{CBDA} \times 0.877 \times \frac{\% \text{conversión}}{100}\right) + \% \text{CBD}_{\text{neutro}}$$

$$\% \text{THC}_{\text{total}} = \left(\% \text{THCA} \times 0.877 \times \frac{\% \text{conversión}}{100}\right) + \% \text{THC}_{\text{neutro}}$$

$$C_{\text{CBD activo}} = \left(\frac{\% \text{CBD}_{\text{total}}}{100}\right) \times C_{\text{extracto}} \quad (\text{mg/mL})$$

$$C_{\text{THC activo}} = \left(\frac{\% \text{THC}_{\text{total}}}{100}\right) \times C_{\text{extracto}} \quad (\text{mg/mL})$$

#### Proporción CBD:THC:

$$\text{Ratio CBD:THC} = \frac{C_{\text{CBD activo}}}{C_{\text{THC activo}}}$$

> **Criterio de Seguridad Pediátrica:** Si $\text{Ratio CBD:THC} < 16$, el preparado se clasifica como *THC-Dominante / No Apto Pediátrico* por riesgo de efectos neuropsiquiátricos disforizantes. La literatura pediátrica exige $\text{Ratio} \ge 16:1$.

### 3.4 Antropometría Pediátrica Estimada

* **Índice de Masa Corporal (IMC):**

$$\text{IMC} = \frac{\text{Peso (kg)}}{\left(\frac{\text{Talla (cm)}}{100}\right)^2} \quad \left(\text{kg/m}^2\right)$$

* **Superficie Corporal (Fórmula de Mosteller):**

$$\text{ASC} = \sqrt{\frac{\text{Talla (cm)} \times \text{Peso (kg)}}{3600}} \quad \left(\text{m}^2\right)$$

---

## 🎨 Arquitectura del Dashboard Interactivo

El dashboard está estructurado en **7 pestañas modulares** con persistencia de datos en `localStorage`:

### Módulo 1: Esquema Actual Ponderado
* **Tabla Interactiva:** Calcula mg/día y mg/kg/día para Kriadex, Tamlet-S, Topamax y RH Oil 5.
* **Componente de Barras de Rango:** Visualización en miniatura con marcadores de posición relativa dentro del rango terapéutico.
* **Gráfico SVG Interactivo (`chartCurrentDoses`):** Comparativa gráfica vectorial entre la dosis actual y los límites normativos.
* **Lectura Contextual:** Modula explicaciones según la perspectiva seleccionada (*Familia* vs. *Neurología*).

### Módulo 2: Propuesta de Titulación de CBD
* **Calculadora de Escalado:** Permite ajustar concentración COA de CBD, THC, dosis inicial, escalón semanal y meta.
* **Gráfico SVG Vectorial (`chartPropTitration`):** Representa la curva de titulación semana a semana y la sombra de área bajo la curva.
* **Proyección de THC Diario:** Cuantifica la ingesta de THC en cada semana para prevenir toxicidad.
* **Alertas Dinámicas:** Notifica si la meta supera 12 mg/kg/día o si el THC es significativo.

### Módulo 3: Matriz de Interacciones y Laboratorios
* **Matriz Pharmacocinética:** Detalla interacciones par a par (ej. CBD + Clonazepam, CBD + Topiramato).
* **Fichas PK/PD:** Vías de eliminación, vida media ($\text{t}_{1/2}$) y alertas de hepatotoxicidad.
* **Calendario de Controles:** Programación de análisis de ALT/AST, bicarbonato, biometría y niveles séricos.

### Módulo 4: Monitor Semiológico y Triaje de Alarma
* **Checklist de Signos y Síntomas:** 10 indicadores clínicos clasificados por severidad (1 a 3).
* **Motor de Triaje:** Genera avisos inmediatos:
  * *Nivel 3:* Emergencia hospitalaria / Urgencias.
  * *Nivel 2:* Consulta médica el mismo día.
  * *Nivel 1:* Notificación telefónica a neuropediatría.

### Módulo 5: Explorador Auditado de Evidencia Científica
* **Filtros por Nivel (I a V) y Tema:** Explora ensayos aleatorizados (Devinsky, Thiele, Miller), metaanálisis (Pamplona 2018) y análisis químicos (Ríos-Pohl 2024).
* **Tabla Comparativa Directa:** Enfrenta CBD purificado farmacéutico vs. extracto de espectro completo.
* **Tarjetas Interactivas:** Popovers desplegables con hallazgos clave, relevancia clínica, DOI directo y enlace de búsqueda en PubMed.

### Módulo 6: Calculadora Analítica BHO / Concentrados
* **Simulador de Descarboxilación:** Calcula concentraciones reales de CBD y THC activo aplicando el factor 0.877.
* **Verificador de Ratio:** Evalúa si la muestra cumple el umbral pediátrico $\ge 16:1$.
* **Botón de Carga Prototípica:** Permite cargar valores promedio de mercado (71% THC) para evidenciar su inviabilidad en pediatría.

### Módulo 7: Ruta Crítica Algorítmica
* **Diagrama de Flujo (8 Pasos):** Desde el diagnóstico diferencial sindrómico hasta la evaluación a 12 semanas.
* **Nodos de Decisión ("Si... Entonces"):** Guía paso a paso para el profesional y la familia.

---

## 📖 Guía de Uso para Cuidadores y Profesionales

1. **Ajuste de Parámetros del Paciente:**
   - Haga clic en la píldora superior del paciente (`26 kg · 6 a · 111 cm`).
   - Ingrese el peso, talla y edad exactos. Todos los cálculos del dashboard se actualizarán automáticamente.
2. **Conmutación de Perspectiva:**
   - Seleccione **Familia** para un lenguaje claro, accesible y enfocado en la vigilancia en casa.
   - Seleccione **Neurología** para desplegar términos farmacocinéticos, vías CYP y detalles metodológicos.
3. **Selección de Tema Visual:**
   - Alterne entre **Claro**, **Oscuro** o **Auto** (sincronizado con las preferencias del sistema operativo).
4. **Exportación e Impresión:**
   - Utilice la función nativa del navegador (`Ctrl + P` o `Cmd + P`). El dashboard incluye estilos CSS específicos de impresión que ocultan controles interactivos y formatean las tablas para el expediente clínico.

---

## 🚀 Despliegue y Mantenimiento en GitHub Pages

El proyecto cuenta con integración continua mediante **GitHub Actions** en `.github/workflows/deploy.yml`.

### Estructura de Archivos en el Repositorio:
```
./
├── .github/
│   └── workflows/
│       └── deploy.yml                       # Workflow de despliegue automático a GitHub Pages
├── index.html                               # Aplicación principal monolítica refactorizada (v1)
├── Mapa terapéutico_ epilepsia mioclónica.md # Documento fuente original en Markdown
├── Mapa terapéutico_ epilepsia mioclónica (2).html # Prototipo HTML legado de respaldo
├── README.md                                # Documentación técnica exhaustiva
├── devlog.md                                # Bitácora de desarrollo de la versión 1.0
└── gap_analysis.md                          # Análisis de brechas (Legado vs v1)
```

### Configuración en GitHub:
1. Ir a **Settings** > **Pages** en el repositorio.
2. En **Source**, seleccionar **GitHub Actions**.
3. Cada `push` a la rama `main` o `master` ejecutará el despliegue automático hacia la URL pública de GitHub Pages.

---

## ⚠️ Descargo de Responsabilidad Médica

*Esta herramienta digital interactiva ha sido desarrollada estrictamente con fines educativos, informativos y de apoyo analítico a la toma de decisiones. No constituye una prescripción médica, indicación terapéutica directa ni sustituye la consulta, diagnóstico o manejo especializado de un neuropediatra o profesional de la salud titulado.*

*Cualquier ajuste posológico en antiepilépticos o cannabinoides debe ser evaluado y prescripto de manera individualizada por el médico tratante.*

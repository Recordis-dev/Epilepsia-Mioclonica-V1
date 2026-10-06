# Gap Analysis & Synergistic Feature Evolution

> **Análisis Comparativo de Brechas, Evolución de Funcionalidades y Registro Sínergico So-Far**
>
> *Proyecto: Mapa Terapéutico e Interactivo para Epilepsia Mioclónica Pediatría*

---

## 📋 Resumen Ejecutivo de la Evolución Terapéutica

Este documento detalla la comparativa técnica entre el **Prototipo Legado (v0)**, las **Mejoras Intermedias** y la **Versión 1.0 Final Refactorizada con Sinergia Total**.

El principio fundamental que guió este desarrollo fue la **sinergia incremental**: conservar e integrar **el 100% del contenido clínico, datos, citas y notas originales** mientras se agregan capacidades interactivas avanzadas, tarjetas flotantes al pasar el cursor (*On-Hover Flashcards*), gráficos vectoriales SVG dinámicos y herramientas de triaje semiológico.

---

## 📊 Matriz Sínergica Comparativa (v0 vs. v1.0)

| Módulo / Funcionalidad | Prototipo Original Legado (v0) | Versión 1.0 Refactorizada Sínergica | Aporte Sínergico / Mejora |
| :--- | :--- | :--- | :--- |
| **Tarjeta de Ficha Médica (*Flashcards*)** | Ocultamiento estático básico | **Flashcards emergentes con despliegue al pasar el cursor (`:hover`), foco (`:focus-within`) y clic** | Lectura ultra fluida, rápida e intuitiva sin perder el hilo de navegación. |
| **Volumen de Literatura y Citas** | 23 Referencias (algunas con errores de DOI) | **23 Referencias con fe de erratas corregida, DOI directo verificado y búsqueda automatizada en PubMed** | 100% de conservación de evidencia con integridad académica garantizada. |
| **Ruta Crítica Algorítmica** | 9 Pasos secuenciales básicos | **9 Pasos interactivos completos con roles (QFB / Neuropediatría), nodos condicionales "Si... Entonces" e *Insights* clínicos integrados** | Claridad en la toma de decisiones para el equipo médico y la familia. |
| **Gráficos de Dosificación** | Barras HTML estáticas simples | **Gráficos vectoriales SVG dinámicos e interactivos** (Rangos normativos + Curva de escalado semanal con área bajo la curva) | Visualización cuantitativa inmediata de la exposición a fármacos y THC. |
| **Proyección de THC Acumulado** | Inexistente en la tabla semanal | **Cuantificación semanal explícita de THC acumulado (mg/día y mg/kg/día)** | Previene la exposición involuntaria a THC en cerebro en desarrollo. |
| **Calculadora BHO / Concentrados** | Aritmética simple sin descarboxilación | **Calculadora analítica completa con factor estequiométrico 0.877, conversión ácida (THCA/CBDA) y verificación de ratio $\ge 16:1$** | Precisión química y farmacéutica de laboratorio. |
| **Triaje Semiológico** | Texto plano simple | **Monitor interactivo con checklist de 10 síntomas, ponderación de urgencia (1 a 3) y avisos dinámicos** | Respuesta rápida de seguridad ante eventos adversos o crisis. |
| **Conmutador de Perspectiva** | Ocultamiento CSS simple | **Perspectiva activa dual (*Familia* vs. *Neurología*)** | Adapta el lenguaje y nivel de detalle según la audiencia. |
| **Persistencia de Datos** | Sin almacenamiento | **Sincronización en tiempo real con `localStorage`** | Preserva peso, talla, edad, dosis y selecciones al recargar. |
| **Despliegue Automático** | Manual / Sin CI | **GitHub Actions Workflow (`.github/workflows/deploy.yml`)** | Despliegue continuo hacia GitHub Pages en cada push. |

---

## 🔍 Inventario Detallado de Funcionalidades So-Far

### 1. Sistema de Tarjetas Emergentes Al Pasar el Cursor (*On-Hover Flashcards*)
- **Mecanismo:** CSS puro combinado con interacción JavaScript (`:hover`, `:focus-within` y `.expanded`).
- **Comportamiento:** Al posicionar el cursor o enfocar con el teclado cualquier tarjeta de referencia bibliográfica o paso de la ruta crítica, se despliega una ficha flotante enriquecida con:
  - **Hallazgo Clave:** Resumen metodológico del estudio.
  - **Relevancia para el Caso:** Aplicación práctica al esquema del paciente.
  - **Identificadores:** Enlaces directos a DOI y PubMed.

### 2. Conservación del 100% de los Datos del Repositorio
- **Evidencia Científica:** Se preservan los 23 registros de literatura (Ensayos Fase III de Devinsky, Thiele, Miller; metaanálisis de Pamplona 2018; estudios de interacciones de Gaston, Geffrey, Szaflarski; preclínica de Russo, Santiago, Cogan; y análisis analíticos de Ríos-Pohl 2024).
- **Ruta Crítica Integrada:** Se conservan los 9 pasos del protocolo desde el diagnóstico diferencial sindrómico hasta la evaluación a 12 semanas.

---

## 📈 Conclusión del Análisis

La versión **v1.0** representa la **sinergia perfecta**: no se eliminó ni un solo dato o concepto del trabajo previo, sino que se potenciaron mediante una interfaz web accesible, reactiva y visualmente superior.

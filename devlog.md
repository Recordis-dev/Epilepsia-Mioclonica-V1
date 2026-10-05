# Development Log (DevLog v1.0)

> **Bitácora de Desarrollo, Arquitectura e Ingeniería de Software**
>
> *Proyecto: Refactorización y Creación del Dashboard Interactivo - Mapa Terapéutico para Epilepsia Mioclónica Pediatría*

---

## 📅 Hitos del Desarrollo

### Fase 1: Análisis y Exploración del Repositorio Basal
- **Fecha:** Octubre 2026
- **Acciones Realizadas:**
  - Inspección profunda del archivo Markdown fuente (`Mapa terapéutico_ epilepsia mioclónica.md`) y del prototipo HTML legado monolítico (`Mapa terapéutico_ epilepsia mioclónica (2).html`).
  - Extracción y análisis del bloque JavaScript original (31 KB unificado).
  - Identificación de inconsistencias citacionales, vacíos de cálculo en acumulación de THC y falta de gráficos vectoriales interactivos.

---

### Fase 2: Arquitectura del Nuevo Sistema (`index.html`)
- **Decisión de Arquitectura:** Creación de una aplicación web monolítica moderna (HTML5, CSS3 modular con variables de diseño, Vanilla JS ES6+) para garantizar **cero dependencias de compilación** y despliegue automático inmediato en GitHub Pages.
- **Aspectos Clave de UI/UX:**
  - Tipografía médica especializada: *Atkinson Hyperlegible* (legibilidad mejorada) y *Newsreader* (elegancia editorial médica).
  - Selector de perspectiva activa: Modo **Familia** (lenguaje preventivo accesible) vs. Modo **Neurología** (detalle técnico farmacocinético, vías CYP450 y metodológico).
  - Selector de modo de tema: **Claro**, **Oscuro** (Dark Mode optimizado para baja fatiga visual) y **Auto**.
  - Panel deslizante de datos del paciente con persistencia de estado mediante `localStorage`.

---

### Fase 3: Implementación de Módulos e Interactividad Vectorial SVG
1. **Módulo 1 (Esquema Actual):**
   - Implementación de tabla reactiva de dosificación por kg/día.
   - Desarrollo del componente vectorial **SVG `chartCurrentDoses`** para comparar dosis actuales con barras de rango objetivo normativo.
2. **Módulo 2 (Propuesta CBD & Titulación):**
   - Desarrollo del simulador de titulación semanal con cálculo automático de acumulación diaria de THC.
   - Creación del **Gráfico Vectorial SVG `chartPropTitration`** con área bajo la curva y marcadores de hitos de laboratorio.
3. **Módulo 3 (Interacciones & PK/PD):**
   - Construcción de la matriz de interacciones combinadas y fichas farmacocinéticas de clonazepam, levetiracetam, topiramato y CBD.
4. **Módulo 4 (Semiología & Triaje):**
   - Implementación del checklist interactivo de 10 síntomas con ponderación de urgencia (Nivel 1 a 3) y caja de alerta dinámica.
5. **Módulo 5 (Explorador de Evidencia):**
   - Sistema de filtrado multidireccional por Nivel de Evidencia (I a V) y Tema.
   - Fichas interactivas con popovers explicativos, DOIs verificados y búsqueda directa en PubMed.
6. **Módulo 6 (Calculadora BHO / Concentrados):**
   - Formulación analítica de descarboxilación con factor estequiométrico 0.877 y validación de ratio pediátrico $\ge 16:1$.
7. **Módulo 7 (Ruta Crítica Algorítmica):**
   - Diagrama de flujo secuencial de 8 pasos con nodos condicionales "Si... Entonces".

---

### Fase 4: Automatización CI/CD para GitHub Pages
- **Archivo Creado:** `.github/workflows/deploy.yml`
- **Configuración:** Workflow oficial de GitHub Actions utilizando `actions/checkout@v4`, `actions/configure-pages@v5`, `actions/upload-pages-artifact@v3` y `actions/deploy-pages@v4`.
- **Resultado:** Despliegue automático y transparente en GitHub Pages con cada commit enviado a las ramas `main` o `master`.

---

### Fase 5: Documentación Técnica exhaustiva
- Elaboración de los tres documentos exigidos:
  1. `README.md`: Max verbose, con sustento clínico, fórmulas matemáticas y guía de uso.
  2. `gap_analysis.md`: Análisis comparativo de brechas entre el prototipo legado v0 y la v1.0.
  3. `devlog.md`: Registro cronológico y técnico de la ingeniería aplicada.

---

## 🧪 Verificación y Pruebas
- **Validación Estructural HTML:** Confirmación de etiquetas semánticas y cierre correcto (`<!DOCTYPE html>` a `</html>`).
- **Verificación de IDs en DOM:** Comprobación automatizada mediante Node.js de la presencia del 100% de los IDs requeridos.
- **Prueba de Renderizado:** Ejecución de servidor local HTTP y verificación de transferencia sin errores (HTTP 200 OK).

---

## 📌 Conclusión
La versión **v1.0** se encuentra completada, verificada y documentada con el máximo rigor exigido.

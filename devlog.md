# Development Log (DevLog v1.0 Sínergico)

> **Bitácora de Desarrollo, Integración Sínergica e Inventario Tecnológico**
>
> *Proyecto: Refactorización y Creación del Dashboard Interactivo - Mapa Terapéutico para Epilepsia Mioclónica Pediatría*

---

## 🛠️ Filosofía de Desarrollo: Sinergia Incremental
El objetivo principal de la Versión 1.0 fue lograr la **sinergia absoluta**: actualizar la experiencia visual y funcional (UI/UX) **sin restar ni omitir ningún dato, cita, tabla, nota o insight presente en el prototipo original v0**.

---

## 🚀 Cronología de Funcionalidades Implementadas

### 1. Interfaz Web Reactiva y Accesible (`index.html`)
- **Arquitectura Monolítica Progresiva:** HTML5 semántico, CSS3 con variables custom para modo Claro/Oscuro/Auto, Vanilla JS ES6+.
- **Navegación por Pestañas Adaptativas:** 7 pestañas modulares con iconos vectoriales.
- **Selector de Perspectiva Activa:**
  - *Modo Familia:* Foco en alertas, diario de crisis y lenguaje accesible.
  - *Modo Neurología:* Foco en farmacocinética, vías CYP, vidas medias e interacciones.
- **Persistencia en `localStorage`:** Mantiene guardados los parámetros del paciente (peso, talla, edad, sexo, dosis) entre sesiones.

### 2. Tarjetas Emergentes al Pasar el Cursor (*On-Hover Flashcards*)
- Implementación de la funcionalidad **On-Hover / On-Focus Flashcards** en el explorador de evidencia.
- Al pasar el cursor o hacer foco sobre una tarjeta bibliográfica, se despliega instantáneamente un popover flotante (*Flashcard*) con los hallazgos clave, relevancia clínica, etiqueta de DOI verificado y enlace directo de búsqueda en PubMed.

### 3. Componentes Vectoriales SVG Interactivas
- **Gráfico de Dosificación Actual (`chartCurrentDoses`):** Muestra visualmente las dosis en mg/kg/día frente a los rangos terapéuticos normativos.
- **Gráfico de Titulación Semanal (`chartPropTitration`):** Dibuja la curva de escalado gradual de CBD, área bajo la curva e hitos de laboratorio.

### 4. Cobertura del 100% de la Data Original
- **23 Referencias de Literatura:** Incluye todos los niveles de evidencia (I a V), citando estudios aleatorizados, metaanálisis, preclínica y química analítica de concentrados.
- **9 Pasos de Ruta Crítica:** Mantiene todos los pasos del protocolo con roles, decisiones "Si... Entonces" e *Insights* prácticos.
- **Calculadora BHO / Concentrados:** Incorpora la fórmula de descarboxilación ($0.877$), desglose de THCA/CBDA y verificación de ratio $\ge 16:1$.

---

## 📋 Inventario Sínergico de Archivos en el Repositorio

```
./
├── .github/workflows/deploy.yml # Workflow oficial de GitHub Actions para GitHub Pages
├── index.html                  # Dashboard web principal interactivo v1.0
├── README.md                   # Documentación técnica max-verbose y guía del dashboard
├── gap_analysis.md             # Matriz comparativa de brechas y evolución sínergica
├── devlog.md                   # Bitácora de desarrollo y registro tecnológico
├── Mapa terapéutico_ epilepsia mioclónica.md # Documento fuente original Markdown
└── Mapa terapéutico_ epilepsia mioclónica (2).html # Prototipo borrador original v0
```

---

## ✅ Conclusión
El desarrollo ha culminado exitosamente reuniendo todas las mejoras previas con las nuevas capacidades avanzadas de UI/UX, gráficos SVG y automatización de despliegue.

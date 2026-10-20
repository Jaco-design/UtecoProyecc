# 📚 Documentación y Registro de Cambios - UtecoProyecc

**Estudiante:** Rafely Aracena  
**Carrera:** Ingeniería de Software  
**Institución:** UTECO  
**Proyecto:** Portafolio Web Personal y Prácticas de Desarrollo Web  
**Fecha de inicio de mejoras:** 20 de Octubre de 2026  

---

## 🎯 Objetivo del Proyecto

Transformar el repositorio inicial de prácticas en un **Portafolio Web Profesional y Moderno**, optimizado para publicación en la web (GitHub Pages), con código semántico, diseño responsivo para móviles, sin duplicidad de archivos y con un historial de Git limpio y profesional.

---

## 📋 Registro Cronológico de Cambios (Changelog)

### [2026-10-20] - Fase 1: Diagnóstico y Resolución del Conflicto de Git

#### 1. Diagnóstico del Estado del Repositorio
* **Problema detectado:** El repositorio local tenía un estado de fusión incompleta (`merge in progress`) tras intentar sincronizar con `origin/main`.
* **Causa técnica:** Había commits divergentes en la rama remota (`origin/main`) y en la rama local (`main`), provocando conflictos en:
  * `MiniPortafolio/complemento.html` vs `Perfil/index1.html`
  * `MiniPortafolio/index.html`
  * `carpeta1/index1.html` (borrado en ambas partes)
* **Marcadores de conflicto en código:** Se encontraron marcas de texto como `<<<<<<<< HEAD`, `========` y `>>>>>>>>` dentro de los archivos HTML, lo cual corrompía la visualización de las páginas en el navegador.

#### 2. Acciones Realizadas
1. **Limpieza de marcadores de conflicto:** Se eliminaron las marcas de Git en `MiniPortafolio/complemento.html` y `Perfil/index1.html`, restaurando los enlaces relativos limpios: `<a href="HTLyJavaScript.html">Volver</a>`.
2. **Eliminación de archivos huérfanos:** Se procesó la baja definitiva de `carpeta1/index1.html` mediante `git rm`.
3. **Consolidación de imágenes:** Se confirmó el uso de `sensor.png` y se retiraron del control de versiones las imágenes obsoletas (`biografia.png`, `boton.png`, `hobies.png`).
4. **Cierre de la fusión:** Se ejecutaron `git add` de los archivos resueltos y se realizó el commit de merge:
   `git commit -m "Merge branch 'origin/main': resolver conflictos y actualizar portafolio"`.
5. **Estado resultante:** Repositorio en rama `main` completamente limpio y sincronizado (`nothing to commit, working tree clean`).

---

## 🧭 Plan de Mejoras Técnicas (Hoja de Ruta)

| # | Tarea | Estado | Descripción |
|---|---|:---:|---|
| 1 | **Resolución de conflictos Git** | ✅ Completado | Árbol de Git reparado, sin marcas de conflicto. |
| 2 | **Creación de Documentación** | ✅ Completado | Bitácora de cambios y conceptos para aprendizaje. |
| 3 | **Unificación de estructura de archivos** | ⏳ En proceso | Colocar `index.html` en raíz, mover estilos e imágenes a carpetas organizadas (`assets/css`, `assets/img`) y eliminar carpetas duplicadas obsoletas (`Perfil/`, `biografia/`). |
| 4 | **Corrección ortográfica y redacción** | ⏳ Pendiente | Corregir textos en HTML ("aprendisaje", "pyocto", acentos, etc.). |
| 5 | **Semántica HTML y accesibilidad** | ⏳ Pendiente | Corregir elementos dentro de `<ul>`, extraer `<footer>` de `<main>`, vincular Google Fonts (`Poppins`). |
| 6 | **Diseño CSS y Responsive Design** | ⏳ Pendiente | Tarjetas modernas de proyectos con Flexbox/Grid, estilos adaptables para celular (`max-width: 100%`). |
| 7 | **Archivos esenciales (`README.md`, `.gitignore`)** | ⏳ Pendiente | Presentación del portafolio y exclusión de archivos temporales. |

---

## 💡 Conceptos Clave de Aprendizaje

### 1. ¿Qué es un conflicto de Git y por qué sucede?
Ocurre cuando dos personas (o tú mismo desde dos lugares diferentes) modifican las mismas líneas de un archivo o cuando se renombra un archivo en una rama mientras en otra se edita. Git no puede adivinar cuál versión es la correcta, así que coloca marcadores:
* `<<<<<<< HEAD`: Lo que tienes en tu rama local actual.
* `=======`: La línea divisoria.
* `>>>>>>> hash_o_rama`: Lo que viene de la otra rama (remoto).

**La solución:** Abrir el archivo, decidir con qué código quedarse, borrar las líneas con `<`, `=` y `>`, guardar el archivo y hacer `git add <archivo>` seguido de `git commit`.

### 2. Rutas Absolutas vs. Rutas Relativas en la Web
* **Ruta Absoluta (`/MiniPortafolio/index.html`):** Empieza con `/` y busca desde la raíz del servidor o del disco duro. En GitHub Pages o al abrir el archivo localmente (`file:///C:/...`), casi siempre falla porque busca fuera de la carpeta del proyecto.
* **Ruta Relativa (`./index.html` o `index.html` o `../index.html`):** Busca en relación a dónde está parado el archivo actual. Es la forma correcta y portable de enlazar páginas e imágenes en proyectos web estáticos.

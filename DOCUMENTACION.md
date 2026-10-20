# 📚 Documentación Técnica y Registro de Cambios - UtecoProyecc

**Estudiante:** Rafely Aracena  
**Carrera:** Ingeniería de Software  
**Institución:** Universidad Tecnológica del Cibao Oriental (UTECO)  
**Proyecto:** Portafolio Web Personal y Prácticas de Desarrollo Web  
**Fecha de actualización:** 20 de Octubre de 2026  

---

## 🎯 Objetivo General

Transformar el repositorio inicial de prácticas académicas en un **Portafolio Web Profesional, Limpio y Moderno**, optimizado para publicación en la web (GitHub Pages), con arquitectura estándar de carpetas, código HTML5 semántico, diseño responsivo para móviles, sin duplicidad de archivos y con un historial de Git impecable.

---

## 📋 Registro Cronológico de Cambios (Changelog)

### [2026-10-20] - Fase 1: Diagnóstico y Resolución del Conflicto de Git

#### 1. Diagnóstico del Estado Inicial
* **Problema detectado:** El repositorio local se encontraba bloqueado en medio de un `git merge` no resuelto contra `origin/main`.
* **Causa técnica:** Commits divergentes entre el repositorio remoto en GitHub y el repositorio local. Ambas ramas habían creado y renombrado archivos simultáneamente (`Perfil/index1.html` vs `MiniPortafolio/complemento.html`, `carpeta1/index1.html`, `index.html`).
* **Marcadores de conflicto en código:** En `complemento.html` y en `index1.html` habían quedado grabadas líneas de conflicto de Git (`<<<<<<<< HEAD`, `========`, `>>>>>>>>`), las cuales se mostraban en pantalla y rompían la visualización de la web.

#### 2. Acciones Realizadas
1. **Limpieza manual de los marcadores:** Se retiraron las marcas de texto de Git y se consolidó el enlace limpio `<a href="HTLyJavaScript.html">Volver</a>`.
2. **Eliminación de archivos huérfanos:** Se retiró definitivamente `carpeta1/index1.html` usando `git rm`.
3. **Consolidación de imágenes:** Se confirmó el uso de la imagen actual `sensor.png` y se retiraron las imágenes antiguas que ya no se utilizaban (`biografia.png`, `boton.png`, `hobies.png`).
4. **Cierre y commit de fusión:** Se indexaron los archivos con `git add` y se completó el merge mediante el commit:
   `git commit -m "Merge branch 'origin/main': resolver conflictos y actualizar portafolio"`.

---

### [2026-10-20] - Fase 2: Reestructuración y Arquitectura del Proyecto

#### 1. Problema de la Estructura Anterior
* El portafolio estaba encerrado en una subcarpeta llamada `MiniPortafolio/`. Si se publicaba en la raíz de un servidor web o GitHub Pages, la página de inicio no cargaba automáticamente.
* Existían tres carpetas con archivos duplicados (`biografia/`, `Perfil/` y `MiniPortafolio/`), lo que generaba confusión sobre qué archivo editar.
* Las rutas en los enlaces eran absolutas (ej. `/MiniPortafolio/index.html`), lo que causaba enlaces rotos al abrir el proyecto con doble clic (`file:///`) o en un subdominio.

#### 2. Nueva Estructura Profesional Implementada
```text
UtecoProyecc/
│
├── index.html               # Portafolio principal en la raíz (carga directa en la web)
├── README.md                # Presentación profesional del repositorio para GitHub
├── DOCUMENTACION.md         # Bitácora técnica y guía de estudio
├── .gitignore               # Configuración para ignorar temporales del sistema
│
├── assets/                  # Recursos multimedia y estilos
│   ├── css/
│   └── styles.css           # Hoja de estilos centralizada y responsive
│   └── img/
│       ├── perfil.jpeg      # Fotografía de perfil optimizada
│       └── sensor.png       # Imagen del proyecto de sensor IoT
│
└── pages/                   # Páginas secundarias y prácticas
    ├── biografia.html       # Biografía personal completa y estilizada
    ├── practica-js.html     # Práctica de interacción y eventos con JavaScript
    └── complemento.html     # Página de complemento con perfil de habilidades
```

3. **Limpieza:** Se eliminaron las carpetas obsoletas y duplicadas (`biografia/`, `Perfil/` y `MiniPortafolio/`), quedando un único árbol de archivos coherente.

---

### [2026-10-20] - Fase 3: Correcciones de Código, Semántica y Diseño

#### 1. Correcciones de Semántica HTML y Accesibilidad
* **Etiquetas `<ul>` y `<ol>`:** Anteriormente, se colocaban etiquetas `<p>`, `<a>`, `<h3>` y `<hr>` directamente dentro de listas desordenadas y ordenadas. En HTML estándar, los únicos hijos permitidos de una lista son `<li>`. Se reestructuró la sección de proyectos como una cuadrícula (`grid`) de artículos semánticos `<article class="project-card">`.
* **Posición de `<footer>`:** Se extrajo el pie de página de la etiqueta `<main>` para respetar la jerarquía estructural recomendada por la W3C (`header`, `main`, `footer` como hermanos).
* **Integración de Tipografía:** Se vinculó la fuente **Poppins** desde Google Fonts en el `<head>` de todas las páginas para garantizar uniformidad visual en cualquier dispositivo.
* **Metadatos y SEO:** Se añadieron etiquetas `<meta name="description">` y `<meta name="author">` en todos los documentos.

#### 2. Correcciones Ortográficas y de Redacción
Se corrigieron todas las faltas ortográficas para reflejar un perfil profesional de ingeniería:
* *"aprendisaje"* ➔ **aprendizaje**
* *"prodran"* ➔ **podrán**
* *"Ingeneria"* ➔ **Ingeniería**
* *"pyocto"* ➔ **proyecto**
* *"utilisando"* ➔ **utilizando**
* *"HTLM"* ➔ **HTML**
* *"humadad"* ➔ **humedad**
* *"rdes sociales"* ➔ **redes sociales**
* *"apreder"* ➔ **aprender**
* *"cirbeguridad"* ➔ **ciberseguridad**
* *"etico"* ➔ **ético**
* *"inovadoras"* ➔ **innovadoras**
* *"pais"* ➔ **país**
* *"pimer pagina"* ➔ **primera página**
* *"Has Click"* ➔ **Haz clic**
* *"se algunas"* ➔ **Sé algunas**
* Acentos ortográficos en títulos: *"Sobre mí"*, *"Biografía"*, *"botón"*, *"Sánchez Ramírez"*.

#### 3. Mejoras Visuales y Responsive en CSS (`styles.css`)
* **Variables CSS (`:root`):** Se crearon variables para colores corporativos (`--primary-color: #1e3a8a`, `--accent-color: #facc15`, etc.), facilitando cambios globales de diseño.
* **Diseño en Tarjetas (CSS Grid):** La sección de proyectos ahora presenta tarjetas modernas con efectos de elevación al pasar el cursor (`transform: translateY(-5px)`), sombras suaves y etiquetas (*badges*) para las tecnologías (`HTML5`, `CSS3`, `JavaScript`, `PHP`, `IoT`).
* **Adaptabilidad Móvil (Responsive Design):** Reglas con `@media (max-width: 768px)` para que el menú, la imagen de perfil, las tarjetas de proyectos y los enlaces de contacto se adapten fluidamente a pantallas de teléfonos inteligentes sin desbordamientos horizontales.

---

## 💡 Conceptos Clave para Aprender y Recordar

### 1. ¿Cómo se produce un conflicto en Git y cómo prevenirlo?
* **¿Por qué ocurre?** Cuando dos ramas o dos personas modifican las mismas líneas de un archivo o cuando se borra/renombra un archivo en una rama mientras en la otra se sigue editando.
* **¿Qué significan las marcas?**
  * `<<<<<<< HEAD`: Código de tu rama actual.
  * `=======`: Línea divisoria.
  * `>>>>>>> <commit>`: Código proveniente de la rama remota o combinada.
* **Buenas prácticas:** Hacer siempre `git pull` antes de empezar a programar un cambio nuevo para tener la última versión actualizada.

### 2. Rutas Relativas vs. Rutas Absolutas
* **Ruta Absoluta (`/assets/img/foto.jpg`):** Comienza con `/` y le dice al navegador: *"busca en la raíz absoluta del disco o del dominio"*. Si tu página está en `github.io/UtecoProyecc/`, una ruta absoluta buscará en `github.io/assets/` y la imagen fallará (error 404).
* **Ruta Relativa (`assets/img/foto.jpg` o `../assets/img/foto.jpg`):** Le dice al navegador: *"busca a partir de la carpeta donde se encuentra este archivo HTML"*. Es la forma estándar y segura para proyectos web.

---

## 🚀 Próximo Paso Recomendado: Subir a GitHub

Tus cambios locales están confirmados en Git con commits limpios. Para publicarlos en tu repositorio remoto en GitHub:
```bash
git push origin main
```
Y si deseas activar **GitHub Pages**, ve a tu repositorio en GitHub > **Settings** > **Pages** > Selecciona rama `main` y carpeta `/ (root)` > Guardar.

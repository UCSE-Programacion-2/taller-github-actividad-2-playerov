[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/aLODUeLq)
# CV web profesional con BootstrapMade, GitHub y GitHub Pages

Actividad práctica para construir un **currículum en formato web**, aplicar un **flujo de trabajo colaborativo** (issues, ramas, pull requests y merge) y **publicar** el resultado en **GitHub Pages**. Aprenderás a combinar plantillas profesionales, el IDE con asistencia de IA y buenas prácticas de control de versiones.

---

## Consigna general (User Story)

> **Como** estudiante que busca presentar su perfil profesional de forma moderna y accesible,  
> **quiero** adaptar una plantilla de CV basada en Bootstrap (por ejemplo, de [BootstrapMade — plantillas Resume / CV](https://bootstrapmade.com/bootstrap-resume-cv-templates/)) usando mi IDE y apoyo de IA,  
> **para** versionar los cambios con Git, integrarlos mediante Pull Requests vinculados a issues y **desplegar** el sitio estático en GitHub Pages siguiendo un flujo ordenado y revisable.

**Criterios de éxito sugeridos**

- El sitio refleja tus datos (nombre, formación, experiencia, contacto, etc.) y se ve bien en móvil y escritorio.
- El historial muestra **commits con mensajes claros** (Convención de commits convencionales).
- Hay al menos un **Pull Request** que cierra el issue correspondiente con `Closes #N`.
- El CV está **publicado** en GitHub Pages y la URL es compartible.

---

## Requisitos previos

- Cuenta en [GitHub](https://github.com/).
- Git instalado localmente y conocimiento básico de terminal (o uso del cliente integrado del IDE).
- Editor recomendado: **Visual Studio Code** o **Cursor**, con asistencia de IA si lo permiten las políticas de tu institución.
- Acceso al listado de plantillas Resume/CV de BootstrapMade: [Bootstrap Resume / CV Templates](https://bootstrapmade.com/bootstrap-resume-cv-templates/).

**Licencias:** revisa la licencia de la plantilla que elijas (gratuita o premium) y respeta sus términos al publicar tu sitio.

---

## Importante: no trabajar directamente en `main`

La rama **`main`** debe mantenerse como línea base **estable** y revisada. Todo cambio de contenido o estructura del CV debe desarrollarse en una **rama de trabajo**, integrarse vía **Pull Request** y mergearse solo después de una revisión breve (autorrevisión o compañero/docente).

| Evitar | Preferir |
|--------|------------|
| Commits directos a `main` para la actividad | Rama `feature/...` o `fix/...` desde `main` actualizada |
| Un solo commit gigante al final | Commits pequeños y con mensaje convencional |
| Mezclar sin issue/PR | Issue → rama → PR con `Closes #…` |

---

## Fases de la actividad

### Fase 1 — Elegir plantilla y editar con el IDE (y opcionalmente IA)

1. Entra en [BootstrapMade — Resume / CV](https://bootstrapmade.com/bootstrap-resume-cv-templates/) y **elige una plantilla** acorde a tu perfil (creativo, minimal, una página, etc.).
2. **Descarga** la plantilla (según las instrucciones del sitio) y **copia los archivos** al repositorio (por ejemplo en la raíz o en una carpeta `docs/` / `src/` — sé consistente con lo que luego configurarás para GitHub Pages).
3. Abre el proyecto en tu IDE. **Sustituye** textos de ejemplo por tu información real (datos personales no sensibles que sí quieras mostrar públicamente).
4. Usa la **IA de forma responsable**: pide ayuda para estructurar secciones, mejorar redacción o accesibilidad; **tú** decides el contenido final y verificas que sea veraz.
5. Comprueba el resultado en el navegador (vista local o extensión “Live Server”, según tu entorno).

**Entregable de fase:** proyecto HTML/CSS/JS coherente, listo para versionar.

---

### Fase 2 — Control de versiones y Pull Request

1. **Issues:** si tu repositorio generó issues automáticamente, úsalos; si no, créalos manualmente desde `.github/ISSUE_TEMPLATE/` o copiando el contenido de los archivos en esa carpeta.
2. Desde el issue de la fase correspondiente, **crea una rama** con un nombre descriptivo, por ejemplo:  
   `feature/cv-bootstrap-template` o `feature/gh-pages-setup`.
3. **Convención de commits (Conventional Commits):** mensajes como:
   - `feat: añadir sección de experiencia laboral`
   - `fix: corregir enlaces rotos en el menú`
   - `docs: actualizar README con URL de Pages`
   - `style: ajustar tipografías en la cabecera`
4. Sube la rama (`git push`) y abre un **Pull Request** hacia `main`.
5. En la descripción del PR, enlaza el issue para que se cierre al fusionar:  
   **`Closes #N`** (sustituye `N` por el número del issue).
6. **Revisa** el diff, la vista previa si está disponible y los checks del repo; luego **merge** (preferiblemente *merge* explícito o *squash* según criterio del docente).

**Entregable de fase:** PR mergeado, issue cerrado automáticamente, historial de commits legible.

---

### Fase 3 — Despliegue en GitHub Pages

1. En el repositorio de GitHub: **Settings → Pages**.
2. Configura la **fuente** (por ejemplo **Deploy from a branch**):
   - Rama: suele ser `main` (o `gh-pages` si generas esa rama).
   - Carpeta: `/ (root)` o `/docs` si sirves el sitio desde `docs/`.
3. Guarda y espera a que el **despliegue** termine (puede tardar unos minutos).
4. Comprueba la **URL pública** (formato típico: `https://<usuario>.github.io/<repositorio>/`).
5. Si algo no carga (rutas CSS/JS), revisa rutas relativas y la carpeta configurada en Pages.

**Entregable de fase:** CV accesible por URL y enlace indicado donde lo pida el docente (foro, aula virtual, etc.).

---

## Convención de commits (referencia rápida)

Formato: `tipo: descripción breve en minúsculas`

| Tipo | Uso típico |
|------|------------|
| `feat` | Nueva sección o funcionalidad visible |
| `fix` | Corrección de errores |
| `docs` | README, comentarios de documentación |
| `style` | Formato, CSS, sin cambiar la lógica |
| `refactor` | Reorganización sin cambiar comportamiento |
| `chore` | Tareas auxiliares (config, dependencias) |

---

## Estructura útil de este repositorio plantilla

| Ruta | Propósito |
|------|-----------|
| `.github/ISSUE_TEMPLATE/` | Plantillas para crear issues de cada fase (o referencia si la automatización creó los issues). |
| `.github/workflows/auto-issues.yml` | Crea los issues iniciales la primera vez que se sube el repositorio (si Actions está habilitado). |

### GitHub Actions y permisos

- En repositorios nuevos (incluidos los que genera **GitHub Classroom**), confirma que **Actions** esté **habilitado** en *Settings → Actions → General*.
- El workflow usa `GITHUB_TOKEN` con permiso para **crear issues** (`issues: write`). En organizaciones con políticas restrictivas, un administrador puede tener que permitir workflows de lectura del repositorio.
- Si la creación automática falla, los alumnos pueden crear los issues **a mano** desde *Issues → New issue* y eligiendo las plantillas **Fase 1**, **Fase 2** y **Fase 3**, o copiando el contenido de los archivos en `.github/ISSUE_TEMPLATE/`.

---

## Recursos

- [BootstrapMade — plantillas Resume / CV](https://bootstrapmade.com/bootstrap-resume-cv-templates/)
- [Conventional Commits](https://www.conventionalcommits.org/)
- [Documentación GitHub Pages](https://docs.github.com/pages)

---

## Licencia del repositorio plantilla

Ajusta esta sección según la licencia que defina tu institución para el material docente. El contenido del CV del alumno es responsabilidad del estudiante y debe respetar la licencia de la plantilla elegida.

---

¡Mucho éxito: un buen CV web y un flujo Git impecable son señales profesionales claras para quien revise tu trabajo!

[03-pull-requests.md](https://github.com/user-attachments/files/35327777/03-pull-requests.md)
# Cómo hacer una Pull Request en GitHub

## 1. ¿Qué es una Pull Request?

Una **Pull Request (PR)** es una propuesta para integrar cambios de una rama en otra. Permite explicar qué se ha modificado, revisar las diferencias, comentar el código o la documentación y decidir si los cambios están preparados para incorporarse a la rama de destino.

En este repositorio utilizamos ramas independientes para trabajar en cada tarea y proponemos los cambios mediante Pull Requests hacia `main`.

## 2. Pasos para crear una Pull Request

### Paso 1. Comprobar el repositorio y la rama principal
Abre el repositorio en GitHub y comprueba cuál es su rama principal (en este proyecto, `main`). Antes de empezar, asegúrate de trabajar sobre la versión actualizada.

### Paso 2. Crear una rama nueva
En el selector de ramas, escribe un nombre descriptivo y crea la rama a partir de `main`. Ejemplos:
- `rama/conceptos-scrum`
- `rama/kanban-vs-scrum`
- `rama/pull-requests`
- `rama/basicos-git`

Una rama permite desarrollar una tarea sin modificar directamente la rama principal.

### Paso 3. Crear o editar el archivo
Añade el archivo Markdown correspondiente o modifica el documento existente. Utiliza títulos, listas, tablas y enlaces para que el contenido sea fácil de consultar.

### Paso 4. Hacer un commit
Un **commit** guarda un conjunto de cambios en el historial del repositorio. Escribe un mensaje breve y descriptivo, por ejemplo:
```text
docs: añadir conceptos clave de Scrum
```

### Paso 5. Publicar los cambios
Si trabajas desde Git en tu ordenador, sube la rama al repositorio remoto:
```bash
git push -u origin rama/conceptos-scrum
```
Si has editado desde la web de GitHub, selecciona la rama correcta al guardar los cambios.

### Paso 6. Abrir la Pull Request
En GitHub, entra en **Pull requests** y pulsa **New pull request**. Selecciona:
- **Base:** `main` (rama que recibirá los cambios).
- **Compare:** tu rama de trabajo (rama que contiene los cambios).

Escribe un título claro y una descripción que explique el objetivo, los archivos modificados y las comprobaciones realizadas. Para vincular la PR con su Issue, incluye:
```text
Closes #1
```
Sustituye el número por el de la Issue correspondiente. Cuando la PR se integre en la rama por defecto, GitHub cerrará automáticamente esa Issue.

### Paso 7. Revisar los cambios
Abre **Files changed** y comprueba el diff. La persona revisora debe verificar que los cambios corresponden al objetivo de la Issue, el contenido es correcto y completo, no hay modificaciones accidentales, y los enlaces y el formato Markdown funcionan. Debe dejar comentarios concretos cuando haya algo que mejorar.

El autor de una PR no debe aprobar su propia propuesta. La revisión debe realizarla otra persona con permisos suficientes.

### Paso 8. Aprobar y hacer Merge
Cuando los cambios estén listos, la persona revisora puede seleccionar **Review changes → Approve**. Después, una persona con permisos adecuados puede pulsar **Merge pull request** y confirmar la integración.

Si se solicitan cambios, el autor los corrige en la misma rama y los nuevos commits aparecen en la PR.

## 3. Flujo resumido

```text
Issue → Crear rama desde main → Editar archivo → Commit → Push
      → Abrir Pull Request (Closes #n) → Revisión en Files changed
      → Aprobación de otra persona → Merge hacia main → Issue cerrada
```

## 4. Ejemplo de descripción de Pull Request

```markdown
## Objetivo
Añadir la sección de conceptos clave de Scrum.

## Cambios realizados
- Explicación de Scrum y sus pilares.
- Descripción de Product Owner, Scrum Master y Developers.
- Resumen de los eventos y artefactos.

## Comprobaciones
- Revisada la ortografía y la estructura Markdown.
- Comprobados los enlaces.

Closes #1
```

## 5. Buenas prácticas
- Una PR debe centrarse en una tarea concreta.
- Utiliza nombres de rama y commits descriptivos.
- Mantén la PR pequeña y fácil de revisar.
- Explica el contexto y el motivo de los cambios.
- Responde a los comentarios y actualiza la rama cuando sea necesario.
- No apruebes tu propia PR: solicita una revisión independiente.
- Integra los cambios solo después de comprobar el diff y resolver los comentarios relevantes.

## Fuentes
- [GitHub Docs — About pull requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests).
- [GitHub Docs — Creating a pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request).
- [GitHub Docs — Reviewing proposed changes](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests).

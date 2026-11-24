[04-fundamentos-git.md](https://github.com/user-attachments/files/35327839/04-fundamentos-git.md)
# Fundamentos de Git

## 1. ¿Qué es Git?

**Git** es un sistema de control de versiones distribuido y gratuito. Permite registrar los cambios de los archivos a lo largo del tiempo, recuperar versiones anteriores y trabajar en paralelo mediante ramas.

Es distribuido porque cada persona que clona un repositorio obtiene una copia completa del historial del proyecto. Puede consultar el historial y realizar muchos cambios localmente sin necesitar conexión permanente al servidor.

Git y GitHub no son lo mismo:
- **Git** es la herramienta de control de versiones.
- **GitHub** es una plataforma web que aloja repositorios Git y añade colaboración, Issues, Pull Requests, revisiones y gestión de proyectos.

## 2. Conceptos fundamentales

### Repositorio
Es el espacio donde Git almacena los archivos del proyecto y su historial de versiones. Puede ser local (en el ordenador) o remoto (por ejemplo, en GitHub).

### Commit
Es una captura lógica de los cambios registrados en el historial. Cada commit tiene un identificador, un autor, una fecha y un mensaje que explica el cambio. Es recomendable que cada commit represente una modificación coherente.

### Rama (branch)
Es una línea de trabajo independiente. Permite desarrollar una funcionalidad o corregir un error sin alterar directamente la rama principal. Cuando el trabajo está listo, se puede integrar mediante un merge o una Pull Request.

### Working directory, staging area y repository
Git organiza el trabajo en tres zonas:
1. **Working directory:** archivos del proyecto que estás editando.
2. **Staging area (índice):** cambios seleccionados para incluir en el siguiente commit.
3. **Repository:** historial de commits guardados.

`git add` prepara cambios en staging; `git commit` los registra en el historial.

### Repositorio remoto
Es una versión del repositorio alojada en otro servidor, como GitHub. Se utiliza para compartir el trabajo y sincronizarlo entre personas y equipos.

## 3. Comandos básicos de Git

| Comando | Función |
|---|---|
| `git --version` | Comprueba la versión instalada |
| `git config --global user.name "Nombre"` | Configura el nombre del autor |
| `git config --global user.email "correo@example.com"` | Configura el correo del autor |
| `git init` | Inicializa un repositorio Git |
| `git clone URL` | Descarga una copia de un repositorio remoto |
| `git status` | Muestra el estado de los archivos y cambios |
| `git add archivo.md` | Añade un archivo al área de preparación |
| `git add .` | Prepara los cambios del directorio actual |
| `git commit -m "mensaje"` | Crea un commit con los cambios preparados |
| `git log --oneline` | Muestra el historial resumido |
| `git branch` | Lista las ramas locales |
| `git switch -c nombre-rama` | Crea una rama y cambia a ella |
| `git switch main` | Cambia a la rama main |
| `git merge nombre-rama` | Integra otra rama en la rama actual |
| `git remote -v` | Muestra los repositorios remotos |
| `git pull` | Descarga e integra cambios del remoto |
| `git push` | Envía commits locales al repositorio remoto |

## 4. Flujo de trabajo habitual

Ejemplo para crear una rama, modificar un documento y publicar los cambios:

```bash
# 1. Clonar el repositorio (solo la primera vez)
git clone https://github.com/Humanabled/KanBan-v1.git
cd KanBan-v1

# 2. Actualizar la rama principal
git switch main
git pull

# 3. Crear una rama para la tarea
git switch -c rama/conceptos-scrum

# 4. Comprobar los cambios
git status

# 5. Preparar el archivo
git add docs/01-conceptos-scrum.md

# 6. Guardar los cambios en el historial
git commit -m "docs: añadir conceptos clave de Scrum"

# 7. Publicar la rama en GitHub
git push -u origin rama/conceptos-scrum
```

Después de publicar la rama, se puede abrir una Pull Request en GitHub para solicitar su revisión e integración en `main`.

## 5. ¿Por qué es importante Git?
- **Historial:** permite saber qué cambió, quién lo hizo y cuándo.
- **Recuperación:** facilita volver a versiones anteriores.
- **Trabajo en paralelo:** las ramas permiten desarrollar tareas sin interferir directamente entre sí.
- **Colaboración:** varias personas pueden compartir cambios mediante repositorios remotos.
- **Trazabilidad:** los commits y las ramas ayudan a relacionar cambios con tareas e incidencias.

## 6. Git y GitHub dentro de este ejercicio

En esta actividad, Git permite registrar los cambios de cada documento Markdown. GitHub aloja el repositorio y facilita la colaboración mediante Issues, ramas, Pull Requests y revisiones. El flujo recomendado es: Issue → rama → edición → commit → push → Pull Request → revisión → merge.

## Fuentes
- [Git — documentación oficial](https://git-scm.com/doc).
- [Pro Git, libro gratuito](https://git-scm.com/book/es/v2).
- [GitHub Docs — Git basics](https://docs.github.com/en/get-started/using-git/about-git).

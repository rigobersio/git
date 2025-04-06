# Git

## ¿Qué es Git?

Git es un sistema de control de versiones distribuido creado por Linus Torvalds en 2005, diseñado para manejar proyectos de cualquier tamaño con velocidad y eficiencia. A diferencia de otros sistemas centralizados, Git permite que cada desarrollador tenga una copia completa del repositorio en su máquina local.

## Características principales

- **Distribuido**: Cada desarrollador tiene una copia completa del repositorio, permitiendo trabajo sin conexión.
- **Rápido**: Diseñado para proyectos grandes como el kernel de Linux, con operaciones locales muy eficientes.
- **Integridad**: Todo en Git tiene un checksum (SHA-1) que garantiza la integridad de los datos.
- **Branching**: Creación de ramas ligeras que facilitan el desarrollo paralelo y la experimentación.
- **Staging Area**: Área intermedia que permite preparar y revisar cambios antes de confirmarlos.

## Comandos básicos con ejemplos

### Inicializar un repositorio

```bash
# Crear un nuevo repositorio Git en el directorio actual
git init

# Verificar el estado después de la inicialización
git status
```

### Clonar un repositorio existente

```bash
# Clonar un repositorio remoto
git clone https://github.com/usuario/repositorio.git

# Clonar un repositorio específico en un directorio personalizado
git clone https://github.com/usuario/repositorio.git mi-directorio

# Clonar solo la rama principal con historial reciente (clon superficial)
git clone --depth=1 https://github.com/usuario/repositorio.git
```

### Gestión de cambios

```bash
# Ver el estado actual del repositorio
git status

# Añadir un archivo específico al área de preparación
git add archivo.txt

# Añadir todos los archivos modificados al área de preparación
git add .

# Añadir archivos de forma interactiva (seleccionando partes específicas)
git add -p

# Confirmar los cambios con un mensaje
git commit -m "Descripción clara del cambio realizado"

# Añadir y confirmar en un solo paso (solo para archivos ya rastreados)
git commit -am "Actualización de archivos existentes"
```

### Trabajar con ramas

```bash
# Ver todas las ramas locales
git branch

# Ver todas las ramas (locales y remotas)
git branch -a

# Crear una nueva rama
git branch nueva-funcionalidad

# Cambiar a una rama existente
git checkout nueva-funcionalidad

# Crear y cambiar a una nueva rama en un solo paso
git checkout -b nueva-funcionalidad

# Fusionar una rama con la rama actual
git merge otra-rama

# Eliminar una rama local después de fusionarla
git branch -d rama-completada
```

### Sincronización con repositorios remotos

```bash
# Ver los repositorios remotos configurados
git remote -v

# Añadir un nuevo repositorio remoto
git remote add origen https://github.com/usuario/repositorio.git

# Descargar cambios del repositorio remoto sin fusionar
git fetch origen

# Descargar cambios y fusionarlos con la rama actual
git pull origen main

# Enviar cambios locales al repositorio remoto
git push origen main

# Enviar una rama local al repositorio remoto por primera vez
git push -u origen nueva-rama
```

### Revisión del historial

```bash
# Ver el historial de commits
git log

# Ver historial en formato compacto y visual
git log --oneline --graph --decorate

# Ver cambios detallados de un commit específico
git show abc123

# Ver cambios entre dos commits
git diff abc123..def456

# Ver cambios en archivos preparados (staged)
git diff --staged
```

### Deshacer cambios

```bash
# Descartar cambios en un archivo específico (no preparado)
git checkout -- archivo.txt

# Deshacer el último commit manteniendo los cambios en el área de preparación
git reset --soft HEAD~1

# Deshacer el último commit y descartar los cambios
git reset --hard HEAD~1

# Crear un nuevo commit que revierte los cambios de un commit anterior
git revert abc123

# Modificar el mensaje del último commit
git commit --amend -m "Nuevo mensaje para el último commit"

# Añadir cambios al último commit
git add archivo-olvidado.txt
git commit --amend --no-edit
```

### Etiquetas (versiones)

```bash
# Crear una etiqueta ligera
git tag v1.0.0

# Crear una etiqueta anotada (con mensaje)
git tag -a v1.0.0 -m "Versión 1.0.0 - Primera versión estable"

# Listar todas las etiquetas
git tag

# Ver información detallada de una etiqueta
git show v1.0.0

# Enviar etiquetas al repositorio remoto
git push origen --tags
```

### Casos de uso comunes

```bash
# Guardar cambios temporalmente sin hacer commit
git stash save "Trabajo en progreso para la funcionalidad X"

# Listar cambios guardados
git stash list

# Recuperar el último cambio guardado
git stash pop

# Ignorar cambios en un archivo rastreado temporalmente
git update-index --skip-worktree archivo.txt

# Volver a rastrear cambios en el archivo
git update-index --no-skip-worktree archivo.txt

# Buscar texto en todos los archivos del repositorio
git grep "texto a buscar"

# Ver quién modificó cada línea de un archivo y en qué commit
git blame archivo.txt
```

## Flujo de trabajo típico

1. Modificar archivos en el directorio de trabajo
2. Preparar los archivos, añadiéndolos al área de preparación (staging)
3. Confirmar los cambios, lo que toma los archivos tal y como están en el área de preparación y almacena esa instantánea de manera permanente en el repositorio Git
4. Sincronizar con repositorios remotos según sea necesario

## Recursos adicionales

- [Documentación oficial de Git](https://git-scm.com/doc)
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
- [Pro Git Book](https://git-scm.com/book/es/v2) - Libro completo disponible en español


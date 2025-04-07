# Git

## ¿Qué es Git?

Git es un sistema de control de versiones distribuido creado por Linus Torvalds en 2005, diseñado para manejar proyectos de cualquier tamaño con velocidad y eficiencia. A diferencia de otros sistemas centralizados, Git permite que cada desarrollador tenga una copia completa del repositorio en su máquina local.

## Características principales

- **Distribuido**: Cada desarrollador tiene una copia completa del repositorio, permitiendo trabajo sin conexión.
- **Rápido**: Diseñado para proyectos grandes como el kernel de Linux, con operaciones locales muy eficientes.
- **Integridad**: Todo en Git tiene un checksum (SHA-1) que garantiza la integridad de los datos.
- **Branching**: Creación de ramas ligeras que facilitan el desarrollo paralelo y la experimentación.
- **Staging Area**: Área intermedia que permite preparar y revisar cambios antes de confirmarlos.

 edit## Comandos básicos con ejemplos

### ¿Qué es un comando Git?

Un comando Git es una instrucción que se envía a Git a través de la terminal o línea de comandos para realizar una acción específica en el repositorio. Git utiliza una estructura de comandos consistente que sigue este patrón general:

```
git [comando] [opciones] [argumentos]
```

Donde:
- **git**: Es el programa principal que invocamos.
- **comando**: Es la acción específica que queremos realizar (como `init`, `add`, `commit`, etc.).
- **opciones**: Son modificadores que cambian el comportamiento del comando (comienzan con guiones, como `-m` o `--global`).
- **argumentos**: Son los datos sobre los que actúa el comando (como nombres de archivos, mensajes, etc.).

Para interactuar con Git:

1. Abre tu terminal o línea de comandos (PowerShell, CMD, Terminal, etc.).
2. Navega hasta el directorio de tu proyecto usando comandos como `cd ruta/del/proyecto`.
3. Ejecuta comandos Git escribiéndolos y presionando Enter.

### Inicializar un repositorio

```bash
# Crear un nuevo repositorio Git en el directorio actual
git init
# ↑     ↑
# │     └── Comando para inicializar un nuevo repositorio
# └──────── Programa Git

# Verificar el estado después de la inicialización
git status
# ↑     ↑
# │     └── Comando para mostrar el estado actual del repositorio
# └──────── Programa Git
```

### Clonar un repositorio existente

```bash
# Clonar un repositorio remoto
git clone https://github.com/usuario/repositorio.git
# ↑     ↑     ↑
# │     │     └── URL del repositorio remoto (argumento)
# │     └──────── Comando para copiar un repositorio existente
# └────────────── Programa Git

# Clonar un repositorio específico en un directorio personalizado
git clone https://github.com/usuario/repositorio.git mi-directorio
#                                                    ↑
#                                                    └── Nombre del directorio local donde se clonará (argumento adicional)

# Clonar solo la rama principal con historial reciente (clon superficial)
git clone --depth=1 https://github.com/usuario/repositorio.git
#         ↑
#         └── Opción que limita la profundidad del historial a 1 commit
```

### Gestión de cambios

```bash
# Ver el estado actual del repositorio
git status
# ↑     ↑
# │     └── Comando para mostrar archivos modificados, preparados y sin seguimiento
# └──────── Programa Git

# Añadir un archivo específico al área de preparación
git add archivo.txt
# ↑   ↑    ↑
# │   │    └── Nombre del archivo a añadir (argumento)
# │   └─────── Comando para añadir cambios al área de preparación
# └─────────── Programa Git

# Añadir todos los archivos modificados al área de preparación
git add .
#        ↑
#        └── El punto representa todos los archivos en el directorio actual (argumento)

# Añadir archivos de forma interactiva (seleccionando partes específicas)
git add -p
#        ↑
#        └── Opción para modo interactivo (patch) que permite seleccionar partes específicas

# Confirmar los cambios con un mensaje
git commit -m "Descripción clara del cambio realizado"
# ↑      ↑  ↑  ↑
# │      │  │  └── Mensaje del commit entre comillas (argumento)
# │      │  └───── Opción para especificar un mensaje
# │      └──────── Comando para confirmar cambios en el repositorio
# └─────────────── Programa Git

# Añadir y confirmar en un solo paso (solo para archivos ya rastreados)
git commit -am "Actualización de archivos existentes"
#          ↑
#          └── Combinación de opciones: -a (añadir archivos modificados) y -m (mensaje)
```

### Trabajar con ramas

```bash
# Ver todas las ramas locales
git branch
# ↑     ↑
# │     └── Comando para gestionar ramas (sin argumentos lista las ramas locales)
# └──────── Programa Git

# Ver todas las ramas (locales y remotas)
git branch -a
#         ↑
#         └── Opción para mostrar todas las ramas (all)

# Crear una nueva rama
git branch nueva-funcionalidad
#         ↑
#         └── Nombre de la nueva rama (argumento)

# Cambiar a una rama existente
git checkout nueva-funcionalidad
# ↑       ↑      ↑
# │       │      └── Nombre de la rama a la que cambiar (argumento)
# │       └──────── Comando para cambiar entre ramas o restaurar archivos
# └──────────────── Programa Git

# Crear y cambiar a una nueva rama en un solo paso
git checkout -b nueva-funcionalidad
#           ↑  ↑
#           │  └── Nombre de la nueva rama (argumento)
#           └───── Opción para crear una rama (-b de branch)

# Fusionar una rama con la rama actual
git merge otra-rama
# ↑     ↑     ↑
# │     │     └── Nombre de la rama a fusionar con la rama actual (argumento)
# │     └──────── Comando para combinar cambios de otra rama
# └────────────── Programa Git

# Eliminar una rama local después de fusionarla
git branch -d rama-completada
#         ↑  ↑
#         │  └── Nombre de la rama a eliminar (argumento)
#         └───── Opción para eliminar (-d de delete)
```

### Sincronización con repositorios remotos

```bash
# Ver los repositorios remotos configurados
git remote -v
# ↑      ↑   ↑
# │      │   └── Opción para modo detallado (verbose) que muestra URLs
# │      └─────── Comando para gestionar repositorios remotos
# └────────────── Programa Git

# Añadir un nuevo repositorio remoto
git remote add origen https://github.com/usuario/repositorio.git
#        ↑   ↑      ↑
#        │   │      └── URL del repositorio remoto (argumento)
#        │   └──────── Nombre que le damos al remoto (argumento)
#        └──────────── Subcomando para añadir un remoto

# Descargar cambios del repositorio remoto sin fusionar
git fetch origen
# ↑     ↑     ↑
# │     │     └── Nombre del repositorio remoto (argumento)
# │     └──────── Comando para descargar objetos y referencias
# └────────────── Programa Git

# Descargar cambios y fusionarlos con la rama actual
git pull origen main
# ↑    ↑      ↑
# │    │      └── Nombre de la rama remota a descargar (argumento)
# │    └──────── Nombre del repositorio remoto (argumento)
# └───────────── Comando para descargar y fusionar cambios (fetch + merge)

# Enviar cambios locales al repositorio remoto
git push origen main
# ↑    ↑      ↑
# │    │      └── Nombre de la rama a enviar (argumento)
# │    └──────── Nombre del repositorio remoto (argumento)
# └───────────── Comando para enviar cambios locales al remoto

# Enviar una rama local al repositorio remoto por primera vez
git push -u origen nueva-rama
#       ↑  ↑      ↑
#       │  │      └── Nombre de la rama local a enviar (argumento)
#       │  └──────── Nombre del repositorio remoto (argumento)
#       └─────────── Opción para establecer seguimiento (upstream) entre ramas
```

### Revisión del historial

```bash
# Ver el historial de commits
git log
# ↑   ↑
# │   └── Comando para mostrar el historial de commits
# └─────── Programa Git

# Ver historial en formato compacto y visual
git log --oneline --graph --decorate
#      ↑         ↑       ↑
#      │         │       └── Opción para mostrar referencias (ramas, tags)
#      │         └─────────── Opción para mostrar el historial como un gráfico ASCII
#      └─────────────────────── Opción para mostrar cada commit en una sola línea

# Ver cambios detallados de un commit específico
git show abc123
# ↑    ↑    ↑
# │    │    └── Identificador (hash) del commit a mostrar (argumento)
# │    └──────── Comando para mostrar detalles de objetos Git
# └────────────── Programa Git

# Ver cambios entre dos commits
git diff abc123..def456
# ↑    ↑    ↑
# │    │    └── Rango de commits a comparar (argumento)
# │    └──────── Comando para mostrar diferencias entre commits
# └────────────── Programa Git

# Ver cambios en archivos preparados (staged)
git diff --staged
#       ↑
#       └── Opción para comparar el área de preparación con el último commit
```

### Deshacer cambios

```bash
# Descartar cambios en un archivo específico (no preparado)
git checkout -- archivo.txt
# ↑        ↑  ↑
# │        │  └── Nombre del archivo a restaurar (argumento)
# │        └───── Separador que indica que lo siguiente son archivos, no ramas
# └────────────── Comando para cambiar entre ramas o restaurar archivos

# Deshacer el último commit manteniendo los cambios en el área de preparación
git reset --soft HEAD~1
# ↑     ↑      ↑
# │     │      └── Referencia al commit anterior al HEAD (argumento)
# │     └──────── Opción que mantiene los cambios en el área de preparación
# └────────────── Comando para mover HEAD a otro commit

# Deshacer el último commit y descartar los cambios
git reset --hard HEAD~1
#        ↑      ↑
#        │      └── Referencia al commit anterior al HEAD (argumento)
#        └──────── Opción que descarta todos los cambios (¡peligroso!)

# Crear un nuevo commit que revierte los cambios de un commit anterior
git revert abc123
# ↑      ↑
# │      └── Identificador (hash) del commit a revertir (argumento)
# └──────── Comando para crear un nuevo commit que deshace cambios

# Modificar el mensaje del último commit
git commit --amend -m "Nuevo mensaje para el último commit"
#         ↑       ↑  ↑
#         │       │  └── Nuevo mensaje para el commit (argumento)
#         │       └───── Opción para especificar un mensaje
#         └─────────── Opción para modificar el último commit

# Añadir cambios al último commit
git add archivo-olvidado.txt
# ↑   ↑    ↑
# │   │    └── Archivo a añadir al área de preparación (argumento)
# │   └──────── Comando para añadir cambios
# └────────────── Programa Git

git commit --amend --no-edit
#         ↑       ↑
#         │       └── Opción para mantener el mensaje de commit original
#         └─────────── Opción para modificar el último commit
```

### Etiquetas (versiones)

```bash
# Crear una etiqueta ligera
git tag v1.0.0
# ↑   ↑   ↑
# │   │   └── Nombre de la etiqueta (argumento)
# │   └─────── Comando para gestionar etiquetas
# └─────────── Programa Git

# Crear una etiqueta anotada (con mensaje)
git tag -a v1.0.0 -m "Versión 1.0.0 - Primera versión estable"
#      ↑  ↑       ↑  ↑
#      │  │       │  └── Mensaje descriptivo de la etiqueta (argumento)
#      │  │       └───── Opción para especificar un mensaje
#      │  └─────────── Nombre de la etiqueta (argumento)
#      └───────────── Opción para crear una etiqueta anotada (con metadatos)

# Listar todas las etiquetas
git tag
# ↑   ↑
# │   └── Comando para listar etiquetas cuando se usa sin argumentos
# └─────── Programa Git

# Ver información detallada de una etiqueta
git show v1.0.0
# ↑    ↑    ↑
# │    │    └── Nombre de la etiqueta a mostrar (argumento)
# │    └──────── Comando para mostrar detalles de objetos Git
# └────────────── Programa Git

# Enviar etiquetas al repositorio remoto
git push origen --tags
# ↑    ↑      ↑
# │    │      └── Opción para enviar todas las etiquetas
# │    └──────── Nombre del repositorio remoto (argumento)
# └───────────── Comando para enviar objetos al repositorio remoto
```

### Casos de uso comunes

```bash
# Guardar cambios temporalmente sin hacer commit
git stash save "Trabajo en progreso para la funcionalidad X"
# ↑     ↑     ↑    ↑
# │     │     │    └── Mensaje descriptivo para identificar el stash (argumento)
# │     │     └──────── Subcomando para guardar cambios
# │     └─────────────── Comando para gestionar el almacenamiento temporal
# └─────────────────────── Programa Git

# Listar cambios guardados
git stash list
# ↑     ↑     ↑
# │     │     └── Subcomando para listar los stashes guardados
# │     └──────── Comando para gestionar el almacenamiento temporal
# └────────────── Programa Git

# Recuperar el último cambio guardado
git stash pop
# ↑     ↑     ↑
# │     │     └── Subcomando para aplicar y eliminar el último stash
# │     └──────── Comando para gestionar el almacenamiento temporal
# └────────────── Programa Git

# Ignorar cambios en un archivo rastreado temporalmente
git update-index --skip-worktree archivo.txt
# ↑     ↑          ↑             ↑
# │     │          │             └── Archivo a ignorar (argumento)
# │     │          └─────────────── Opción para ignorar cambios en el archivo
# │     └────────────────────────── Comando para modificar el índice de Git
# └────────────────────────────────── Programa Git

# Volver a rastrear cambios en el archivo
git update-index --no-skip-worktree archivo.txt
#                 ↑                 ↑
#                 │                 └── Archivo a volver a rastrear (argumento)
#                 └───────────────────── Opción para volver a rastrear cambios

# Buscar texto en todos los archivos del repositorio
git grep "texto a buscar"
# ↑    ↑    ↑
# │    │    └── Patrón de texto a buscar (argumento)
# │    └──────── Comando para buscar en el contenido de los archivos
# └────────────── Programa Git

# Ver quién modificó cada línea de un archivo y en qué commit
git blame archivo.txt
# ↑     ↑     ↑
# │     │     └── Archivo a analizar (argumento)
# │     └──────── Comando para mostrar quién modificó cada línea
# └────────────── Programa Git
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


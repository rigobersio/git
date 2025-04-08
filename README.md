# Git - Guía Básica para Principiantes

## ¿Qué es Git?

Git es un sistema de control de versiones que permite guardar el historial de cambios de tus archivos y trabajar en equipo de manera eficiente. Fue creado por Linus Torvalds en 2005 y es la herramienta estándar para desarrollo de software.

## Características principales

- **Distribuido**: Cada desarrollador tiene una copia completa del repositorio.
- **Rápido**: Operaciones locales muy eficientes.
- **Branching**: Permite crear ramas para trabajar en paralelo sin afectar el código principal.
- **Staging Area**: Área intermedia para preparar y revisar cambios antes de confirmarlos.

## Comandos básicos con ejemplos

### ¿Qué es un comando Git?

Un comando Git es una instrucción que se envía a Git a través de la terminal siguiendo este patrón:

```
git [comando] [opciones] [argumentos]
```

Donde:
- **git**: El programa principal.
- **comando**: La acción a realizar (como `init`, `add`, `commit`).
- **opciones**: Modificadores con guiones (como `-m` o `--global`).
- **argumentos**: Datos sobre los que actúa el comando (archivos, mensajes, etc.).

Para usar Git:

1. Abre tu terminal (PowerShell, CMD, Terminal).
2. Navega a tu proyecto con `cd ruta/del/proyecto`.
3. Ejecuta comandos Git.

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

# Clonar un repositorio en un directorio personalizado
git clone https://github.com/usuario/repositorio.git mi-directorio
#                                                    ↑
#                                                    └── Nombre del directorio local donde se clonará
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
# │   │    └── Nombre del archivo a añadir
# │   └─────── Comando para añadir cambios
# └─────────── Programa Git

# Añadir todos los archivos modificados al área de preparación
git add .
#        ↑
#        └── El punto representa todos los archivos en el directorio actual

# Confirmar los cambios con un mensaje
git commit -m "Descripción del cambio realizado"
# ↑      ↑  ↑  ↑
# │      │  │  └── Mensaje del commit entre comillas
# │      │  └───── Opción para especificar un mensaje
# │      └──────── Comando para confirmar cambios
# └─────────────── Programa Git

# Añadir y confirmar en un solo paso (solo para archivos ya rastreados)
git commit -am "Actualización de archivos existentes"
#          ↑
#          └── Combinación de opciones: -a (añadir) y -m (mensaje)
```

### Trabajar con ramas

```bash
# Ver todas las ramas locales
git branch
# ↑     ↑
# │     └── Comando para gestionar ramas
# └──────── Programa Git

# Crear y cambiar a una nueva rama en un solo paso
git checkout -b nueva-funcionalidad
#           ↑  ↑
#           │  └── Nombre de la nueva rama
#           └───── Opción para crear una rama (-b)

# Cambiar a una rama existente
git checkout main
# ↑       ↑     ↑
# │       │     └── Nombre de la rama a la que cambiar
# │       └─────── Comando para cambiar entre ramas
# └─────────────── Programa Git

# Fusionar una rama con la rama actual
git merge otra-rama
# ↑     ↑     ↑
# │     │     └── Nombre de la rama a fusionar
# │     └──────── Comando para combinar cambios
# └────────────── Programa Git

# Eliminar una rama después de fusionarla
git branch -d rama-completada
#         ↑  ↑
#         │  └── Nombre de la rama a eliminar
#         └───── Opción para eliminar (-d)
```

### Sincronización con repositorios remotos

```bash
# Ver los repositorios remotos configurados
git remote -v
# ↑      ↑   ↑
# │      │   └── Opción para mostrar URLs
# │      └─────── Comando para gestionar repositorios remotos
# └────────────── Programa Git

# Descargar cambios y fusionarlos con la rama actual
git pull origin main
# ↑    ↑      ↑
# │    │      └── Nombre de la rama remota
# │    └──────── Nombre del repositorio remoto
# └───────────── Comando para descargar y fusionar cambios

# Enviar cambios locales al repositorio remoto
git push origin main
# ↑    ↑      ↑
# │    │      └── Nombre de la rama a enviar
# │    └──────── Nombre del repositorio remoto
# └───────────── Comando para enviar cambios
```

### Revisión del historial

```bash
# Ver el historial de commits
git log
# ↑   ↑
# │   └── Comando para mostrar el historial de commits
# └─────── Programa Git

# Ver historial en formato compacto y visual
git log --oneline --graph
#      ↑         ↑
#      │         └── Opción para mostrar el historial como un gráfico
#      └─────────── Opción para mostrar cada commit en una sola línea

# Ver cambios en archivos preparados (staged)
git diff --staged
#       ↑
#       └── Opción para ver cambios preparados
```

### Deshacer cambios

```bash
# Descartar cambios en un archivo específico (no preparado)
git checkout -- archivo.txt
# ↑        ↑  ↑
# │        │  └── Nombre del archivo a restaurar
# │        └───── Separador para indicar archivos
# └────────────── Comando para restaurar archivos

# Deshacer el último commit manteniendo los cambios
git reset --soft HEAD~1
# ↑     ↑      ↑
# │     │      └── Referencia al commit anterior
# │     └──────── Opción que mantiene los cambios
# └────────────── Comando para deshacer commits

# Modificar el mensaje del último commit
git commit --amend -m "Nuevo mensaje para el último commit"
#         ↑       ↑  ↑
#         │       │  └── Nuevo mensaje para el commit
#         │       └───── Opción para especificar mensaje
#         └─────────── Opción para modificar el último commit
```

## Flujo de trabajo básico

1. Modificar archivos en tu proyecto
2. Revisar cambios con `git status`
3. Añadir cambios al área de preparación con `git add`
4. Confirmar cambios con `git commit -m "mensaje"`
5. Sincronizar con el repositorio remoto usando `git pull` y `git push`

## Recursos para aprender más

- [Documentación oficial de Git](https://git-scm.com/doc)
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
- [Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials)


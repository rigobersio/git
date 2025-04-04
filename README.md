# Git

## ¿Qué es Git?

Git es un sistema de control de versiones distribuido creado por Linus Torvalds en 2005, diseñado para manejar proyectos de cualquier tamaño con velocidad y eficiencia. A diferencia de otros sistemas centralizados, Git permite que cada desarrollador tenga una copia completa del repositorio en su máquina local.

## Características principales

- **Distribuido**: Cada desarrollador tiene una copia completa del repositorio, permitiendo trabajo sin conexión.
- **Rápido**: Diseñado para proyectos grandes como el kernel de Linux, con operaciones locales muy eficientes.
- **Integridad**: Todo en Git tiene un checksum (SHA-1) que garantiza la integridad de los datos.
- **Branching**: Creación de ramas ligeras que facilitan el desarrollo paralelo y la experimentación.
- **Staging Area**: Área intermedia que permite preparar y revisar cambios antes de confirmarlos.

## Comandos básicos

```bash
# Inicializar un repositorio
git init

# Clonar un repositorio existente
git clone <url>

# Añadir cambios al área de preparación
git add <archivo>

# Confirmar cambios
git commit -m "mensaje descriptivo"

# Ver el estado actual
git status

# Ver historial de commits
git log

# Crear una nueva rama
git branch <nombre-rama>

# Cambiar a otra rama
git checkout <nombre-rama>

# Fusionar ramas
git merge <nombre-rama>
```

## Flujo de trabajo típico

1. Modificar archivos en el directorio de trabajo
2. Preparar los archivos, añadiéndolos al área de preparación (staging)
3. Confirmar los cambios, lo que toma los archivos tal y como están en el área de preparación y almacena esa instantánea de manera permanente en el repositorio Git


# Commits con Fecha Personalizada en Git

## Comandos complejos para manipulación de fechas

Git permite modificar las fechas de autor y de commit mediante variables de entorno. El siguiente comando combina múltiples operaciones para crear un commit con una fecha específica y subirlo al repositorio remoto:

```bash
git add . && GIT_AUTHOR_DATE="2025-03-01T17:33:00" GIT_COMMITTER_DATE="2025-03-01T17:33:00" git commit -m "mensaje" && git push -u origin main
```

### Explicación por partes:

1. `git add .` - Añade todos los archivos modificados al área de preparación (staging)

2. `GIT_AUTHOR_DATE="2025-03-01T17:33:00"` - Establece la fecha de autoría del commit (cuándo se escribieron los cambios)

3. `GIT_COMMITTER_DATE="2025-03-01T17:33:00"` - Establece la fecha de confirmación del commit (cuándo se registró en el repositorio)

4. `git commit -m "mensaje"` - Crea el commit con el mensaje especificado y las fechas personalizadas

5. `git push -u origin main` - Sube los cambios a la rama principal del repositorio remoto

<!-- -->

- Git permite hacer commit con fechas que no sean cronológicamente lineales
- Existen algunos repositorios con proteciones, como por ejemplo, GitHub que por defecto no permite retroceder cronológicamente

<!-- Nota sobre riesgos -->
- Editar fechas de commits ya publicados puede causar inconsistencias en el historial
- Hacer nuevos commits con fechas anteriores al último commit puede:
  * Confundir el orden cronológico en GitHub
  * Afectar herramientas que dependen del historial lineal
  * Generar conflictos en pull requests
  * Requerir force push (--force) que puede afectar a otros colaboradores


## en caso de cometer este error

git log --oneline para obtener los hash del los commit de manera abreviada

Mantener los cambios en el área de trabajo (working directory):

conservar los cambios realizados después del commit seleccionado en tu directorio de trabajo para revisarlos o modificarlos, utiliza:

bash

git reset --mixed <commit-hash>


Este comando restablece la rama actual al commit especificado y deja los cambios posteriores sin confirmar en el área de trabajo.

<!-- Esta sección no especifica claramente cuál es "este error" mencionado en el título. -->
<!-- La estructura es inconsistente: mezcla texto plano con lo que parece ser un bloque de código sin formato adecuado. -->
<!-- Hay un error gramatical en "del los commit", debería ser "de los commits". -->
<!-- El término "rama" se usa aquí, pero en otras partes del repositorio se usa "branch", lo que crea inconsistencia terminológica. -->

## Alternativa más segura

Para modificar commits recientes sin alterar el historial compartido:

```bash
git commit --amend --reset-author --date="YYYY-MM-DDThh:mm:ss"
```

Este método solo funciona para el último commit y es más seguro para repositorios colaborativos.



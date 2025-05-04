# Branch & Merge en Git

1. Crear un nuevo branch: `git branch <nombre-branch>`
    a. Para crear y cambiar inmediatamente al nuevo branch: `git checkout -b <nombre-branch>`

2. Ver todos los branches: `git branch`
    a. Adicionalmente, con `git branch -a` se pueden visualizar también los branches remotos

3. Eliminar un branch: `git branch -d <nombre-branch>`
    a. Es importante destacar que `-d` solo elimina branches que ya han sido mergeados. Para forzar la eliminación de un branch no mergeado se usa `-D`

4. Para realizar un merge:
	a. Hacer commit para finalizar los cambios en el branch experimental
	b. Cambiar al branch destino con `git checkout <branch-destino>`
	c. Merge: `git merge <nombre-branch-experimental>`
    d. En caso de conflictos, una de las mejores alternativas para resolverlos es utilizar la interfaz gráfica de un editor de código (por ejemplo VS Code)

5. Después de un merge, los dos branches son virtualmente idénticos.
   Incluso un `git add` no marcará diferencias entre ellos. Las diferencias
   comenzarán a aparecer cuando se realice un nuevo commit en alguno de los branches.

<!-- Después del merge, ambos branches contienen los mismos commits, pero siguen siendo branches independientes que pueden divergir con nuevos commits -->

6. De manera similar, cuando se crea un nuevo branch es necesario
   realizar un commit para que exista una diferencia visible entre los branches.

<!-- Un nuevo branch hereda todos los commits del branch de origen, y solo diverge cuando se hacen nuevos commits en él -->

7. Respecto a GitHub:
	a. Luego de un merge se crea un commit automáticamente
	b. Por lo tanto, `git status` no mostrará cambios pendientes
	c. Es recomendable ejecutar `git push -u origin main` (o el nombre
	   correspondiente del branch) para sincronizar con el repositorio remoto

<!-- El commit automático ocurre cuando se hace el merge a través de la interfaz de GitHub (pull request) o algunos editores de código modernos -->

7.1. Como alternativa usual al punto 4 (flujo de trabajo en equipo):
    a. Cuando se trabaja en equipo, cada actualización se desarrolla en un branch separado. Al finalizar el desarrollo, se realiza una solicitud de cambios o pull request para incorporar las modificaciones.
    
    b. Para evitar errores y asegurarse de que el branch de desarrollo no presente conflictos con el branch destino, es muy conveniente realizar una revisión previa de manera local con un merge.
    
    c. Para esto, primero se debe actualizar el branch principal con:
       `git pull origin main`
    
    d. Luego, estando posicionado en el branch de desarrollo, incorporar los cambios del branch principal:
       `git merge main`
    
    e. Los editores de código modernos ofrecen interfaces interactivas para resolver cualquier tipo de conflicto que pueda surgir.

8. Después de crear un nuevo branch y realizar el primer commit,
   cualquier cambio pendiente (sin confirmar con otro commit) impedirá cambiar
   a otro branch, incluso utilizando `git checkout`

8.1. Para solucionar este problema se puede usar:
    a. `git stash save "mensaje descriptivo"`
       # Guarda temporalmente los cambios pendientes en una pila
    b. `git checkout <otro-branch>`
       # Ahora es posible cambiar de branch sin problemas
    c. `git stash pop`
       # Recupera los cambios guardados cuando vuelvas al branch original

8.2. Otra alternativa es usar:
    a. `git checkout --force <otro-branch>`
       # Cambia de branch descartando los cambios pendientes (¡cuidado!). En este caso los cambios no guardados se perderán permanentemente.

9. Es posible clonar específicamente un branch del repositorio GitHub:
	a. Para realizar esta acción: `git clone -b <nombre-branch> <url-repositorio>`
	b. Esto descargará únicamente el branch especificado, lo que puede ser útil cuando solo se necesita trabajar con una parte específica del proyecto

<!-- Sugerencia: Considerar añadir una sección detallada sobre resolución de conflictos durante el merge, incluyendo ejemplos prácticos -->
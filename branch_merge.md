# branch --> merge

1. hacer un nuevo branch: git branch <nombre-branch>
    a. para crear y cambiar inmediatamente a la nueva branch: git checkout -b <nombre-branch>

2. ver todas las ramas: git branch
    a. adicionalmente con: git branch -a se pueden incluir las ramas remotas

3. eliminar branch: git branch -d <nombre-branch>
    a. es necesario mencionar que `-d` solo elimina ramas que ya han sido fusionadas. Para forzar la eliminación de una rama no fusionada se usa `-D`

4. para hacer un merge:
	a. hacer commit para finalizar la branch experimental
	b. cambiar a la branch  madre con git checkout <branch-madre>
	c. merge: git merge <nombre-branch-experimental
    d. en el caso de que se produzca un conflicto una de las mejores alternativas para resolverlos es en el editor de código (por ejemplo VS Code) ocupando la interface gráfica

5. después de un merge las 2 ramas son virtualmente iguales
incluso un git add no marca diferencia. la diferencia empieza con
un commit.

<!-- después del merge, ambas ramas contienen los mismos commits, pero siguen siendo ramas independientes que pueden divergir con nuevos commits -->

6. de la misma forma cuando se crea una nueva branch es necesario
hacer un commit para marcar diferencia.

<!-- una nueva rama hereda todos los commits de la rama de origen, y solo diverge cuando se hacen nuevos commits en ella -->

7. respecto a GitHub:
	a. luego de un merge se crea un commit en automático
	b. entonces un git status no muestra cambios pendientes
	c. es recomendable hacer un git push -u origin main (o como
	se llame la rama)

<!-- el commit automático ocurre cuando se hace el merge a través de la interfaz de GitHub (pull request) o algunos editores de código modernos. -->

7.1. como alternativa usual a punto 4
    a. cuando se trabaja en equipo cada actualización se desarrolla en una rama y al finalizar el desarrollo se realiza una solicitud de cambio o pull request para incorporar los cambios. Para evitar errores y asegurarse de que la rama de desarrollo no sea conflictiva respecto a la rama a la que se incorporarán los cambios es muy conveniente hacer una revisión de manera local con un <merge>. Para hacer esto se necesita tener actualizada la rama principal con <git pull origin main> y luego llevar cualquier actualización a la rama de desarrollo con <git merge main> (para hacer esto hay que estar posicionado en la rama de desarrollo). Los editores de código modernos ofrecen interfaces interactivas para corregir cualquier tipo de conflicto.

8. luego de que se crea una nueva branch y se hace el primer commit
cualquier cambio pendiente (sin otro commit) impedirá cambiar a otra
branch aun haciendo git checkout

8.1. para solucionar esto se puede usar:
    a. git stash save "mensaje descriptivo"
       # guarda temporalmente los cambios pendientes en una pila
    b. git checkout <otra-rama>
       # ahora es posible cambiar de rama sin problemas
    c. git stash pop
       # recupera los cambios guardados cuando vuelvas a la rama original

8.2. otra alternativa es usar:
    a. git checkout --force <otra-rama>
       # cambia de rama descartando los cambios pendientes (¡cuidado!). En este caso los cambios no guardados se perderán.

9. es posible clonar específicamente una branch del repositorio GitHub
	a. para realizar esta acción: git clone -b <nombre-rama> <url-repositorio>

<!-- Sugerencia: Considerar añadir una sección sobre resolución de conflictos durante el merge -->
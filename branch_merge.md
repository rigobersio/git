# branch --> merge

1. hacer un nuevo branch: git branch <nombre-branch>

2. ver todos: git branch

3. eliminar branch: git branch -d <nombre-branch>

4. para hacer un merge:
	a. hacer commit para finalizar la branch experimental
	b. cambiar a la branch  madre con git checkout <branch-madre>
	c. merge: git merge <nombre-branch-experimental>

5. después de un marge las 2 ramas son virtualmente iguales
incluso un git add no marca diferencia. la diferencia empieza con
un commit.

6. de la misma forma cuando se crea una nueva branch es necesario
hacer un commit para marcar diferencia.

7. respecto a GitHub:
	a. luego de un merge se crea un commit en automático
	b. entonces un git status no muestra cambios pendientes
	c. es recomendable hacer un git push -u origin main(o como
	se llame la rama)

7.1. como alternativa usual a punto 4
    a. cuando se trabaja en equipo cada actualización se desarrolla en una rama y al finalizar el desarrollo se realiza una solicitud de cambio o pull request para incorporar los cambios. Para evitar errores y asegurarse de que la rama de desarrollo no sea conflictiva respecto a la rama a la que se incorporaran los cambios es muy conveniente hacer una revision de manera local con un <merge>. para hacer esto se necesita tener actualizada la rama principal con <git pull origin main> y luego llevar cualquier actualización a la rama de desarrollo con <git merge main> (para hacer esto hay que estar posesionado en la rama de desarrollo). Los editores de código modernos ofrecen interfaces interactivas para corregir cualquier tipo de conflicto

8. luego de que se crea una nueva branch y se hace el primer commit
cualquier cambio pendiente (sin otro commit) impedirá cambiar a otra
branch aun haciendo git checkout

9. es posible clonar especificamente una branch del repositorio GitHub
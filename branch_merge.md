# branch --> merge

1. hacer un nuevo branch: git branch <nombre-branch>

2. ver todos: git branch

3. eliminar branch: git branch -d <nombre-branch>

4. para hacer un merge:
	a. hacer commit para finalizar la branch experimental
	b. cambiar a la branch  madre con git checkout <branch-madre>
	c. merge: git merge <nombre-branch-experimental>

5. Después de un marge las 2 ramas son virtualmente iguales
incluso un git add no marca diferencia. la diferencia empieza con
un commit.

6. de la misma forma cuando se crea una nueva branch es necesario
hacer un commit inmediatamente para marcar diferencia.
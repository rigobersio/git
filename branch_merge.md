# branch --> merge

1. hacer un nuevo branch: git branch <nombre_branch>

2. ver todos: git branch

3. eliminar branch: git branch -d <nombre_branch>

4. para hacer un merge:
	a. hacer commit para finalizar la branch experimental
	b. cambiar a la branch  madre con git checkout <branchmadre>
	c. merge: git merge <nombre.de.la.branch.experimental>
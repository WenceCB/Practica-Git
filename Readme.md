# Práctica GIT

## Ejercicio 1

### ¿Qué comando utilizaste en el paso 11? ¿Por qué?
> 		git reset --hard HEAD~1
> 
> Porque se nos pedía deshacer el último commit perdiendo los cambios realizados en el working copy, si hubiese hecho un `git reset HEAD~1`, no se habrían 'perdido' los cambios.

### ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?
> 		git reflog
	  git reset --hard numerodecommitanterior
 
> Porque el commit estaba 'perdido' por tanto primero usé un `git reflog` para localizar el hash del commit que queriamos rehacer y luego un `git reset --hard numerodecommit` para dehacer lo deshecho.

### El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?
>		  git branch
		git merge master
> En primer lugar compruebo que estoy posicionado en la rama
 que va a absorber a master , a continuación realizo el merge. En este caso no hay conflicto, git me informo con un mensaje `Already up to date`, ( es lineal ) por lo tanto hacer un merge o no van a tener el mismo acceso al primer commit que es dónde está alojado **git-nuestro.md**.


### El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?
>	      git branch
		git merge htmlify
> 
> Sí, Porque hay lineas de codigo con diferente contenido en la misma posición lo que provoca que git no sepa con que contenido quedarse, para soluciuonarlo abriremos el archivo que causó el conflicto y elegiremos con que código debe quedarse GIT. Guardaremos, lo añadiremos y haremos un commit por último. Con estos pasos debería solucionarse el conflicto y ejecutar el merge con éxito. 

### El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?
>		  git checkout master
		git merge styled
>Se hace el merge sin problemas , al igual que el anterior **Fast-Foward**.

### ¿Qué comando o comandos utilizaste en el paso 25?
> 		$ git log --graph --abbrev-commit --decorate --all
>	![captura](https://raw.githubusercontent.com/WenceCB/Practica-Git/master/Grafo.jpg?token=ADFRXEW2JSM3YWLLPYQD363BT2FRU)

### 26.- Hacer un merge “no fast-forward” de “title” en “master” (master absorbe a title)  ¿Podría ser **Fast-Foward**?

> 		git merge --no-ff title
>Si fuese fast foward desplazaríamos el puntero master al commit de title , en este caso title se mantiene en su commit y tanto **master** como **HEAD** se depslazan juntos al commit de la unión.

### 27. ¿Qué comando o comandos utilizaste en el paso 27?
>		git reset HEAD~1
>Volvemos atrás sin descartar los cambios del Working copy.


### 28.-Descartar los cambios - ¿Qué comando o comandos utilizaste en el paso 28?

>		git checkout git-nuestro.md

### 29.- Eliminar la rama "title" - ¿Qué comando o comandos utilizaste en el paso 29?
>
>		git branch -D title
> Aunque haya borrado la rama el contenido del working copy y staying area no varía dado a que hemos eliminado un puntero del grafo.

### 30.- Rehacer el merge que hemos deshecho - ¿Qué comando o comandos utilizaste en el paso 30?

>	   git reflog
	 git checkout (Hash)
> Comprobamos la posición del commit antes de borrar , y después nos movemos hasta él.

### 32.- Volver al commit inicial cuando se creó el poema - ¿Qué comando o comandos utilizaste en el paso 32?

>	   git reflog
	 git checkout (Hash) / git reset (Hash)
>Comprobamos la posición del commit antes de borrar , y después nos movemos hasta él.

### 33.- Volver al estado final, cuando pusimos título al poema - ¿Qué comando o comandos utilizaste en el paso 33?

>		git reflog
	  git checkout (Hash) / git reset (Hash)
>Comprobamos la posición del commit antes de borrar , y después nos movemos hasta él.
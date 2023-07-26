# Deschaer cambios - Tarea

##### Algunos ejercicios tienen *Spoiler warning*. Si les damos click, podemos ver una forma de resolverlo.

###### En este repo vas a encontrar un archivo de texto con algunas frases de los simuladores


- Clonar el repo con el siguiente comando
```
git clone https://github.com/mlucyy/cursoGIT.git
```
- Ir a la rama *simuladores-ejercicio*
```
git checkout simuladores-ejercicio
```
- Mirar los commits que hay
- Borrar todo el contenido que hay en *frases.txt* y guardarlo. Sin hacer commit
- OH NO! UN ERROR!! D: Utilizar un comando de git para deshacer los cambios

<br/><br/>
<details>
    <summary>Spoiler warning</summary>
Como no hicimos commits, los cambios aún están en nuestro *working* *directory*, por lo que debemos hacer un
  
    git restore frases.txt
    
De esta forma, deshacemos los cambios y volvemos al último commit
</details>
<br/><br/>

- De repente se vieron las dos temporadas en un finde y quieren agregar una frase al archivo *frases.txt*
- Agregar un commit a la rama *simuladores-ejercicio*
- Después de un tiempo de consideración, te diste cuenta de que no querías el último commit. Utilizar un comando de git para deshacer los cambios. CUIDADO: Estas en una rama compartida por muchos!

<br/><br/>
<details>
    <summary>Spoiler warning</summary>
Como es una rama compartida e hicimos un commit, si hacemos un *reset* vamos a borrar el historial que tenemos compartido con otras personas. Lo ideal sería hacer un *revert*, por lo que crearíamos un nuevo commit revirtiendo nuestros cambios y volviendo al commit anterior
  
    git revert <commit-hash>

Recordemos que el commit hash son los caractéres alfanuméricos que aparecen cuando hacemos *git* *log*
    
De esta forma, deshacemos los cambios y volvemos al último commit
</details>
<br/><br/>


- Crear una nueva rama a partir de la rama *simuladores-ejercicio* y realizar tres commits diferentes (Se pueden agregar más frases :) al archivo *frases.txt*
- OH NO! UN ERROR!! D: Utilizar un comando de git para deshacer los cambios de los últimos dos commits

<br/><br/>
<details>
    <summary>Spoiler warning</summary>
Si bien hicimos commits en una rama nuestra, nunca la compartimos, por lo que está bien hacer un reset. Para eso tenemos dos opciones. Ambos borran el segundo y tercer commit que hicimos, sin embargo, con la primera mantenemos los cambios que hicimos en esos commits en nuestra área de trabajo (working directory), mientras que el segundo borra esos cambios por completo

```
git reset --soft <commit-hash>
```

```
git reset --hard <commit-hash>
```

Recordemos que el commit hash son los caractéres alfanuméricos que aparecen cuando hacemos *git* *log*
    
De esta forma, deshacemos los cambios y volvemos al primer commit
</details>
<br/><br/>


- Después de un tiempo, te diste cuenta que no tenías que haber hecho ese *reset*
- OH NO! UN ERROR!! D: Utilizar un comando de git para deshacer el *reset* que hiciste

<br/><br/>
<details>
    <summary>Spoiler warning</summary>
Este ejercicio es un poco más complejo, pero útil. Primer debemos hacer un reflog

```
git reflog
```
Lo que nos interesa está en las dos primeras lineas, que tendran la siguiente forma
```
HEAD@{0}: reset: moving to <commit-hash>
HEAD@{1}: commit: <commit-message>
```
Cada línea está asociada a un *hash* (El valor alfanumérico de la izquierda), nos interesa el hash de la segunda línea, ya que en ese momento hicimos el commit. Si hacemos un reset con ese commit
```
git reset --hard <commit-hash>
```

    
De esta forma, deshacemos los cambios hechos por el reset, y volvemos a tener los 3 commits
Para estar seguro, los podemos ver con 

```
git log
```
</details>
<br/><br/>

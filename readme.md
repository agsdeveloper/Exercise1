#readme.md 
## (solución ejercicio 1)

**- ¿Qué comando utilizaste en el paso 11? ¿Por qué?**

 > `git reset --hard HEAD~1`
   
 > He utilizado un 'hard reset' un paso atrás. Debido a que el comando, me mueve el puntero HEAD una posición atrás y mi working copy se va a quedar tal y como lo tenía. Por ello recuperaré el fichero en su estado anterior.
**- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?**>  `git reset --hard HEAD@{1}`
     o 
    `git reset --hard 17d20a0`
    > Aquí, he utilizado la misma estrategia que en la pregunta anterior, pero a diferencia que se basa en deshacer el último paso. Utilizando reflog, puedo observar el id o utilizar la referencia HEAD@{}, que hará que me mueva por el reflog a la penúltima acción realizada.
**- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?**

> No causa ningún conflicto porque la rama STYLED ya tiene todas las modificaciones del archivo en su commit (realmente parte de la rama MASTER) y eso significa que está al día (Up-to-date), por ello el puntero HEAD no se moverá de STYLED.
**- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?**
  
>Sí causó un conflicto, porqué en las mismas líneas del archivo 'git-nuestro' hay dos versiones del mismo (en la rama HTMLIFY, aplicado estilo HTML y en la rama STYLED, aplicado estilo MARKDOWN). 
  Entonces, el procedimento es quedarnos con lo que nos interesa (contenido rama STYLED) y volver a commitear el archivo resultante final.
  
>También es importante dárse cuenta que se producirá un MERGE NO FAST FORWARD, debido a que la rama STYLED, absorbe el trabajo que tenía HTMLIFY y por ello este último commit tendrá dos padres.

**- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?**

>En este caso, no se producirá ningún conflicto debido principalmente a que se realizará un MERGE FAST FORWARD. La razón es que la rama MASTER absorbe todo el trabajo de STYLED y el puntero de la rama MASTER, pasará a apuntar al commit absorbido en STYLED.

**- ¿Qué comando o comandos utilizaste en el paso 25?**

>Me he creado un alias de varios comandos que me simplifican la correcta visión y síntesis del diagrama de commits,ramas y tags. He utilizado el siguiente comando:

>`git config --global alias.all “log --graph --decorate --pretty=oneline”` 
 **- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?**

> Realmente si, ya que la rama TITLE está un commit por encima de la rama MASTER. Lo que ocurriría es que el puntero de rama de MASTER, estaría apuntado al mismo commit que al de TITLE (PASO 23) y absorbería su trabajo.

**- ¿Qué comando o comandos utilizaste en el paso 27?**> `git reset 917373c` 

> O lo que es lo mismo, un reset soft al id antes del MERGE (proporcionado por el comando git reflog). El reset soft lo realizo porque no quiero perder los cambios de mi working copy.**- ¿Qué comando o comandos utilizaste en el paso 28?**

> Para descartar los cambios de mi working copy y mi staging area (es decir, descartar los cambios y dejar el archivo tal cual está en el repositorio) he utilizado el comando: 

> `git checkout -- git-nuestro.md`

**- ¿Qué comando o comandos utilizaste en el paso 29?**

> `git branch -D title`

> Este comando lo que realiza es un forzado para borrar la rama expecificada (sin confirmación).

**- ¿Qué comando o comandos utilizaste en el paso 30?**

> Aquí he realizado un reset HARD consultando la id del commit que tengo realizado el MERGE, utilizando reflog.

>`git reset --hard d4d8d91`

**- ¿Qué comando o comandos usaste en el paso 32?**> Aquí he utilizado de nuevo un reset HARD y de nuevo he consultado la id de mi commit inicial:

>`git reset --hard 17d20a0`
**- ¿Qué comando o comandos usaste en el punto 33?**

>Aquí otra vez he utilizado el reset HARD y de nuevo he consultado la id de mi commit inicial:

>`git reset --hard f761ef3`
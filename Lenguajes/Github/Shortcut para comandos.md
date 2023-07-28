# Shortcut para comandos
Git no infiere automáticamente su comando si lo escribe parcialmente. Si no desea escribir el texto completo de cada uno de los comandos de Git, puede configurar fácilmente un alias para cada comando usando git config. Aquí hay un par de ejemplos que puede configurar:

![[Pasted image 20221223213119.png]]
Esto significa que, por ejemplo, en lugar de escribir git commit, solo necesita escribir git ci.

Esta técnica también puede ser muy útil para crear comandos que cree que deberían existir. Por ejemplo, para corregir el problema de usabilidad que encontró al desmontar un archivo, puede agregar su propio alias de desmontaje a Git:

![[Pasted image 20221223213126.png]]
Como puede ver, Git simplemente reemplaza el nuevo comando con cualquier alias para el que lo haya creado. Sin embargo, tal vez desee ejecutar un comando externo, en lugar de un subcomando de Git. En ese caso, inicia el comando con un !carácter. Esto es útil si escribe sus propias herramientas que funcionan con un repositorio de Git. Podemos demostrar mediante alias git visual para ejecutar git:

![[Pasted image 20221223213135.png]]

# Proposito y precondiciones

Tanto el proposito como las precondiciones se escriben en comentarios.
## Proposito

 El **proposito** es lo que deberia hacer el programa, es decir, se enfoca en el estado final del programa y no lo que suceda en el medio (transformaciones parciales, intermedias), cuando el efecto de un programa coincide con su proposito, decimos que es un programa correcto. Si el proposito no lo indica, el cabezal deberia quedarse donde comenzo. Si no se indica donde empieza el cabezal, este empezara en la celda 0,0 y el cabezal debe volver a 0,0.
## Precondiciones

Las **precondiciones** son las condiciones necesarias para garantizar que un problema pueda resolverse, es decir deben contestarse por si o no.  Las precondiciones se dan en terminos del estado del tablero inicial. La combinacion de los comando afecta a las precondiciones, por ejemplo, si tengo dos Sacar(Rojo) si o si debo tener como minimo dos bolitas rojas en la celda donde quiero realizar ese comando. Si la precondicion se cumple un programa correcto debe cumplir su proposito. En caso de que la precondicion no se cumpla, el programa falla con BOOM.

Al conjunto de proposito y precondiciones lo llamamos **contrato** de un programa. El contrato establece que debe hacer un programa y en que situaciones va a funcionar correctamente.

![[Pasted image 20230819161030.png]]
## Observaciones

Tambien tenemos las **observaciones**, son aclaraciones que resultan perninentes pero no son parte del proposito.


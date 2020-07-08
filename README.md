# Hunting Treasure

Para poder resolver este problema se debe tener en cuenta de que la única forma de recoger todos los tosoros, es ir recogiendo todos los tesoros existentes en una fila antes de subir a la siguiente, dado que está prohibido volver a una fila que ya se pasó.

Para recoger todos los esoros existenttes en una fila, se partirá de donde se subió la vez anterior (una de las zonas seguras), y recorrer todo hacia la derecha y posteriormente todo a la izquierda, o viceversa. Por lo cual en cada fila se terminará ubicado en el tesoro de más a la derecha o de más a la izquierda de esa fila.

Por lo cual, lo primero que se debe hacer es leer todos los tesoros e ir registrándolos por fila, en 2 arreglos, izquierda y derecha, ambos de tamaño n (cantidad de filas del mapa). Luego de esto se deben guardar las zonas seguras, las cuales funcionan como "escaleras al siguiente nivel". Se crean 2 arreglos los cuales ayudarán a conocer el lugar por el que se debe subir al siguiente nivel, estos arreglos indican que para una determinada posición, la zona segura siguiente a la izquierda estará en la posición x y la segura a la derecha estará en la posición y.

Posteriormente, se debe comenzar con la recolección de tesoros, la cual sigue las siguientes reglas.

	1.- La primera fila siempre terminará en el tesoro más a la derecha. Por lo que se puede subir por su derecha o su izquierda. Esto al menos que no existan tesoros en esa fila, por lo que se procederá a subir por la zona segura más cercana.
	2.- Para el resto de filas, exceptuando la última se debe calcular la distancia a recorrer entra la subida en la fila anterior y subir por la escalera:
		a.- izquierda del tesoro más a la izquierda.
		b.- derecha del tesoro más a la izquierda.
		c.- izquierda del tesoro más a la derecha.
		d.- derecha del tesoro más a la derecha.
	Por lo cual se calcularán 16 posiblies subidas, guardando la mejor para cada caso. En caso de no existir tesoros en ese nivel, sólo se subirá al siguiente.
	3.- En la última fiila, se hará lo mismo, pero esta vez, sólo se debe terminar en uno de los tesoros más extremos.

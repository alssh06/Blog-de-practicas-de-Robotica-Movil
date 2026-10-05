# Blog-de-practicas-de-Robotica-Movil

## Practica 1: Navegación pseudoaleatoria con FSM en una aspiradora de gama baja

### Guion de funcionamiento del programa
Para empezar el robot posee 4 estados principales:
- **SPIRAL**: Avanza describiendo una espiral que se va abriendo.
- **FORWARD**: Avanza en línea recta.
- **BACKWARD**: Retrocede durante un tiempo corto.
- **TURN**: Gira en el sitio con dirección y duración aleatorias.

Y consta del siguiente flujo de accion en su bucle:
1. El robot **empieza en estado SPIRAL**.
2. Mientras está en SPIRAL o FORWARD, avanza hasta que:
   - El láser detecta un obstáculo delante, **o**
   - El sistema anti-atasco detecta que lleva demasiado tiempo sin moverse.
3. En ese momento pasa a **BACKWARD** (retrocede).
4. Al terminar el retroceso (o si no consigue retroceder), pasa a **TURN**.
5. Después del giro, elige de forma aleatoria entre volver a **FORWARD** o a **SPIRAL**.
6. El ciclo se repite indefinidamente.

Además del láser, el código incorpora un **sistema de detección de atascos por posición**. Este sistema guarda la última posición en la que el robot se movió de forma significativa. Si pasa demasiado tiempo sin avanzar lo suficiente, se considera que está atascado aunque el láser no detecte nada. También se utiliza durante el retroceso: si el robot no se mueve al intentar ir hacia atrás, se fuerza el giro para intentar escapar.

### Videos del codigo







### Conclusiones

En los videos se ve que el robot se queda atrapado al final del segundo video, esto es una posibilidad debido a su funcionamiento automatico, pero tambien podemos decir debido a esto mismo que en algun punto saldra y limpiara el resto de la casa. Aun asi, añadiria que este robot tiene una mayor eficacia si se encierra de habitacion en habitacion en vez de recorrer la casa al completo, debido a que asi tiene mas posibilidades de limpiar mas area de mas de necesitar menos bateria.





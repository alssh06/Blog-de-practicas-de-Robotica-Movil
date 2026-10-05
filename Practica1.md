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
https://github.com/user-attachments/assets/ce0f226f-ce3c-4ed8-8990-298c63f54aa2

https://github.com/user-attachments/assets/17fe72c3-cf79-45de-8865-30eb7b6992d5

https://github.com/user-attachments/assets/f2ffd089-9d67-4a91-93b3-b37662ed3b56

https://github.com/user-attachments/assets/1ec1aa50-5f09-4443-822a-537ebe720fa0


### Conclusiones
Por lo que podemos ver en los videos el robot se mueve de forma completamente aleatoria e impredecible, lo que hace dificil que complete la limpieza de la casa en un tiempo corto o sin necesitar cargar su bateria. Por lo que, a la hora de usar estos robots, seria recomendable meterlos en habitaciones cerradas e irlos moviendo entre ellas para generar una aleatoriedad controlada y aumentar su eficiencia


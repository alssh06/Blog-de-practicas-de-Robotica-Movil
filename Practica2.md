### Guion de funcionamiento del programa 
El programa implementa un **sistema reactivo de bucle infinito** para que el coche de formula1 sega la línea roja, basado en la teoría de control clásico (PID) y en el paradigma de sistemas reactivos (actuación(t) = f(observación(t))).

#### Estados principales (selección de acción reactiva):
- **FOLLOW**: Sigue la línea con control PID adaptativo.
- **RECOVERING**: Intenta recuperar la línea usando el último error conocido (ventana corta de frames).
- **SEARCH**: Búsqueda oscilante (senoidal) cuando se pierde la línea durante demasiado tiempo.

#### Flujo de acción :

1. **Sensar**  
   Capturar imagen → extraer ROI inferior → convertir a HSV → máscara de rojo → calcular centroide de la línea.

2. **Evaluar situación** (espacio de situaciones mutuamente excluyentes):
En función de si se detecta linea, se ha dejado de detectar la linea tras un seguimiento o si no se ha seguido la linea, se selecciona un caso

3. **Actuar según situación** :

 **-Caso FOLLOW (LÍNEA_DETECTADA):**
 Se calcula el error y a través del mismo observamos si tenemos enfrente una recta o una curva, ajustando que Ks se usan, y apartir se esto se calcula la proporcional, la integral y la derivada que manejan la velocidad del coche

 **-Caso RECOVERING:**
 Se hace que el coche gire en la dirección donde se perdió la linea para volver a encontrarla

 **-Caso SEARCH:**
 Ponemos una velocidad y velocidad angulares fijas para que el coche gire en busca de la linea

4. **Ejecutar**  
Se ponen las velocidades actualizas al final del ciclo junto con una actualización de la imagen

5. **Repetir** 



### Videos del código


### Conclusiones
Por lo que podemos ver el coche sigue a la linea con un poco de dificultades y ajustando constantemente la posición para asegurar un buen seguimiento. Durante la práctica se han encontrado dificultades en el ajuste general de los valores, que incluyen las Ks de los PIDs, las velocidades máximas y mínimas fijas y de aceleración y de frenado, y los valores de fijación de la cámara y los sensores. Se ha llegado a un punto aceptable con una velocidad media lenta, y es muy posible que se pueda mejorar, pero esta ha sido la mejor combinación a la que se ha logrado llegar.

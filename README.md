# Blog-de-practicas-de-Robotica-Movil

## Practica 1: Navegación pseudoaleatoria con FSM en una aspiradora de gama baja

### Objetivo
El objetivo de esta practica es programar una aspiradora cuya misión es que limpie una casa a través de un sistema pseudoaleatorio con FSM que hemos programado nosotros.

### Guion de desarrollo
Lo primero que se hace en esta practica es describir los estados de la aspiradora junto con sus estadísticas. Estas incluirán el estado giro, espiral, avanzar y retroceder, además de sus velocidades y tiempos para ciertas acciones. Una vez descritas, creamos un bucle infinito que el robot seguirá, que sigue esta idea:

El robot empezara con una espiral hasta que choque. Una vez choca, el robot retrocede y gira con tiempo y sentidos aleatorios. Después, otra vez de forma aleatoria, el sistema elije si hacer otra espiral o avanzar, y esta acción no terminara hasta que haya un choque. Así de forma indefinida hasta que se apague el sistema

Además de lo descrito, el código tiene implementados un laser, un cronometro y un detector de posición, con los que detectara los choques y los atascamientos. Siendo que si el laser detecta un choque retrocederá, pero en caso de que el laser no detecte choque pero el robot no se haya movido en un tiempo predeterminado, este considerara que ha chocado. También hemos implementado que si durante el retroceso el robot no se mueve, este considerara que esta atascado, y que necesita girar para salir.

### Video del codigo


# Aprendizajes:
# Clases Base - Video
# Clases Derivadas - Pelicula, Serie (con composicion)
# Poliformismo con arreglo de apuntadores de la clase Base - usando el método virtual str() y las
# clases Derivadas - Serie y Pelicula
# Arreglos de apuntadores de clase base - se aplica el poliformismo con un 
# método virtual y las clases Derivadas (hijas)

<img alt="points bar" align="right" height="36" src="../../blob/status/.github/activity-icons/points-bar.svg" />


# CASOS DE PRUEBA
```
# Caso 1
Datos de entrada:
1
1
100

Datos de salida:
100 P1 100 A 100.000000 1
101 P2 200 A 100.000000 2
Total = 2


# Caso 2
Datos de entrada:
1
2
C

Datos de salida:
102 P3 100 C 90.000000 3
Total = 1


# Caso 3
Datos de entrada:
1
3

Datos de salida:
100 P1 100 A 100.000000 1
101 P2 200 A 100.000000 2
102 P3 100 C 90.000000 3
Peliculas = 3
Series = 0


# Caso 4
Datos de entrada:
1
4

Datos de salida:
100 P1 100 A 100.000000 1
101 P2 200 A 100.000000 2
102 P3 100 C 90.000000 3
Total Peliculas = 3


# Caso 5
Datos de entrada:
1
5

Datos de salida:
No series

```

2. Push your changes back to your assignment GitHub repo. Remember to try to make your commits atomic and your commit messages descriptive.

3. Wait a minute for the tests to run. Refresh the repo page to see if you have completed the exercise successfully.
You should score 100 marks if the test passes.

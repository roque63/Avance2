
# Aprendizajes:
# Clases Base - Video
# Clases Derivadas - Pelicula, Serie (con composicion)
# Poliformismo utilizando 1 método virtual str()
# Arreglos de apuntadores

<img alt="points bar" align="right" height="36" src="../../blob/status/.github/activity-icons/points-bar.svg" />

```c++

/
//  main.cpp
//  Tarea2
//
//  Created by Ma. Guadalupe Roque Díaz de León on 28/05/23.
//

#include <iostream>
#include "Video.h"
#include "Poliformismo.h"
#include "Episodio.h"
#include "Pelicula.h"
#include "Serie.h"

void poliformismo(Poliformismo inventario){
    int opcion;
    double calificacion;
    string genero;
    cin >> opcion;

    switch (opcion) {
        case 1:
            cin >> calificacion;
            inventario.reporteCalificacion(calificacion);
            break;

        case 2:
            cin >> genero;
            inventario.reporteGenero(genero);
            break;

        case 3:
            inventario.reporteInventario();
            break;

        default:
            cout << "Error\n";
            break;
    }
}

int main() {    
        // Declaracion de objetos
        Video viernes;
        Pelicula pel;
        Serie serie2;
        Poliformismo neflix;

        Episodio episodio_viernes{"Tigres_Rayados", 90, 100};
        Episodio episodio_sabado{"Tigres_Campeones", 90, 100};
        Pelicula peli{"0001", "Tigres_Chivas", 600, "Deportes", 100.0, 20};
        Serie serie1{"0002", "POO", 500, "Programacion", 100};

        int opcion;

        // Añadir episodios a la serie1
        serie1.agregaEpisodio(episodio_viernes);
        serie1.agregaEpisodio(episodio_sabado);

        // leer la opcion
        cin >> opcion;

        switch (opcion){
            case 1:
                cout << serie1.getGenero() << endl;
                cout << serie1.getDuracion() << endl;
                cout << serie1.getCalificacion() << endl;
                cout << serie1.getEpisodio(0).str() << endl;
                cout << serie1.getEpisodio(1).str() << endl;
                cout << serie1.str() << endl;
                break;

            case 2:
              cout << "CDV=" << viernes.str() << endl;
              cout << "CDP=" << pel.str() << endl;
              cout << "CDS=" << serie2.str() << endl;
                break;

            case 3:
               neflix.leerArchivo("Inventario1.csv");
               poliformismo(neflix);
               break;

        case 4:
              neflix.leerArchivo("Inventario2.csv.csv");
              poliformismo(neflix);
              break;

        default:
              cout << "incorrecta" ;
        }


    return 0;
}


```
# CASOS DE PRUEBA
```c++
/* Casos de Prueba
//  
# 1
Datos de entrada:
1

Datos de salida:
Programacion
500
100
Tigres_Rayados 90 100
Tigres_Campeones 90 100
0002 POO 500 Programacion 100.000000 2
Tigres_Rayados 90 100
Tigres_Campeones 90 100

# 2
Datos de entrada:
2

Datos de salida:
CDV=0000 TC1030 10 Computación 100.000000
CDP=0000 TC1030 10 Computación 100.000000 100
CDS=0000 TC1030 10 Computación 100.000000 0

# 3
Datos de entrada:
3
1
100

Datos de salida:
0 100 P1 100 A 100.000000 1
1 101 P2 200 A 100.000000 2
2 102 P3 100 A 95.000000 3
3 103 P4 200 P 99.000000 4
4 104 P5 100 P 110.000000 5
5 105 P6 200 P 120.000000 6
6 106 P7 200 A 100.000000 7
7 107 P8 200 A 100.000000 8
8 108 P9 200 A 95.000000 9
9 109 P10 200 P 150.000000 10
100 P1 100 A 100.000000 1
101 P2 200 A 100.000000 2
106 P7 200 A 100.000000 7
107 P8 200 A 100.000000 8
total = 4

# 4
Datos de entrada:
3
2
A
Datos de salida:
0 100 P1 100 A 100.000000 1
1 101 P2 200 A 100.000000 2
2 102 P3 100 A 95.000000 3
3 103 P4 200 P 99.000000 4
4 104 P5 100 P 110.000000 5
5 105 P6 200 P 120.000000 6
6 106 P7 200 A 100.000000 7
7 107 P8 200 A 100.000000 8
8 108 P9 200 A 95.000000 9
9 109 P10 200 P 150.000000 10
100 P1 100 A 100.000000 1
101 P2 200 A 100.000000 2
102 P3 100 A 95.000000 3
106 P7 200 A 100.000000 7
107 P8 200 A 100.000000 8
108 P9 200 A 95.000000 9
total = 6


# 5
Datos de entrada:
3
4
1
Datos de salida:
0 100 P1 100 A 100.000000 1
1 101 P2 200 A 100.000000 2
2 102 P3 100 A 95.000000 3
3 103 P4 200 P 99.000000 4
4 104 P5 100 P 110.000000 5
5 105 P6 200 P 120.000000 6
6 106 P7 200 A 100.000000 7
7 107 P8 200 A 100.000000 8
8 108 P9 200 A 95.000000 9
9 109 P10 200 P 150.000000 10
100 P1 100 A 100.000000 1
cal promedio = 100


# 6
Datos de entrada:
3
5
1
Datos de salida:
0 100 P1 100 A 100.000000 1
1 101 P2 200 A 100.000000 2
2 102 P3 100 A 95.000000 3
3 103 P4 200 P 99.000000 4
4 104 P5 100 P 110.000000 5
5 105 P6 200 P 120.000000 6
6 106 P7 200 A 100.000000 7
7 107 P8 200 A 100.000000 8
8 108 P9 200 A 95.000000 9
9 109 P10 200 P 150.000000 10
no series

```

2. Push your changes back to your assignment GitHub repo. Remember to try to make your commits atomic and your commit messages descriptive.

3. Wait a minute for the tests to run. Refresh the repo page to see if you have completed the exercise successfully.
You should score 100 marks if the test passes.

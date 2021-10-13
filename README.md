# Algebra-Abstracta-Gabriel-Choque

El algoritmo de Euclides nos ayuda a hallar el Maximo Común Divisor de 2 numeros.

Algoritmo de Euclides:

    Mientras modulo(a, b) != 0 hacer:
        Variable_entera temp = b;
        b = modulo(a, b);
        a = temp;
        cont++;
    }

Para hallar "x" e "y":

    Hacer (g0, g1, u0, u1, v0, v1, i) = (B, A, 1, 0, 0, 1, 1)

    Mientras g[i] =! 0 hacer:
      Hacer y[i+1] = parte entera(g[i+1]/g[i]
      Hacer g[i+1] = g[i-1] - y[i+1] * g[i]
      Hacer u[i+1] = u[i-1] - y[i+1] * u[i]
      Hacer v[i+1] = v[i-1] - y[i+1] * v[i]
      Haver i = i+1

    Si ( v[i-1] < 0)
      Hacer v[i-1] = v[i-1] + B

    Hacer x = v[i-1]

Entonces en las variables:

    Valor de "x" = u[i]
    
    VAlor de "y" = v[i]
    
Ejemplo:

  x = Euclid_extended(A, B)

  x = Euclid_extended(9, 275)
   
  Hacer (g0, g1, u0, u1, v0, v1, i) = (B, A, 1, 0, 0, 1, 1)

      Reemplazando en el pseudocodigo quedaria:
        i     y[i]     g[i]     u[i]     v[i]
        0     -        275      1        0
        1     -        9        0        1
        2     30       5        1        -30
        3     1        4        -1       31
        4     1        1        2        -61
        5     4        0        -9       275 
 
  
  El proceso se repite hasta que g[i] = 0; 
  
  Entonces x = -61, pues v antes de que g sea 0 es -61, e y = 2, pues u antes de que g sea 0 es 2.
  
  
  Esto lleva a la ecuación gcd(9, 275) = -61(9) + 2(275)
  
  Respuesta 1 = 1, cumple
  
  ¿Que tan rapido es el algoritmo de Euclides?
  
  Es muy rapido, por lo general llega a la solucion en muy pocos pasos, por ejemplo encontrar el mcd dentro de un cuerpo de
  2048 bits es instantaneo.

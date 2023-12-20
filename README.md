# Oca
No son necesarias librerias especiales ni normas especiales para ejecutar o compilar, al principio te preguntaran el nombre y un solo apellido a ambos jugadores y el dado se lanza con la tecla enter

Se compone de un array de 64 casillas, sus casillas especiales son:

    Casilla 5 - Oca
    Casilla 6 - Puente
    Casilla 9 - Oca
    Casilla 14 - Oca
    Casilla 18 - Oca
    Casilla 19 - Posada
    Casilla 23 - Oca
    Casilla 26 - Dados
    Casilla 27 - Oca
    Casilla 31 - Pozo
    Casilla 32 - Oca
    Casilla 36 - Oca
    Casilla 41 - Oca
    Casilla 42 - Laberinto
    Casilla 45 - Oca
    Casilla 50 - Oca
    Casilla 52 - Cárcel
    Casilla 53 - Dados
    Casilla 54 - Oca
    Casilla 58 - Muerte
    Casilla 59 - Oca
    Casilla 63 - Puerta del Jardín de la Oca
    Y las normales son el resto.

Reglamento:

   
    Oca: Casillas 5, 9, 14, 18, 23, 27, 32, 36, 41, 45, 50, 54 y 59. Si se cae en una de estas casillas, se debe avanzar hasta la siguiente casilla en la que hay una oca y volver a tirar.
    Puente: Casilla 6 y 12. Si se cae en estas casillas se salta a la casilla 19 (la Posada) y se pierde un turno. En algunos tableros, solo figura como puente la casilla 6.
    Posada: Casilla 19. Si se cae en esta casilla se pierde un turno.
    Pozo: Casilla 31. Si se cae en esta casilla se pierden 3 turnos;
    Laberinto: Casilla 42. Si se cae en esta casilla, se esta obligado a retroceder a la casilla 30.
    Cárcel: Casilla 56. Si se cae en esta casilla se pierden 5 turnos;
    Dados: Casillas 26 y 53. Si se cae en estas casillas, se suma la marcación de la casilla de los dados (26 o 53) y se avanza tanto como resulte.
    Muerte: Casilla 58. Si se cae en esta casilla, hay que volver a la Casilla 0, vuelve a iniciar el Camino.
    A partir de la casilla 60: Se juega solo con 1 dado.
    Entrar al Jardín de la Oca: Es necesario sacar los puntos justos para entrar, en caso de exceso se retroceden tantas casillas como puntos sobrantes.


Estados (se mantienen condicionalmente):

    Los estados duran más que una llamada:
    Puente: dado1, dado2=0 durante 1 turno

    Pozo: dado1, dado2=0 durante 3 turnos

    Carcel:dado1, dado2=0 durante 5 turnos

    Casilla>60: dado2=0
    

Acciones: 
    Duran una sola llamada:
    
    Oca: Se mueve a la siguiente oca y vuelve a tirar

    Puente: se mueve a la casilla Posada

    Laberinto: se mueve a la casilla 30

    Dado 26: te mueves a la casilla 53 (el otro dado) y vuelves a tirar

    Dado 53: te mueves a la casilla 26 (el otro dado) y vuelves a tirar

    Calavera: te mueves a la casilla 0

    Jardín de la oca: el jugador gana y se acaba la partida


   DISEÑO DEL PROGRAMA:
    El programa consta de 6 módulos más el principal:
   
1 MÓDULO PARA CADA JUGADOR (JUGADOR _1 Y JUGADOR_ 2)
1 MÓDULO QUE DEVUELVE EL TIPO DE CASILLA EN EL QUE ESTA EL JUGADOR (BUSCAR_TIPO_CASILLA)
1 MÓDULO QUE INDICA LAS ACCIONES A REALIZAR SEGÚN EL TIPO DE CASILLA (COMPROBAR_CASILLA)
1 MÓDULO QUE SIMULA LA TIRADA DE DADOS (DADOS)
1 MÓDULO QUE DEVUELVE LA CANTIDAD DE TURNOS PERDIDOS EN FUNCIÓN DE LA CASILLA (TURNOS_PERDIDOS)

Explicación de los módulos:


MÓDULOS JUGADOR_1 Y JUGADOR_2:

1.PERMITEN OBTENER EL VALOR DE LA CASILLA DE CADA JUGADOR AL FINAL DE LA TIRADA Y DEVUELVEN DEL DATO  AL MóDULO PRINCIPAL
2.JUNTO CON EL MÓDULO TURNOS_PERDIDOS SON LOS ÚNICOS MÓDULOS LLAMADOS DIRECTAMENTE DESDE EL MÓDULO PRINCIPAL
3.LLAMAN AL MÓDULO DADOS QUE DEVUELVE EL VALOR CONJUNTO DE LOS 2 DADOS
4.LLAMAN AL MÓDULO COMPROBAR CASILLA QUE DEVUELVE EL NÚMERO DE LA CASILLA ACTUAL AL MÓDULO DEL JUGADOR QUE LO HAYA LLAMADO

MÓDULO COMPROBAR_ CASILLA
1.LLAMADO DESDE LOS MÓDULOS DE CADA JUGADOR
2.LLAMA AL MÓDULO BUSCAR_TIPO_CASILLA. ESTE LE DEVUELVE
EL TIPO DE CASILLA EN EL QUE SE ESTA
3. DEVUELVE A LOS MÓDULOS JUGADOR_1 Y JUGADOR_2 
EL NUMERO DE LA CASILLA TRAS LA TIRADA

MÓDULO DADOS
1.LLAMADO DESDE LOS MÓDULOS DE CADA JUGADOR
2.DEVUELVE  EL VALOR CONJUNTO DE LOS DADOS

MÓDULO BUSCAR_TIPO_ CASILLA
1.LLAMADO DESDE DEL MÓDULO COMPROBAR_CASILLA
2.DEVUELVE  EL TIPO DE CASILLA EN EL QUE SE ESTA

MÓDULO TURNOS_PERDIDOS
1.LLAMADO DESDE MÓDULO PRINCIPAL
2.DEVUELVE LA CANTIDAD DE TURNOS PERDIDOS SEGÚN EL VALOR DE LA CASILLA
3.CASILLAS DE PERDIDA DE TURNO: 
POSADA ( CASILLA 19, 1 TURNO PERDIDO), 
POZO ( CASILLA 31, 3 TURNOS PERDIDOS), 
CÁRCEL (CASILLA 52, 5 TURNOS PERDIDOS)

Al finalizar la partida, se preguntará si deseas jugar otra, si la respuesta es afirmativa,se reinicirá la partida.



    

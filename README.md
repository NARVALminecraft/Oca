# Oca
No son necesarias librerias especiales ni normas especiales para ejecutar o compilar, al principio te preguntaran el nombre y un solo apellido a ambos jugadores y el turno se pasa con la tecla enter

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

Reglamento:

   
    Oca: Casillas 5, 9, 14, 18, 23, 27, 32, 36, 41, 45, 50, 54 y 59. Si se cae en una de estas casillas, se puede avanzar hasta la siguiente casilla en la que hay una oca y volver a tirar.
    Puente: Casilla 6 y 12. Si se cae en estas casillas se salta a la casilla 19 (la Posada) y se pierde un turno. En algunos tableros, solo figura como puente la casilla 6.
    Posada: Casilla 19. Si se cae en esta casilla se pierde un turno.
    Pozo: Casilla 31. Si se cae en esta casilla se pierden 3 turnos;
    Laberinto: Casilla 42. Si se cae en esta casilla, se est obligado a retroceder a la casilla 30.
    Cárcel: Casilla 56. Si se cae en esta casilla se pierden 5 turnos;
    Dados: Casillas 26 y 53. Si se cae en estas casillas, se suma la marcación de la casilla de los dados (26 o 53) y se avanza tanto como resulte.
    Calavera: Casilla 58. Si se cae en esta casilla, hay que volver a la Casilla 1, vuelve a iniciar el Camino.
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

    Dado 26: te mueves a la casilla 53 (el otro dado) y avanzas 5+3 casillas

    Dado 53: te mueves a la casilla 26 (el otro dado) y avanzas 2+6 casillas

    Calavera: te mueves a la casilla 0

    Jardín de la oca: el jugador gana y se acaba la partida

    

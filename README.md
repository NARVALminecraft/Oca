# Oca
Oca programacion

Array de 64 casillas, sus casillas especiales son:

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

    Inicio de la Partida: Si al tirar los dados la suma de ambos es 9, puede suceder:
        Los dados son 5 y 4. Se salta a la casilla 53 (Dados)
        Los dados son 3 y 6. Se salta a la casilla 26 (Dados)
    Oca: Casillas 5, 9, 14, 18, 23, 27, 32, 36, 41, 45, 50, 54 y 59. Si se cae en una de estas casillas, se puede avanzar hasta la siguiente casilla en la que hay una oca y volver a tirar.
    Puente: Casilla 6 y 12. Si se cae en estas casillas se salta a la casilla 19 (la Posada) y se pierde un turno. En algunos tableros, solo figura como puente la casilla 6.
    Posada: Casilla 19. Si se cae en esta casilla se pierde un turno.
    Pozo: Casilla 31. Si se cae en esta casilla, NO se puede volver a jugar hasta que no caiga otro jugador en esa casilla.
    Laberinto: Casilla 42. Si se cae en esta casilla, se est obligado a retroceder a la casilla 30.
    Cárcel: Casilla 56. Si se cae en esta casilla, hay que permanecer hasta que caiga alli otro jugador y lo rescate.
    Dados: Casillas 26 y 53. Si se cae en estas casillas, se suma la marcación de la casilla de los dados (26 o 53) y se avanza tanto como resulte.
    Calavera: Casilla 58. Si se cae en esta casilla, hay que volver a la Casilla 1, vuelve a iniciar el Camino.
    A partir de la casilla 60: Se juega solo con 1 dado.
    Entrar al Jardín de la Oca: Es necesario sacar los puntos justos para entrar, en caso de exceso se retroceden tantas casillas como puntos sobrantes.

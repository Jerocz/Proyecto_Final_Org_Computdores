BLACKMIND - Version 0.9
========================

CAMBIO EN ESTA VERSION
----------------------

ARREGLO CRITICO: Validacion de suma > 11 al plantarse.

Antes, si te plantabas con suma > 11 (sin haber usado la secreta),
el juego sumaba la suma como puntos. Esto era un bug grave porque
permitia ganar 12, 13, 14 puntos plantandose despues de pasarse.

Ahora `stand()` valida 3 casos:
  - Suma > 11    -> 0 puntos (te pasaste)
  - Suma 0 o menos -> 0 puntos
  - Suma 1 a 11    -> igual a la suma

OBJETIVO DEL JUEGO
------------------
Acumular la mayor cantidad de puntos en 3 rondas.
Los puntos al plantarte = la suma actual (si esta entre 1 y 11).
Si te pasas de 11, no sumas nada esa ronda.

CONTROLES
---------
  Flechas Izq/Der  :  Mover el cursor
  Enter            :  Seleccionar carta o activar secreta
  P                :  Plantarse
  Q                :  Salir

REGLAS DE PUNTOS
----------------
| Suma final  | Puntos              |
|-------------|---------------------|
| 0 o menos   | 0                   |
| 1 a 11      | igual a la suma     |
| 12 o mas    | 0 (te pasaste)      |

LA CARTA SECRETA
----------------
Aparece como +***+ Solo se puede usar UNA vez por ronda.
Al activarse ejecuta uno de 5 efectos al azar:
  1. Revela 1 carta numerica oculta
  2. Revela 2 cartas numericas ocultas
  3. +3 puntos a tu suma actual
  4. -2 puntos a tu suma actual
  5. Deselecciona todas tus cartas

REGLA DE PASARSE
----------------
- Si te pasas y AUN no usaste la secreta: aviso, la ronda continua
- Si te pasas y YA usaste la secreta: ronda terminada con 0 puntos
- Si te plantas con suma > 11: 0 puntos (NUEVO)

COMPILACION
-----------
1. Abrir JackCompiler y apuntarlo a la carpeta del proyecto
2. Cargar la carpeta en VMEmulator
3. Pulsar Run

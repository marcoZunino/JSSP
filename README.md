# JSSP

Log de avances:
---
19/7
  - se agrega restriccion de precedencia para los bz (4.1.1.1)
  - se modifica la restriccion de precedencia de cantidades (4.1.2) para permitir producir de sobra (se agregan slacks)
  - chequeo de factibilidad mediante seguimiento de constantes 
  - Resultados: (con estos cambios y sin considerar la restriccion de no superposicion)
    1) Gurobi: -724800 (7700 si se considera la constante total de xtQx) en 6 horas
      FACTIBLE PERO NO ÓPTIMO
      - S{JB1,LAM1,M1,1} = 4.0
      - S{JB1,LAM1,M1,2} = 0.0
      - S{JB1,LAM2,M1,1} = 0.0
      - S{JB1,LAM2,M1,2} = 4.0
      - S{JB1,B1,M2} = 8.0
      - S{JB1,B1,M3} = 8.0
      - S{JB2,LAM1,M1} = 1.0
      - S{JB2,B2,M2} = 7.0
      - L{JB1,LAM1,M1,1} = 0.0
      - L{JB1,LAM1,M1,2} = 4.0
      - L{JB1,LAM2,M1,1} = 0.0
      - L{JB1,LAM2,M1,2} = 4.0
      - L{JB1,B1,M2} = 0.0
      - L{JB1,B1,M3} = 4.0
      - L{JB2,LAM1,M1} = 2.0
      - L{JB2,B2,M2} = 2.0
      - E{JB1} = 12.0
      - E{JB2} = 11.0
      - d{JB1} = 0.0
      - d{JB2} = 1.0
      - bz{L{JB1,LAM1,M1,1}} = 1.0
      - bz{L{JB1,LAM1,M1,2}} = 0.0
      - bz{L{JB1,LAM2,M1,1}} = 1.0
      - bz{L{JB1,LAM2,M1,2}} = 0.0
      - bz{L{JB1,B1,M2}} = 1.0
      - bz{L{JB1,B1,M3}} = 0.0
      - bz{L{JB2,LAM1,M1}} = 0.0
      - bz{L{JB2,B2,M2}} = 0.0
      - X^M1 =
        - [[0 0 0 0 0]
        - [0 0 1 0 0]
        - [0 0 0 0 0]
        - [1 0 0 0 0]
        - [0 1 0 0 0]]
      - X^M2 =
        - [[0 0]
        - [1 0]]
      - X^M3 =
        - [[1]]
      - u_{M1,1} = 1.0
      - u_{M1,2} = 1.0
      - u_{M1,3} = 1.0
      - u_{M1,4} = 0.0
      - u_{M1,5} = 0.0
      - u_{M2,1} = 1.0
      - u_{M2,2} = 0.0
      - u_{M3,1} = 1.0
    2) Dwave: error de embedding


17/7
  - restricciones 4.8.1, 4.9.1, 4.9.2, 4.9.3
  - soluciones poco optimas y no factibles para Gurobi
  - error de embedding en Dwave


15/7:
  - ejecucion con restricciones 4.1.1, 4.1.2, 4.2, 4.3, 4.5, 4.6, 4.6.1, 4.7.1, 4.7.1.1 (P = 2000):
    1) Dwave: -327700.0
      - S{JB1,LAM1,M1,1} = 2
      - S{JB1,LAM1,M1,2} = 0
      - S{JB1,LAM2,M1,1} = 1
      - S{JB1,LAM2,M1,2} = 0
      - S{JB1,B1,M2} = 12
      - S{JB1,B1,M3} = 10
      - S{JB2,LAM1,M1} = 0
      - S{JB2,B2,M2} = 2
      - L{JB1,LAM1,M1,1} = 1
      - L{JB1,LAM1,M1,2} = 4
      - L{JB1,LAM2,M1,1} = 4
      - L{JB1,LAM2,M1,2} = 6
      - L{JB1,B1,M2} = 2
      - L{JB1,B1,M3} = 0
      - L{JB2,LAM1,M1} = 0
      - L{JB2,B2,M2} = 3
      - E{JB1} = 10
      - E{JB2} = 8
      - d{JB1} = 0
      - d{JB2} = 0
      - bz{L{JB1,LAM1,M1,1}} = 0
      - bz{L{JB1,LAM1,M1,2}} = 0
      - bz{L{JB1,LAM2,M1,1}} = 0
      - bz{L{JB1,LAM2,M1,2}} = 0
      - bz{L{JB1,B1,M2}} = 1
      - bz{L{JB1,B1,M3}} = 0
      - bz{L{JB2,LAM1,M1}} = 1
      - bz{L{JB2,B2,M2}} = 0
      - X^M1 =
        - [[0 1 0 0 1]
        - [1 1 0 0 0]
        - [0 0 0 0 1]
        - [0 0 0 0 1]
        - [1 1 1 0 0]]
      - X^M2 =
        - [[1 1]
        - [0 0]]
      - X^M3 =
        - [[0]]
      - u_{M1,1} = 1
      - u_{M1,2} = 1
      - u_{M1,3} = 0
      - u_{M1,4} = 1
      - u_{M1,5} = 1
      - u_{M2,1} = 0
      - u_{M2,2} = 0
      - u_{M3,1} = 1
    2) Gurobi: -722100 en 4 min
      - S{JB1,LAM1,M1,1} = 0.0
      - S{JB1,LAM1,M1,2} = 4.0
      - S{JB1,LAM2,M1,1} = 1.0
      - S{JB1,LAM2,M1,2} = 2.0
      - S{JB1,B1,M2} = 5.0
      - S{JB1,B1,M3} = 9.0
      - S{JB2,LAM1,M1} = 2.0
      - S{JB2,B2,M2} = 7.0
      - L{JB1,LAM1,M1,1} = 3.0
      - L{JB1,LAM1,M1,2} = 1.0
      - L{JB1,LAM2,M1,1} = 3.0
      - L{JB1,LAM2,M1,2} = 1.0
      - L{JB1,B1,M2} = 3.0
      - L{JB1,B1,M3} = 1.0
      - L{JB2,LAM1,M1} = 2.0
      - L{JB2,B2,M2} = 2.0
      - E{JB1} = 10.0
      - E{JB2} = 11.0
      - d{JB1} = 1.0
      - d{JB2} = 1.0
      - bz{L{JB1,LAM1,M1,1}} = 0.0
      - bz{L{JB1,LAM1,M1,2}} = 0.0
      - bz{L{JB1,LAM2,M1,1}} = 0.0
      - bz{L{JB1,LAM2,M1,2}} = 0.0
      - bz{L{JB1,B1,M2}} = 0.0
      - bz{L{JB1,B1,M3}} = 0.0
      - bz{L{JB2,LAM1,M1}} = 0.0
      - bz{L{JB2,B2,M2}} = 0.0
      - X^M1 =
        - [[0 0 0 0 1]
        - [1 0 0 0 0]
        - [0 0 0 1 0]
        - [0 0 1 0 0]
        - [0 1 0 0 0]]
      - X^M2 =
        - [[0 1]
        - [1 0]]
      - X^M3 =
        - [[1]]
      - u_{M1,1} = 1.0
      - u_{M1,2} = 1.0
      - u_{M1,3} = 1.0
      - u_{M1,4} = 1.0
      - u_{M1,5} = 1.0
      - u_{M2,1} = 1.0
      - u_{M2,2} = 1.0
      - u_{M3,1} = 1.0


13/7:
  - restricciones 4.7.1, 4.7.1.1
  - ejecucion con restricciones 4.1.1, 4.1.2, 4.2, 4.3, 4.5, 4.6, 4.6.1, 4.7.1, 4.7.1.1 (P = 2000):
    1) Gurobi: tiempo maximo excedido (20 min): -722000.0
    2) Dwave: falta comprobar solucion obtenida
    3) "A mano": optimo de -724000


10/7:
  - correccion restriccion 4.6 (definicion de u_mk)
  - FO + restricciones 4.1.1, 4.1.2, 4.2, 4.5, 4.6, 4.6.1 (P = 2000):
  - Resultados:
    1) Gurobi: -196600 en 15.1s
      - L{JB1,LAM1,M1,1} = 0.0
      - L{JB1,LAM1,M1,2} = 4.0
      - L{JB1,LAM2,M1,1} = 0.0
      - L{JB1,LAM2,M1,2} = 4.0
      - L{JB1,B1,M2} = 0.0
      - L{JB1,B1,M3} = 4.0
      - L{JB2,LAM1,M1} = 2.0
      - L{JB2,B2,M2} = 2.0
      - bz{L{JB1,LAM1,M1,1}} = 1.0
      - bz{L{JB1,LAM1,M1,2}} = -0.0
      - bz{L{JB1,LAM2,M1,1}} = 1.0
      - bz{L{JB1,LAM2,M1,2}} = 0.0
      - bz{L{JB1,B1,M2}} = 1.0
      - bz{L{JB1,B1,M3}} = 0.0
      - bz{L{JB2,LAM1,M1}} = 0.0
      - bz{L{JB2,B2,M2}} = 0.0
      - X^M1 =
        - [[0 0 0 0 0]
        - [0 1 0 0 0]
        - [0 0 0 0 0]
        - [1 0 0 0 0]
        - [0 0 1 0 0]]
      - X^M2 =
        - [[0 0]
        - [1 0]]
      - X^M3 =
        - [[1]]
      - u_{M1,1} = 1.0
      - u_{M1,2} = 1.0
      - u_{M1,3} = 1.0
      - u_{M1,4} = 0.0
      - u_{M1,5} = 0.0
      - u_{M2,1} = 1.0
      - u_{M2,2} = -0.0
      - u_{M3,1} = 1.0


7/7:
  - restricciones 4.3, 4.5, 4.6, 4.6.1
  - analisis de penalidades y factibilidad
  - malos resultados con el simulador para varias penalidades distintas


6/7:
  - restricciones con clases (migracion a clases COMPLETA)
  - calculo de penalidad para 4.1.1, 4.1.2, 4.2: P > 1950
  - analisis de constantes para funciones cuadraticas para FO y Constraints
  - FO + restricciones 4.1.1, 4.1.2, 4.2 (P = 2000):
  - Resultados:
    1) Gurobi: -58800 (factible) en 1.7s
      - L{JB1,LAM1,M1,1} = 0.0
      - L{JB1,LAM1,M1,2} = 4.0
      - L{JB1,LAM2,M1,1} = 0.0
      - L{JB1,LAM2,M1,2} = 4.0
      - L{JB1,B1,M2} = 0.0
      - L{JB1,B1,M3} = 4.0
      - L{JB2,LAM1,M1} = 2.0
      - L{JB2,B2,M2} = 2.0
    2) SimulatedAnnealing: -43050 (no factible) con beta_range=(0.01, 7), reads=100 en 2m34s
   

5/7:
  - merge clases
  - resolucion con Gurobi
  - resolucion con simulador modificando beta_range (energia inicial y final)
  - Resultados: (solo restricciones 4.1.1, 4.1.2, 4.2)
    1) Gurobi: solucion factible de -28 en 0.6s
    2) SimulatedAnnealing: solucion factible de -28 con beta_range=(0.01, 7), reads=150 en 1m30s


4/7:
  - verificacion del valor de xtQx para las soluciones optimas
  - resultados no optimos con el simulador

3/7:
  - correccion de restriccion de cantidad
  - Resultados:
    1) restricciones {L = L'} y {a = L}: OK
    2) definicion de bz: OK
    3) problemas al imponer (i) y (ii) al mismo tiempo
    
  - reformulacion con clases / objetos

30/6:
  - agregar restricciones de L para cantidad de produccion:
    * L = L' para precedencias L' -> L
    * amount = sum_s {L_s} para tareas finales
    * definicion de bz

28/6:
  - solo con Función Objetivo.
  - Resultados:
    * todos los bz = 1 (S y L indistintos) para eliminar el costo de producción
    * los X = 0 (algunos son indistintos si los TC=0) para eliminar los costos de cambio
    * los d y E iguales a 0 para minimizar el costo de fuera de plazo


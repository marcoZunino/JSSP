# JSSP

Log de avances:
---

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


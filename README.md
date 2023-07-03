# JSSP

Log de ejecuciones:
---
28/6:
  - solo con Función Objetivo.
  Resultados:
    * todos los bz = 1 (S y L indistintos) para eliminar el costo de producción
    * los X = 0 (algunos son indistintos si los TC=0) para eliminar los costos de cambio
    * los d y E iguales a 0 para minimizar el costo de fuera de plazo

30/6:
  - agregar restricciones de L para cantidad de produccion:
    * L = L' para precedencias L' -> L
    * amount = sum_s {L_s} para tareas finales
    * definicion de bz

3/7:
  - correccion de restriccion de cantidad
  Resultados:
    (1) restricciones {L = L'} y {a = L}: OK
    (2) definicion de bz: OK
    (3) problemas al imponer (1) y (2) al mismo tiempo
    
  - reformulacion con clases / objetos



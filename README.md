# JSSP

Log de ejecuciones:
---
28/6:
  - solo con Función Objetivo:
    * todos los bz = 1 (S y L indistintos) para eliminar el costo de producción
    * los X = 0 (algunos son indistintos si los TC=0) para eliminar los costos de cambio
    * los d y E iguales a 0 para minimizar el costo de fuera de plazo

30/6:
  - agregar restricciones de L para cantidad de produccion
    * L = sum_s {L'_s} para precedentes L'
    * amount = sum_s {L_s} para tareas finales
    * definicion de bz



# P02 — RCC y GPIO por registros (pendiente)

**Estado:** por realizar. Esta carpeta no contiene resultados experimentales.

## Objetivo proyectado

Configurar y controlar PA5 usando registros de `RCC` y `GPIOA` y comparar el comportamiento con HAL.

## Registros por estudiar en RM0383

- `RCC_AHB1ENR`: habilitación del reloj del periférico GPIOA.
- `GPIOA_MODER`: modo de operación del pin.
- `GPIOA_ODR`: estado de la salida.
- `GPIOA_BSRR`: set/reset de bits de salida.

## Criterio de aceptación propuesto

Demostrar control físico del LED con evidencia de los registros y explicar las máscaras utilizadas. No confundir un código que compila con una prueba realizada en la placa.

## Documentación

Cuando termine esta práctica, usar la [plantilla general](../../docs/plantilla_practica.md) y agregar capturas reales en `evidence/`.

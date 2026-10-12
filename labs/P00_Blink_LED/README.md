# P00 — Blink LED mediante HAL

## Objetivo

Configurar el LED de usuario **LD2 (PA5)** de la NUCLEO-F411RE como salida digital y alternar su nivel lógico cada 500 ms mediante HAL.

## Elementos de hardware

- NUCLEO-F411RE / MCU STM32F411RET6.
- LD2 conectado a PA5.
- ST-LINK para programación y depuración SWD.
- Sin circuito externo.

## Configuración inicial

- PA5: `GPIO_Output`, salida push-pull, estado inicial bajo, sin pull-up/down.
- Mantener SWD habilitado.

Fragmento **didáctico** utilizado en el `while (1)` generado por CubeMX:

```c
HAL_GPIO_TogglePin(GPIOA, GPIO_PIN_5);
HAL_Delay(500);
```

`TogglePin` invierte el estado de PA5; `HAL_Delay(500)` añade aproximadamente 500 ms entre cambios. El período completo es aproximadamente **1 s (1 Hz)** en condiciones normales. No es una temporización precisa de tiempo real ni una medición de osciloscopio.

## Build y depuración

- `Ctrl + S` → `Project → Build Project`.
- Utilizar ST-LINK en `Debug` para cargar y ejecutar el `.elf`.
- **La compilación sin errores no es una validación eléctrica ni temporal.**

## Evidencia y resultado

**Observación comunicada:** la práctica Blink fue completada en la placa. Capturas de compilación, ejecución, y versiones exactas están **pendientes de incorporar**.

## Siguiente evolución

Comparar HAL con los registros RCC/`GPIOA_MODER`/`GPIOA_BSRR`; reemplazar el retraso bloqueante por un temporizador cuando corresponda.

## Código fuente

> Copiar el proyecto **real** de STM32CubeIDE (incluyendo `.ioc`, fuentes, linker, startup y drivers) dentro de `firmware/`. Este paquete es documentación inicial, no contiene un proyecto CubeIDE ya compilable.

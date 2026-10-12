# STM32F411RE — Embedded Firmware Labs

> Laboratorios progresivos de firmware embebido con **NUCLEO-F411RE (STM32F411RET6)**, C, HAL, depuración por ST-LINK/SWD y estudio de registros a través de **RM0383**.

## Objetivo

Comprender **qué hace el firmware**, **cómo se configura el hardware** y **cómo validar su funcionamiento**. Cada laboratorio incluye código fuente, explicación técnica, referencias al manual, capturas del depurador y resultados efectivamente observados.

## Plataforma

| Elemento | Descripción |
| --- | --- |
| Tarjeta | ST NUCLEO-F411RE |
| MCU | STM32F411RET6 (ARM Cortex-M4F) |
| Desarrollo | STM32CubeIDE 1.19.x / CubeMX integrado (comprobar subversión) |
| Lenguaje | C |
| Programador/depurador | ST-LINK vía SWD |
| Paquete HAL | STM32Cube FW_F4 (documentar versión exacta del proyecto) |

> **Limitación de hardware:** la STM32F411RE no integra controlador CAN/FDCAN. Se estudiará CAN por simulación u otro hardware de laboratorio compatible en una etapa posterior.

## Prácticas

| ID | Laboratorio | Aprendizaje | Estado |
| --- | --- | --- | --- |
| P00 | [Blink LED](labs/P00_Blink_LED/README.md) | GPIO de salida, HAL, build/flash/debug | Ejecutado; capturas por incorporar |
| P01 | [Entrada digital PA9](labs/P01_GPIO_Polling_PA9/README.md) | Pull-up, polling, lectura `IDR`, SFRs y Expressions | Lectura PA9 LOW/HIGH y respuesta de LED comprobadas |
| P02 | [GPIO por registros](labs/P02_GPIO_Registros/README.md) | RCC, MODER, ODR, BSRR, máscaras de bits | Por realizar |

## Cómo reproducir

1. Instalar STM32CubeIDE y el paquete STM32Cube FW_F4 correspondiente al `.ioc`.
2. Abrir/importar el proyecto situado en la carpeta `firmware/` de la práctica elegida (copiar allí los proyectos **reales** de CubeIDE; esta plantilla no incluye firmware).
3. Revisar el archivo `.ioc`, especialmente pines, reloj y configuración de depuración.
4. Compilar usando `Project → Build Project`.
5. Programar la Nucleo por ST-LINK y ejecutar/depurar.
6. Comparar los resultados con los observados en cada README.

La compilación y la prueba física son validaciones diferentes. No se atribuyen pruebas reales a prácticas aún no ejecutadas.

## Documentación técnica

- [Cómo leer registros y usar el depurador](docs/lectura_registros.md)
- [Plantilla para nuevas prácticas](docs/plantilla_practica.md)
- [STM32F411RE — Datasheet DS10314](https://www.st.com/resource/en/datasheet/stm32f411re.pdf)
- [STM32F411 — Reference Manual RM0383 y documentación oficial](https://www.st.com/en/microcontrollers-microprocessors/stm32f411/documentation.html)
- [NUCLEO-64 — User Manual UM1724](https://www.st.com/resource/en/user_manual/dm00105823.pdf)

## Convenciones

- Código bajo control de versiones; imágenes en `evidence/` y resultados medidos en el README de la práctica.
- Código **generado por CubeMX** distinguido del **código escrito manualmente**.
- Incluir `.ioc`, archivos de proyecto, linker script, fuentes y headers. Excluir binarios y datos temporales con `.gitignore`.
- Commits descriptivos: `feat(p01): read PA9 with HAL` o `docs(p01): explain IDR bit masking`.

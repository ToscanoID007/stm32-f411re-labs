\# Blink — STM32F411RE



\## Objetivo

Controlar una salida digital mediante las funciones HAL del STM32F411RE.



\## Hardware

\- NUCLEO-F411RE

\- Salida GPIO configurada como `blink\_Pin`

\- ST-LINK para programación y depuración



\## Funcionamiento

El programa establece la salida en alto durante 500 ms y después en bajo durante 500 ms, repitiendo el proceso continuamente.



```c

HAL\_GPIO\_WritePin(blink\_GPIO\_Port, blink\_Pin, GPIO\_PIN\_SET);

HAL\_Delay(500);



HAL\_GPIO\_WritePin(blink\_GPIO\_Port, blink\_Pin, GPIO\_PIN\_RESET);

HAL\_Delay(500);

```



\## Archivos principales

\- `Core/Src/main.c`: lógica principal.

\- `Core/Src/gpio.c`: configuración de GPIO.

\- `Blink.ioc`: configuración de STM32CubeMX.



\## Resultados

Se comprobó el funcionamiento de Blink en la placa. Las mediciones temporales están pendientes de documentar.


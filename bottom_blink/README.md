\# bottom\_blink — Lectura digital con STM32



\## Objetivo



Leer una entrada digital y controlar un LED utilizando la biblioteca HAL de STM32.



\## Configuración



\- \*\*Entrada:\*\* `Buttom\_Pin`, configurada como entrada con resistencia pull-up.

\- \*\*Salida:\*\* `LED\_Pin`, configurada como salida push-pull.

\- \*\*Microcontrolador:\*\* STM32F411RE.



\## Funcionamiento



El microcontrolador consulta continuamente el estado de la entrada.



```c

state\_buttom = HAL\_GPIO\_ReadPin(Buttom\_GPIO\_Port, Buttom\_Pin);



if (state\_buttom == GPIO\_PIN\_SET) {

&#x20;   HAL\_GPIO\_WritePin(LED\_GPIO\_Port, LED\_Pin, GPIO\_PIN\_SET);

} else {

&#x20;   HAL\_GPIO\_WritePin(LED\_GPIO\_Port, LED\_Pin, GPIO\_PIN\_RESET);

}



HAL\_Delay(50);

```



Cuando la entrada está en alto, el LED se activa. Cuando está en bajo, se desactiva.



\## Conceptos utilizados



\- GPIO de entrada y salida.

\- Resistencias pull-up.

\- Lectura digital mediante HAL.

\- Polling.

\- Temporización mediante `HAL\_Delay()`.



\## Código fuente



\- `Core/Src/main.c`: funcionamiento del programa.

\- `Core/Src/gpio.c`: configuración de los pines.

\- `bottom\_blink.ioc`: configuración de STM32CubeMX.


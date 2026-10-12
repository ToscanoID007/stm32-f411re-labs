# Lectura de registros STM32F411RE

## ¿Qué documentos consultar?

| Documento | Responde a... |
| --- | --- |
| Datasheet **DS10314** | Pines, especificaciones eléctricas, capacidades y memorias |
| Reference Manual **RM0383** | Direcciones, offsets, bits y funcionamiento de registros |
| User Manual **UM1724** / esquema de la Nucleo | ¿A qué componente físico de la tarjeta va conectado el pin? |

## Ejemplo: `GPIOA_IDR` (registro de entrada)

En el **RM0383**, la descripción de `GPIOx_IDR` indica un **offset de `0x10`** desde la dirección base del puerto. Para GPIOA:

- Dirección base GPIOA: `0x40020000`.
- Offset de IDR: `0x10`.
- Dirección de IDR: `0x40020010`.

Para GPIOC, el mismo offset produce `0x40020810`. **PA9 no es PC9:** el nombre del puerto forma parte de la identificación del pin.

```c
// Leer únicamente PA9. El miembro IDR está representado por una
// estructura de registros CMSIS, que accede al periférico en memoria.
uint32_t estado_pa9 = (GPIOA->IDR >> 9U) & 1U;
```

- `GPIOA`: puntero a los registros del puerto A.
- `->`: acceso a un campo de la estructura apuntada.
- `IDR`: campo del registro Input Data Register.
- `>> 9U`: desplaza el contenido 9 posiciones a la derecha; `U` indica literal unsigned.
- `& 1U`: AND bit a bit que conserva solo el bit 0 después del desplazamiento.
- Resultado: `0` o `1` sin modificar el registro.

Equivalente con una máscara:

```c
uint32_t nivel_alto = (GPIOA->IDR & (1UL << 9U)) != 0U;
```

- `1UL << 9U` construye la máscara `0x0200`.
- `&` no es lo mismo que `&&` (AND lógico).
- Leer IDR es diferente de escribir ODR/BSRR.

## Vistas de STM32CubeIDE

| Vista | Cuándo utilizarla |
| --- | --- |
| Variables | Ver el valor almacenado por el firmware en una variable C |
| SFRs | Inspeccionar registros reales de periféricos como GPIOA_IDR |
| Expressions | Evaluar expresiones C como `(GPIOA->IDR >> 9U) & 1U` al depurar |

**Atención:** mientras el procesador esté detenido, una variable no cambia por sí sola; conserva el valor del último cálculo. Algunos registros pueden requerir actualizar manualmente la vista.

## Próxima etapa

Estudiar `RCC_AHB1ENR` para habilitar GPIOA, `GPIOA_MODER` para modo del pin y `GPIOA_BSRR` para cambiar una salida. Leer la sección correspondiente de RM0383 antes de programar registros.

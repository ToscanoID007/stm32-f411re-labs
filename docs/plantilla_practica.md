# PXX — [Nombre de la práctica]

## Objetivo y criterio de aceptación

**Objetivo:** [comportamiento observable]

**Aprobación:** [qué se medirá, con qué herramienta y qué valor esperamos]

## Hardware, entorno y configuración

| Elemento | Valor |
| --- | --- |
| MCU / revisión placa | [confirmar] |
| IDE / HAL / compilador | [versiones comprobadas] |
| Pines | [puerto, pin, modo, pull-up/down, función alternativa] |
| Conexiones | [diagrama de bajo voltaje y referencia GND] |

## Referencias leídas

- Datasheet: [apartado exacto]
- RM0383: [sección y registro, campo y offset]
- UM1724 / esquema: [sección]

## Diseño e implementación

[Por qué se eligió polling/IRQ/DMA, qué parte viene de CubeMX y cuál fue escrita a mano.]

```c
// Fragmento REPRESENTATIVO de código realmente implementado
```

## Interpretación del registro

| Registro | Base + offset | Bits relevantes | Evidencia |
| --- | --- | --- | --- |
| [registro] | [dirección] | [bits] | [captura] |

Explicar operadores, máscaras, significado físico del valor leído y diferencias HAL/registros.

## Validación real

| Caso | Entrada | Resultado esperado | Resultado observado | Estado |
| --- | --- | --- | --- | --- |
| 1 | [condición] | [valor] | [observación] | Pendiente |

## Capturas y pruebas

![Texto alternativo descriptivo](evidence/nombre.png)

## Problemas encontrados y diagnóstico

[Error, hipótesis, herramienta utilizada, comprobación, solución.]

## Conclusiones y mejoras pendientes

[Qué se aprendió, limitaciones y siguiente reto.]

## METEO Módulo Meteorológico
(versión original 2012 - updated 03.2022)

### Introducción
La placa METEO de [L&R Ingeniería](https://www.lyringenieria.com.ar/language/es/)  es una placa periférica orientada a su utilización en conjunto con el módulo de CPU [CL2bm1-AVR](https://www.lyr-ing.com/Embedded/LyRAVR_CyEn.htm), y funciona como unidad de adquisición de datos meteorológicos en un formato compatible con gabinetes para riel DIN (modelo DINR416). El primer desarrollo se realizó entre 2005 y 2007 (Ver paper XII-RPIC 2007, con Ing. N.Cortez en **/docs**) para un sistema del proyecto PERMER.   Se basa en un controlador [CY8C29466](https://www.infineon.com/cms/en/product/microcontroller/legacy-microcontroller/legacy-8-bit-16-bit-microcontroller/psoc-1/cy8c29x66/) de la línea PSoC 1 (Programmable System-on-Chip, de Infineon/Cypress) - [Ref1](https://github.com/LyRIng/PlacaM4-E/blob/master/README.md#Referencias) y soporta una interfaz para programación ISP (In-System Programming). Esta familia de controladores cuenta internamentecon módulos configurables analógicos y digitales, lo cual les da una gran flexibilidad para adaptarse a cambios de requerimientos y diseño. Un diagrama en bloques de la placa METEO y su esquemático se encuentra disponible en el directorio **/schem** del presente repositorio. El firmware permite una lectura muy precisa de la frecuencia en los rangos típicos de los sensores anemométricos, y el hardware permite el acondicionamiento de las señales para sensores típicos como los NRG o Thies. Además tiene entradas analógicas con ADC de 12 bits para medición de dirección de viento, temperatura, y presión barométrica. La salida de datos se transmite cada 1 segundo en una trama serial (en general convertida a RS485, @38400 baud) con encabezado, terminación y checksum para ser validada por la CPU receptora. 


En el directorio **/docs** se realiza una descripción del funcionamiento del sistema y su calibración. 

### Programación
Se encuentra pendiente la incorporación del código fuente de versiones abiertas de este módulo meteorológico.

### Referencias
[Ref1 - Infineon/Cypress-PSoC1-CY8C29466] (https://www.infineon.com/cms/en/product/microcontroller/legacy-microcontroller/legacy-8-bit-16-bit-microcontroller/psoc-1/cy8c29x66/)

[Ref2 - PSoC Designer v5.4] (https://www.infineon.com/cms/en/design-support/tools/sdk/psoc-software/psoc-designer/)

[Ref3 - LyR AVR+Cypress] (http://www.lyr-ing.com/Embedded/LyRAVR_CySp.htm)


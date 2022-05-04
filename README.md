## METEO Módulo Meteorológico / Meteorological Module
(versión original 2012 - updated 05.2022)

### Introducción / Introduction
(SP) La placa METEO de [L&R Ingeniería](https://www.lyringenieria.com.ar/language/es/)  es una placa periférica orientada a su utilización en conjunto con los módulos de CPU [CL2bm1-AVR](https://www.lyr-ing.com/Embedded/LyRAVR_CyEn.htm) y CL3, y funciona como unidad de adquisición de datos meteorológicos (Viento, Presión Atmosférica y Temperatura) en un formato compatible con gabinetes para riel DIN (modelo DINR416). El primer desarrollo se realizó entre 2005 y 2007 (Ver paper XII-RPIC 2007, con Ing. N.Cortez en **/docs**) para un sistema del proyecto PERMER.   Se basa en un controlador [CY8C29466](https://www.infineon.com/cms/en/product/microcontroller/legacy-microcontroller/legacy-8-bit-16-bit-microcontroller/psoc-1/cy8c29x66/) de la línea PSoC 1 (Programmable System-on-Chip, de Infineon/Cypress) - [Ref1](https://github.com/LyRIng/PlacaM4-E/blob/master/README.md#Referencias) y soporta una interfaz para programación ISP (In-System Programming). Esta familia de controladores cuenta internamentecon módulos configurables analógicos y digitales, lo cual les da una gran flexibilidad para adaptarse a cambios de requerimientos y diseño. Un diagrama en bloques de la placa METEO y su esquemático se encuentra disponible en el directorio **/schem** del presente repositorio. El firmware permite una lectura muy precisa de la frecuencia en los rangos típicos de los sensores anemométricos, y el hardware permite el acondicionamiento de las señales para sensores típicos como los NRG o Thies. Además tiene entradas analógicas con ADC de 12 bits para medición de dirección de viento, temperatura, y presión barométrica. La salida de datos se transmite cada 1 segundo en una trama serial (en general convertida a RS485, @38400 baud) con encabezado, terminación y checksum para ser validada por la CPU receptora.

(EN) The METEO board by [L&R Ingeniería](https://www.lyringenieria.com.ar/language/en/) is a peripheral board  designed for use with the [CL2bm1-AVR](https://www.lyr-ing.com/Embedded/LyRAVR_CyEn.htm) or CL3 CPU boards. It works as a remote data acquisition unit of environmental data (wind intensity and direction, temperature and barometric pressure) in a DIN-rail compatible format (model DINR416). The first development was finished by 2007 (See paper XII-RPIC 2007, with Ing. N.Cortez in **/docs**) for a PERMER funded project. It is based on a PSoC 1 [CY8C29466](https://www.infineon.com/cms/en/product/microcontroller/legacy-microcontroller/legacy-8-bit-16-bit-microcontroller/psoc-1/cy8c29x66/) microcontroller  (Programmable System-on-Chip, by Infineon/Cypress) - [Ref1](https://github.com/LyRIng/PlacaM4-E/blob/master/README.md#Referencias). I supports a low cost ISP (In-System Programming) to USB interface by Infineon. This family of microcontrollers has a number of internal analog and digital modules which are software-configurable. A block diagram and schematic of the METEO board are available in the **/schem** directory of this repo. The firmware allows for a highly accurate reading of frequencies in the range of typical wind sensors, and the input circuitry can be configured for signal conditioning of typical sensors such as  NRG or Thies. Its analog inputs use a 12-bit ADC for measuring wind-direction (example NRG#200P), temperature (example NRG110S) and barometric pressure (example NRG BP20). Data output is transmitted every one second as a serial packet (usually converted to RS485, @38400 baud) with a header, termination and checksum to be validated by the main CPU board.


En el directorio **/docs** se realiza una descripción del funcionamiento del sistema y su calibración. 

### Programación
Se encuentra pendiente la incorporación del código fuente de versiones abiertas de este módulo meteorológico.

### Referencias
[Ref1 - Infineon/Cypress-PSoC1-CY8C29466] (https://www.infineon.com/cms/en/product/microcontroller/legacy-microcontroller/legacy-8-bit-16-bit-microcontroller/psoc-1/cy8c29x66/)

[Ref2 - PSoC Designer v5.4] (https://www.infineon.com/cms/en/design-support/tools/sdk/psoc-software/psoc-designer/)

[Ref3 - LyR AVR+Cypress] (http://www.lyr-ing.com/Embedded/LyRAVR_CySp.htm)


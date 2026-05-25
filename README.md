## METEO Meteorological Module (Módulo Meteorológico)
(original version 2012 - updated 05.2026)

### Introduction 
(EN) The METEO board by [L&R Ingeniería](https://www.lyringenieria.com.ar/language/en/) is a peripheral board originally designed for use with the [CL2bm1-AVR](https://www.lyr-ing.com/Embedded/LyRAVR_CyEn.htm) (https://github.com/LyRIng/CL2bm1) or CL3 (STM32F4) CPU boards (https://github.com/LyRIng/CL3board). Between 2025 and 2026 interfaces for STM35H573-I-DK under FreeRTOS and AzureRTOS have been developed, including demonstrations for the ITTIA-DB-Lite database (https://github.com/LyRIng/stm32-ittia-meteo) coupled with ITTIA Analitica software (https://www.ittia.com/workshops/weather-station-ai).  The desing has focused on reliability,  and modules have been continuously working for over a decade in harsh conditions at various sites. METEO works as a remote data acquisition unit of environmental data (wind intensity and direction, temperature and barometric pressure) in a DIN-rail compatible format (model DINR416). The first prototypes were finished in 2007 (See paper XII-RPIC 2007, with Ing. N.Cortez in **/docs**) for a PERMER funded project, and then deployed since 2012 at the INTI-Wind Turbine Test Site (see: https://www.lidsen.com/journals/jept/jept-07-02-009) 
METEO is based on a PSoC 1 [CY8C29466](https://www.infineon.com/cms/en/product/microcontroller/legacy-microcontroller/legacy-8-bit-16-bit-microcontroller/psoc-1/cy8c29x66/) microcontroller  (Programmable System-on-Chip, by Infineon/Cypress) - [Ref1](https://github.com/LyRIng/PlacaM4-E/blob/master/README.md#Referencias). It supports a low cost ISP (In-System Programming) to USB interface by Infineon. This family of microcontrollers has a number of internal analog and digital modules which are software-configurable. A block diagram and schematic of the METEO board are available in the **/schem** directory of this repo. The firmware allows for a highly accurate reading of frequencies in the range of typical wind sensors, and the input circuitry can be configured for signal conditioning of typical sensors such as  NRG or Thies. Its analog inputs use a 12-bit ADC for measuring wind-direction (example NRG#200P), temperature (example NRG110S) and barometric pressure (example NRG BP20). Data output is transmitted every one second as a serial packet (usually converted to RS485, @38400 baud) with a header, termination and checksum to be validated by the main CPU board.

A complete description of the internals and calibration is avaialable in **/docs** , and a Firmware flow diagram in C para PSoC-Designer is now available in **/docs/FirmwareFlow_v20**. 

Pre-programmed METEO boards, with or without DIN-compatible cases and metal enclosures, are available from: https://www.lyringenieria.com.ar/language/en/productos/meteo-module-for-meteorological-measurements/
The TTL-to-RS485 interface is available from:
https://www.lyringenieria.com.ar/language/en/productos/rs485-brd-rs-485-rs-232-ttl-board-module-v2/

### Programming
Source code and programming tools are available upon request and previous registration for a small fee.

### References
[Ref1 - Infineon/Cypress-PSoC1-CY8C29466] (https://www.infineon.com/cms/en/product/microcontroller/legacy-microcontroller/legacy-8-bit-16-bit-microcontroller/psoc-1/cy8c29x66/)

[Ref2 - PSoC Designer v5.4] (https://www.infineon.com/cms/en/design-support/tools/sdk/psoc-software/psoc-designer/)

[Ref3 - LyR AVR+Cypress] (http://www.lyr-ing.com/Embedded/LyRAVR_CySp.htm)
 
### (SP) Introducción 
 La placa METEO de [L&R Ingeniería](https://www.lyringenieria.com.ar/language/es/) es una placa periférica diseñada originalmente para su uso con las placas CPU [CL2bm1-AVR](https://www.lyr-ing.com/Embedded/LyRAVR_CyEn.htm) (https://github.com/LyRIng/CL2bm1) o CL3(STM32F4) (https://github.com/LyRIng/CL3board). Entre 2025 y 2026 se desarrollaron interfaces para STM35H573-I-DK bajo FreeRTOS y AzureRTOS, incluyendo demostraciones para la base de datos ITTIA-DB-Lite (https://github.com/LyRIng/stm32-ittia-meteo) en conjunto con el software ITTIA Analitica (https://www.ittia.com/workshops/weather-station-ai). Se ha buscado un diseño de alta confiabilidad y  los módulos han funcionado de forma continua durante más de una década en condiciones adversas en diversos emplazamientos. METEO funciona como una unidad de adquisición de datos meteorológicos (Viento, Presión Atmosférica y Temperatura) en un formato compatible con gabinetes para riel DIN (modelo DINR416). Los primeros prototipos fueron terminados en 2007 (ver artículo XII-RPIC 2007, con el Ing. N. Cortez en **/docs**) para un proyecto financiado por PERMER, y posteriormente desplegados desde 2012 en el Sitio de Ensayo de Aerogeneradores del INTI (ver: https://www.lidsen.com/journals/jept/jept-07-02-009)   
METEO se basa en un controlador [CY8C29466](https://www.infineon.com/cms/en/product/microcontroller/legacy-microcontroller/legacy-8-bit-16-bit-microcontroller/psoc-1/cy8c29x66/) de la línea PSoC 1 (Programmable System-on-Chip, de Infineon/Cypress) - [Ref1](https://github.com/LyRIng/PlacaM4-E/blob/master/README.md#Referencias) y soporta una interfaz para programación ISP (In-System Programming). Esta familia de controladores cuenta internamentecon módulos configurables analógicos y digitales, lo cual les da una gran flexibilidad para adaptarse a cambios de requerimientos y diseño. Un diagrama en bloques de la placa METEO y su esquemático se encuentra disponible en el directorio **/schem** del presente repositorio. El firmware permite una lectura muy precisa de la frecuencia en los rangos típicos de los sensores anemométricos, y el hardware permite el acondicionamiento de las señales para sensores típicos como los NRG o Thies. Además tiene entradas analógicas con ADC de 12 bits para medición de dirección de viento, temperatura, y presión barométrica. La salida de datos se transmite cada 1 segundo en una trama serial (en general convertida a RS485, @38400 baud) con encabezado, terminación y checksum para ser validada por la CPU receptora.

En el directorio **/docs** se realiza una descripción del funcionamiento del sistema y su calibración,
se ha agregado un diagrama de flujo del Firmware en C para PSoC-Designer en **/docs/FirmwareFlow_v20**.

Los módulos METEO pre-programados, con o sin carcasas DIN R416 y gabinetes metálicos, están disponibles en: https://www.lyringenieria.com.ar/productos/modulo-meteo-para-mediciones-meteorologicas/
La interfaz TTL-a-RS485 se encuentra disponible en:
https://www.lyringenieria.com.ar/productos/rs485-brd-placa-y-o-modulo-rs-485-rs-232-ttl/

### Programación
Se encuentra disponible el código fuente de versiones de este módulo meteorológico, previo registro y por una módica tarifa.

### Referencias
[Ref1 - Infineon/Cypress-PSoC1-CY8C29466] (https://www.infineon.com/cms/en/product/microcontroller/legacy-microcontroller/legacy-8-bit-16-bit-microcontroller/psoc-1/cy8c29x66/)

[Ref2 - PSoC Designer v5.4] (https://www.infineon.com/cms/en/design-support/tools/sdk/psoc-software/psoc-designer/)

[Ref3 - LyR AVR+Cypress] (http://www.lyr-ing.com/Embedded/LyRAVR_CySp.htm)


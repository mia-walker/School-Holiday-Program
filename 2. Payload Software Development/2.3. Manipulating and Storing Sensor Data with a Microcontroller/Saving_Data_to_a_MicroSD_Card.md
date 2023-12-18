### Saving Data to A MicroSD Card

## Resources:
- Tutorial by kiwih: "Tutorial: An SD card over SPI using STM32CubeIDE and FatFS" https://01001000.xyz/2020-08-09-Tutorial-STM32CubeIDE-SD-card/.
- https://controllerstech.com/sd-card-using-spi-in-stm32/
- "SPI Signal Names" by SparkFun Electronics: https://www.sparkfun.com/spi_signal_names

## Required Software & Equipment
- BinarX Rocket Payload Microcontroller Board
- MicroSD Card
- STM32CubeIDE
- STLink STM32 Dubugger & Programmer

## Procedure

1. Configure the SPI2 periphral for "Full Duplex Controller" (formerly known as "Full Duplex Master") with no chip select ("CS") signal (sometimes formerly referred to as slave select, "SS" or "NSS")

    ![SPI2 Pins for MicroSD](./SPI2_pins_for_microSD.png)

1. Set the "Data Size" to "8 bits":

    ![8 Bit Data Size](./8_bit_data_size.png)

1. Configure PB12 as a "GPIO Output" and give it the label "uSD_CS":

    ![uSD CS Pin GPIO Mode](uSD_CS_pin_GPIO_mode.png)

1. Set the prescaler to 128, which with the 16 MHz, HSE oscillator should give you a baud rate of 125 KBits/s:

    ![SPI Prescaler](SPI_prescaler.png)

1. Move over to the "Clock Configuration" tab, and click "Resolve Clock Issues" if needed.

1. In the left hand side, scroll down to "Middleware and Software Packs", click on FATFS:

    ![FATFS Middleware](FATFS_middleware.png)

    then enable it by ticking "User-defined" in the middle pane:

    ![FATFS User Defined Tick Box](FATFS_user_defined.png)

1. Save, and generate code.

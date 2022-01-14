# Electret Microphone software

This is a home made microphone project, more info about the whole project [here](https://github.com/Vaarai/USB_Microphone)

The code is based on the USB Audio Class project provided by STM32CubeMx

## Description

This microphone provide a 48khz / 16-bit audio stream with a 1ms delay.
The audio is oversampled at 768kHz => 16x 48kHz

The STM32 code use the followings features :
- An ADC channel that run conversions at 768kHz
- An oversampling buffer that is acircular buffer handling the ADC conversion result
- A DMA that carry ADC conversion data to the oversampling buffer
- An ADC conversion callback that proceed to a decimation over the oversampling buffer to increase the precision
- A two packet wide buffer where the conversion callback store the decimation result (On half of the buffer is send while the other serve to store decimation incoming data)
- The STM32 provided USB driver that send audio packet over USB Audio Class (1000 packets per second)

## Installation

Work in progress !!!
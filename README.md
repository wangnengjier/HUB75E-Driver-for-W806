# HUB75E-Driver for W806 
Oct 13 2022
Author: Wangnengjie
wangnengjie@hotmail.com
W806 is a powerful microcontroller. The following is a summary.

-32-bit XT804 processor, frequency up to 240MHz, built-in DSP, FPU and security engine
B-uilt-in 1MB Flash, 288KB RAM
-Integrated PSRAM interface, supports up to 64MB external PSRAM memory
-6-channel UART high-speed interface
-4-channel 16-bit ADC, the highest sampling rate is 1KHz
-1 high-speed SPI interface (slave interface), supports up to 50MHz
-master/slave SPI interface
-1 SDIO_HOST interface, supports SDIO2.0, SDHC, MMC4.2
-1 SDIO_DEVICE, supports SDIO2.0, the maximum throughput rate is 200Mbps
-1 I²C controller
-Integrated GPIO controller supporting up to 44 GPIOs
-5 channel PWM interface
-1 Duplex I²S controller
-LCD controller, supports 4x32 interface
-1 7816 interface
-15 Touch Sensors integrated

Here's another guy post his chip board:   https://hackaday.io/page/11837-getting-started-with-w806-240mhz-32-bit-mcu

HUB75E RGB LED Matrix Panel is popular in the life. W806 lib is similar like STM32 HAL lib. so we forked Driver from Thakaa's project in order to adapting for W806. 
```C


int main(void) {

	HUB75E_Init();
	HUB75E_setDisplayBuffer(myBitmap); //Each bit represent each pixels. 1 Byte contains 8 pixels 
	HUB75E_setDisplayBrightness(BrightnessLevel1);
	HUB75E_setDisplayColor(Blue);
	HUB75E_setAddressingMode(HUB75EAddressingModeABCDE);
	while(1) {
 	   HUB75E_displayBufferPixels();
        }
}

```
**Configurations**

HORIZONTAL_PIXELS - HUB75ELib.h (Default to 64).  
VERTICAL_PIXEL - HUB75ELib.h (Default to 64).



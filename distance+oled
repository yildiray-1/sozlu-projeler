from hcsr04 import HCSR04
from machine import Pin, SoftI2C
import ssd1306
from time import sleep

sensor = HCSR04(trigger_pin=5, echo_pin=18, echo_timeout_us=10000)
i2c = SoftI2C(scl=Pin(22), sda=Pin(21))

oled_width = 128
oled_height = 64
oled = ssd1306.SSD1306_I2C(oled_width, oled_height, i2c)


while True:
    oled.fill(0)
    distance = sensor.distance_cm()
    oled.text(("distance:"),0 ,0)
    oled.text(str(distance),0 ,10)
    oled.show()
    sleep(0.3)

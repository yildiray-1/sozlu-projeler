from machine import Pin
from time import sleep
import dht 
from machine import Pin, SoftI2C
import ssd1306


i2c = SoftI2C(scl=Pin(22), sda=Pin(21))

oled_width = 128
oled_height = 64
oled = ssd1306.SSD1306_I2C(oled_width, oled_height, i2c)


sensor = dht.DHT11(Pin(4))

while True:
  try:
    oled.fill(0)
    sleep(0.5)
    sensor.measure()
    temp = sensor.temperature()
    hum = sensor.humidity()
    temp_f = temp * (9/5) + 32.0
    oled.text(str('Temperature: %3.1f C' %temp),0 ,0)
    oled.text(str('Temperature: %3.1f F' %temp_f),0 ,10)
    oled.text(str('Humidity: %3.1f %%' %hum),0 ,20)
    oled.show()
  except OSError as e:
    oled.text(str('Failed to read sensor.'),0 ,0)
    oled.show()

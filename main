from machine import Pin, I2C
from ssd1306 import SSD1306_I2C
import time
import machine, utime
import gfx
import random



i2c=I2C(0,sda=Pin(0), scl=Pin(1), freq=400000)
oled = SSD1306_I2C(128, 32, i2c)

graphics = gfx.GFX(128, 32, oled.pixel)

sensor_temp = machine.ADC(4)
conversion_factor = 3.3 / (65535)


while True:
    oled.fill(0)
    
    
    
    reading_in_volts = sensor_temp.read_u16() * conversion_factor
    temperature = 27 - (reading_in_volts - 0.706)/0.001721
    f = str(round(temperature * (9/5) + 32))
    
    oled.text('T:' + f + 'F', 0, 0, 1)
        
    oled.rect(0, 9, 128, 23, 1) # BOTTOM RECT
    oled.rect(44, 0, 40, 8, 1) #TOP RECT
    
    oled.fill_rect(47, 2, 10, 4, 1)
    oled.fill_rect(59, 2, 10, 4, 1)
    oled.fill_rect(71, 2, 10, 4, 1)
    
    
    mylist1 = [1, 0]
    
    number1 = (random.choice(mylist1)) # SPAZ CIRCLE NUM GEN
    number2 = (random.choice(mylist1))
    number3 = (random.choice(mylist1))
    number4 = (random.choice(mylist1))
    number5 = (random.choice(mylist1))
    
    
    graphics.fill_circle(90, 4, 3, 1) 
    graphics.fill_circle(90, 4, 2, number1)    # SPAZ CIRCLES
    
    graphics.fill_circle(98, 4, 3, 1)
    graphics.fill_circle(98, 4, 2, number2)
    
    graphics.fill_circle(106, 4, 3, 1)
    graphics.fill_circle(106, 4, 2, number3)
    
    graphics.fill_circle(114, 4, 3, 1)
    graphics.fill_circle(114, 4, 2, number4)
    
    graphics.fill_circle(122, 4, 3, 1)
    graphics.fill_circle(122, 4, 2, number5)
    
    num_list = [number1, number2, number3, number4, number5]
     
    if num_list == [1, 1, 1, 1, 1]:
        
        mylist2 = range(2, 126)
        
        mylist3 = range(10, 21)
        
        x1 = (random.choice(mylist2))
        x2 = (random.choice(mylist2))
        x3 = (random.choice(mylist2))
        
        y1 = (random.choice(mylist3))
        y2 = (random.choice(mylist3))
        y3 = (random.choice(mylist3))
        
        graphics.fill_triangle(x1, y1, x2, y2, x3, y3, 1)
        
        oled.show()
        time.sleep(1)
 
    oled.show()

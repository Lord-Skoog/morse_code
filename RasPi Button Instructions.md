How to make a buzzer and button thing with a raspberry pi and breadboard

Materials:
1 Raspberry pi and GPIO pin connector 
1 breadboard 
6 M to F wires
1 key studio button 
1 key studio active buzzer 


STEP 1: Setting up the circuit
On your  bread board make the following circuit:  
![![[IMG_8442.jpg]]]
Wire the "S" to GPIO pin 21


![![[IMG_8443.jpg]]]
Wire the "S" wire to GPIO pin 16

For both wire the "G" to ground and "V" to voltage respectively 

STEP 2:
Write a python script on your RasPi, I recommend naming it buzz.py 
Here is mine :
...................................................
	
import RPi.GPIO as GPIO  
import time  
  
GPIO.setmode(GPIO.BCM)  
GPIO.setup(16, GPIO.OUT)  
GPIO.setup(21, [GPIO.IN](http://GPIO.IN))  
GPIO.setwarnings(False)  
p = GPIO.PWM(16, 100)  
  
i = GPIO.input(21)  
while True:  
if GPIO.input(21) == GPIO.LOW:  
p.start(50)  
elif GPIO.input(21) == GPIO.HIGH:  
p.stop()  
  
GPIO.cleanup()

.....................................................
it should be preinstalled but you may have to pip Install time using the command
" pip install time "

STEP 3:
Run the program in your terminal
'python buzz.py'
any time you press the button the beeper should beep.
to end the beeping press 'CTRL C'
SYSTEM DESCIPTION:
This system is a lighting system that is implemented by two LEDs, one
represents for the porch light and one represent for the hallway light, and both are 
controlled by a push button. All these devises are connected to the Arduino Nano 33 IoT
to run.

HOW IT WORKS:
When the button is pressed, both LEDs turns on. After 30 seconds and 60 seconds,
the porch light and hallway light turns off respectively. 

CODE EXPLAINATION:
First, we defines digital pins for all the accessories, including button (pin 4),
porch light (red LED, pin 2), hallway light (blue LED, pin 3), and defines a 
variable names buttonState to read the button status. Then, the code is 
structured into two main parts: setup() and loop(). The setup() function is used
for code that only need to run once at the start, then here, we initialize
pin modes with LED pins as OUTPUT and button pin as INPUT_PULLUP. This is simply because 
by setting the LEDs pin as OUTPUT, the Arduino sends a signal to controlled the LEDs 
on and off while setting the button pin as INPUT, the Arduino receives a signal 
from the outside world. Besides, loop() function gives continuous execution, then 
it contains the main logic of the program, including read button state by using digitalRead,
check condition if the button is pressed (LOW), the lights turn on, if not, the lights
turn of by using digitalWrite. In this program, we also use delay to keep the lights
turn on after 30 and 60 seconds.

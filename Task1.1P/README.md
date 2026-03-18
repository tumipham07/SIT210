SYSTEM DESCIPTION:
This system is a lighting system that is implemented by two LEDs, one
represents for the porch light and one represent for the hallway light, and both are 
controlled by a push button. All these devises are connected to the Arduino Nano 33 IoT
to run.

HOW IT WORKS:
When the button is pressed, both LEDs turns on. After 30 seconds and 60 seconds,
the porch light and hallway light turns off respectively. 

CODE EXPLAINATION:
First, we define digital pins for all the accessories, including the button (pin 4), porch light (red LED, pin 2), and hallway light (blue LED, pin 3). Then, we also declare variables including buttonState to read the button status, porchTimer and hallwayTimer to track time using the millis() function, and porchState and hallwayState as boolean variables to track whether each light is currently on or off.

Next, The code is structured into two main parts: setup() and loop(). For the setup() function, it runs once at the start of the program. Here, we initialize pin modes with LED pins as OUTPUT and the button pin as INPUT_PULLUP. By setting the LED pins as OUTPUT, the Arduino sends signals to control the LEDs turning on and off. Setting the button pin as INPUT_PULLUP enables the internal pull-up resistor, so the Arduino receives a HIGH signal when the button is not pressed and a LOW signal when it is pressed. We also initialize both LEDs to be turned off at the start using digitalWrite(porchPin, LOW) and digitalWrite(hallwayPin, LOW).
 For the loop() function, it runs continuously and contains the main logic of the program. It reads the button state using digitalRead(buttonPin) and checks if the button is pressed (LOW). When the button is pressed, both LEDs turn on using digitalWrite(), the state variables (porchState and hallwayState) are set to true to indicate the lights are on, and timers are recorded using millis().

Instead of using delay(), which would block the program from doing anything else, this code uses millis(). After the button press logic, the loop() calls two custom functions: porchLight() and hallwayLight(). The porchLight() function checks if the porch light is on (porchState is true) AND if 30 seconds (30000 milliseconds) have passed since the porch timer was set. If both conditions are true, it turns off the porch light and updates porchState to false. It is similar to the hallwayLight() function, checking if 60 seconds (60000 milliseconds) have passed before turning off the hallway light.

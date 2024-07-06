 int tiltPin = 2;             // Tilt switch module connected to digital pin 2
int ledPin = 13;             // Built-in LED connected to digital pin 13

void setup() {
  pinMode(ledPin, OUTPUT);   // Sets the digital pin as output
  pinMode(tiltPin, INPUT_PULLUP);   // Sets the digital pin as input with internal pull-up resistor
  Serial.begin(9600);        // Starts serial communication at 9600 baud
}

void loop() {
  int tiltState = digitalRead(tiltPin);  // Read the state of the tilt switch value
  Serial.println(tiltState);  // Print the state to the Serial Monitor to observe changes

  if (tiltState == LOW) {     // If the tilt switch is tilted (active LOW)
    digitalWrite(ledPin, HIGH);  // Turns on the LED
  } else {
    digitalWrite(ledPin, LOW);   // Turns off the LED when not tilted
  }

  delay(10);  // Short delay to reduce the responsiveness for easier observation
}

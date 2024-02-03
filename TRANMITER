#include <SoftwareSerial.h>

const byte HC12RxdPin = 11;                  // Recieve Pin on HC12
const byte HC12TxdPin = 10;                  // Transmit Pin on HC12
int charsRead;
 char input[10];
SoftwareSerial HC12(10,11); // Create Software Serial Port

void setup() {
  Serial.begin(9600);                       // Open serial port to computer
  HC12.begin(9600);                         // Open serial port to HC12
}

void loop() {
  if(HC12.available()){                     // If Arduino's HC12 rx buffer has data
    Serial.print(HC12.read());              // Send the data to the computer
    }
   while (Serial.available()) {
    charsRead = Serial.readBytesUntil('\n', input, sizeof(input) - 1);  //gets bytes until Enter pressed
    input[charsRead] = NULL;   // This makes it a string
   int h= Serial.print(input);
    HC12.print(h);
}

}

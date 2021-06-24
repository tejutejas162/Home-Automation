# Home-Automation

Home automation system using a simple Android app, which you can use to control electrical appliances with clicks or voice command. Commands are sent via Bluetooth to Arduino UNO. So you need not get up to switch on and off the device while watching a movie or doing some work

here is the arduino code.


#define RELAY_ON 0
#define RELAY_OFF 1

#define RELAY_1  4

char data = 0;

void setup() {

// Set pin as output.

pinMode(RELAY_1, OUTPUT);

// Initialize RELAY1 = off. So that on reset it would be off by default

digitalWrite(RELAY_1, RELAY_OFF);

Serial.begin(9600);

Serial.print(“Type: 1 to turn on the bulb. 0 to turn it off!”);

}

void loop() {

 if (Serial.available() > 0) {

data = Serial.read();      //Read the incoming data and store it into variable data

  Serial.print(data);        //Print Value inside data in Serial monitor

Serial.print(“\n”);        //New line

if(data == ‘1’){

digitalWrite(RELAY_1, RELAY_ON);

Serial.println(“Bulb is now turned ON.”);

}

else if(data == ‘0’){

digitalWrite(RELAY_1, RELAY_OFF);

 Serial.println(“Bulb is now turned OFF.”);

}

}

}


Video link: https://drive.google.com/file/d/1znx6DmCyGM4CHYYpiwC59Zss8oNdEv4Y/view?usp=sharing

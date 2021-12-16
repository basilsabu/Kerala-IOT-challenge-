# Kerala IOT Challenge

>Foxlab Makerspace in association with GTech - Group of Technology Companies in Kerala is launching our prestigious program “Kerala IoT Challenge 2021”, with a vision to mould 100 IoT experts in Kerala, hosting on the µLearn platform. Kerala IoT Challenge is a program designed in 4 levels followed by a hackathon to identify and train quality industry leaders in the IoT domain, while any novice learner can start with layer 1 and others can enter laterally to the desired layer after an evaluation.#

# About Me
>Hello guyus..,
My name is **Basil Sabu**
I am a second year BTech Electronics and Communication student studying at **[College of Engineering Kidangooring](https://www.ce-kgr.org)**

# LEVEL 1


## Experiment List
Exp No       | List
------------ | -------------
1 |	LED Blinking
2 |	Traffic Light
3 |   LED Chasing
4 |	Button controlled LED
5 |   Buzzer
6 |   RGB LED
7 |   LDR Light sensor
8 |   Flame sensor
9 |   Temperature sensor
10|   IR Remote control
11|	Potentiometer Analog value reading
12|   7 Segment display

## Experiment 1 - Hello World LED Blinking

### code
```int ledPin = 10; // define digital pin 10.
void setup()
{
pinMode(ledPin, OUTPUT);// define pin with LED connected as output.
}
void loop()
{
digitalWrite(ledPin, HIGH); // set the LED on.
delay(1000); // wait for a second.
digitalWrite(ledPin, LOW); // set the LED off.
delay(1000); // wait for a second
}
```
![hello world](https://user-images.githubusercontent.com/70280105/131733910-0231fa02-ad37-44f9-9202-56519bfaa574.jpg)

## Experiment 2 - Traffic Light

### code
```int redled =10; // initialize digital pin 8.
int yellowled =7; // initialize digital pin 7.
int greenled =4; // initialize digital pin 4.
void setup()
{
pinMode(redled, OUTPUT);// set the pin with red LED as “output”
pinMode(yellowled, OUTPUT); // set the pin with yellow LED as “output”
pinMode(greenled, OUTPUT); // set the pin with green LED as “output”
}
void loop()
{
digitalWrite(greenled, HIGH);//// turn on green LED
delay(5000);// wait 5 seconds

digitalWrite(greenled, LOW); // turn off green LED
for(int i=0;i<3;i++)// blinks for 3 times
{
delay(500);// wait 0.5 second
digitalWrite(yellowled, HIGH);// turn on yellow LED
delay(500);// wait 0.5 second
digitalWrite(yellowled, LOW);// turn off yellow LED
} 
delay(500);// wait 0.5 second
digitalWrite(redled, HIGH);// turn on red LED
delay(5000);// wait 5 seconds
digitalWrite(redled, LOW);// turn off red LED
}
```

![Traffic Light](https://user-images.githubusercontent.com/70280105/131755398-e7cd6fd7-10be-4a5b-87c2-b43000f952f6.jpg)

## Experiment 3 - LED Chasing Effect

### code
```int BASE = 2 ;  // the I/O pin for the first LED
int NUM = 6;   // number of LEDs
void setup()
{
   for (int i = BASE; i < BASE + NUM; i ++) 
   {
     pinMode(i, OUTPUT);   // set I/O pins as output
   }
}
void loop()
{
   for (int i = BASE; i < BASE + NUM; i ++) 
   {
     digitalWrite(i, LOW);    // set I/O pins as “low”, turn off LEDs one by one.
     delay(200);        // delay
   }
   for (int i = BASE; i < BASE + NUM; i ++) 
   {
     digitalWrite(i, HIGH);    // set I/O pins as “high”, turn on LEDs one by one
     delay(200);        // delay
   }  
}
```
![LED Chasing Effect](https://user-images.githubusercontent.com/70280105/131970500-139c6893-04d1-4e06-9de0-81385b943fd2.jpg)

<p align="center">
https://youtu.be/ZJX09qersdY[](url)
</p>

## Experment 4 - Button Controlled LED

### code

```int ledpin=11;// initialize pin 11
int inpin=7;// initialize pin 7
int val;// define val
void setup()
{
pinMode(ledpin,OUTPUT);// set LED pin as “output”
pinMode(inpin,INPUT);// set button pin as “input”
}
void loop()
{
val=digitalRead(inpin);// read the level value of pin 7 and assign if to val
if(val==LOW)// check if the button is pressed, if yes, turn on the LED
{ digitalWrite(ledpin,LOW);}
else
{ digitalWrite(ledpin,HIGH);}
}
```
![Button Controlled LED](https://user-images.githubusercontent.com/70280105/132117747-9a8ae0f6-1190-4aa2-8ea6-dc4b7a89860f.jpg)

## Experment 5 - Buzzer

### code
```int buzzer=8;// initialize digital IO pin that controls the buzzer
void setup() 
{ 
  pinMode(buzzer,OUTPUT);// set pin mode as “output”
} 
void loop() 
{
digitalWrite(buzzer, HIGH); // produce sound
}
```
![Buzzer](https://user-images.githubusercontent.com/70280105/132118077-416d0941-d266-4012-93ed-2b64038c3542.png)

## Experment 6 - RGB LED

### code
```int redpin = 11; //select the pin for the red LED
int bluepin =10; // select the pin for the blue LED
int greenpin =9;// select the pin for the green LED
int val;
void setup() {
  pinMode(redpin, OUTPUT);
  pinMode(bluepin, OUTPUT);
  pinMode(greenpin, OUTPUT);
  Serial.begin(9600);
}
void loop() 
{
for(val=255; val>0; val--)
  {
   analogWrite(11, val);
   analogWrite(10, 255-val);
   analogWrite(9, 128-val);
   delay(1); 
  }
for(val=0; val<255; val++)
  {
   analogWrite(11, val);
   analogWrite(10, 255-val);
   analogWrite(9, 128-val);
   delay(1); 
  }
 Serial.println(val, DEC);
}
```
![RGB LED](https://user-images.githubusercontent.com/70280105/132117858-1bbfbb87-dfa4-4b06-9e12-23f19dee9f36.png)

## Experment 7 - LDR Light Sensor

### code
```int potpin=0;// initialize analog pin 0, connected with photovaristor
int ledpin=11;// initialize digital pin 11, 
int val=0;// initialize variable val
void setup()
{
pinMode(ledpin,OUTPUT);// set digital pin 11 as “output”
Serial.begin(9600);// set baud rate at “9600”
}
void loop()
{
val=analogRead(potpin);// read the value of the sensor and assign it to val
Serial.println(val);// display the value of val
analogWrite(ledpin,val/4);// set up brightness（maximum value 255）
delay(10);// wait for 0.01 
}
```
![LDR Light Sensor](https://user-images.githubusercontent.com/70280105/132117799-b2757ef4-8eae-4785-830a-d3196ec44128.jpg)

## Experment 8 - Flame Sensor

### code
```
const int temperaturePin = 0;
int buzzer = 12; 
void setup()
{
	pinMode(buzzer, OUTPUT);
	//set the pin connected to the buzzer as an output
}

void loop()
{
  	float voltage, degreesC;
	voltage = getVoltage(temperaturePin);
	degreesC = (voltage - 0.5) * 100.0;

    if(degreesC>37)
    {
      digitalWrite(buzzer, HIGH);    
      delay(500);  //delay half a second           
      tone(12, 10000, 100);
    }
}

float getVoltage(int pin)
{
  
  return (analogRead(pin) * 0.004882814);
}
```
![image](https://user-images.githubusercontent.com/70280105/133314201-5250ff80-c122-4a32-8aa4-1a015063d093.png)

## Experment 9 - LM35 Temperature Sensor

### cod
``` potPin = 0; // initialize analog pin 0 for LM35 temperature sensor
void setup()
{
Serial.begin(9600);// set baud rate at”9600”
}
void loop()
{
int val;// define variable
int dat;// define variable
val=analogRead(0);// read the analog value of the sensor and assign it to val
dat=(125*val)>>8;// temperature calculation formula
Serial.print("Tep");// output and display characters beginning with Tep
Serial.print(dat);// output and display value of dat
Serial.println("C");// display “C” characters
delay(500);// wait for 0.5 second
}
```
![LM35 Temperature Sensor](https://user-images.githubusercontent.com/70280105/132118621-f9831e93-e978-4b4b-8776-9540c04e7ae0.png)

## Experment 10 - IR Remote Control Using TSOP

### code
```clude <IRremote.h>
int RECV_PIN = 11;
int LED1 = 2;
int LED2 = 3;
int LED3 = 4;
int LED4 = 5;
int LED5 = 6;
int LED6 = 7;
long on1  = 0x00FF6897;
long off1 = 0x00FF9867;
long on2 = 0x00FFB04F;
long off2 = 0x00FF30CF;
long on3 = 0x00FF18E7;
long off3 = 0x00FF7A85;
long on4 = 0x00FF10EF;
long off4 = 0x00FF38C7;
long on5 = 0x00FF5AA5;
long off5 = 0x00FF42BD;
long on6 = 0x00FF4AB5;
long off6 = 0x00FF52AD;
IRrecv irrecv(RECV_PIN);
decode_results results;
// Dumps out the decode_results structure.
// Call this after IRrecv::decode()
// void * to work around compiler issue
//void dump(void *v) {
//  decode_results *results = (decode_results *)v
void dump(decode_results *results) {
  int count = results->rawlen;
  if (results->decode_type == UNKNOWN) 
    {
     Serial.println("Could not decode message");
    } 
  else 
   {
    if (results->decode_type == NEC) 
      {
       Serial.print("Decoded NEC: ");
      } 
    else if (results->decode_type == SONY) 
      {
       Serial.print("Decoded SONY: ");
      } 
    else if (results->decode_type == RC5) 
      {
       Serial.print("Decoded RC5: ");
      } 
    else if (results->decode_type == RC6) 
      {
       Serial.print("Decoded RC6: ");
      }
     Serial.print(results->value, HEX);
     Serial.print(" (");
     Serial.print(results->bits, DEC);
     Serial.println(" bits)");
   }
     Serial.print("Raw (");
     Serial.print(count, DEC);
     Serial.print("): ");
 for (int i = 0; i < count; i++) 
     {
      if ((i % 2) == 1) {
      Serial.print(results->rawbuf[i]*USECPERTICK, DEC);
     } 
    else  
     {
      Serial.print(-(int)results->rawbuf[i]*USECPERTICK, DEC);
     }
    Serial.print(" ");
     }
      Serial.println("");
     }
void setup()
 {
  pinMode(RECV_PIN, INPUT);   
  pinMode(LED1, OUTPUT);
  pinMode(LED2, OUTPUT);
  pinMode(LED3, OUTPUT);
  pinMode(LED4, OUTPUT);
  pinMode(LED5, OUTPUT);
  pinMode(LED6, OUTPUT);  
  pinMode(13, OUTPUT);
  Serial.begin(9600);
   irrecv.enableIRIn(); // Start the receiver
 }
int on = 0;
unsigned long last = millis();
void loop() 
{
  if (irrecv.decode(&results)) 
   {
    // If it's been at least 1/4 second since the last
    // IR received, toggle the relay
    if (millis() - last > 250) 
      {
       on = !on;
//       digitalWrite(8, on ? HIGH : LOW);
       digitalWrite(13, on ? HIGH : LOW);
       dump(&results);
      }
    if (results.value == on1 )
       digitalWrite(LED1, HIGH);
    if (results.value == off1 )
       digitalWrite(LED1, LOW); 
    if (results.value == on2 )
       digitalWrite(LED2, HIGH);
    if (results.value == off2 )
       digitalWrite(LED2, LOW); 
    if (results.value == on3 )
       digitalWrite(LED3, HIGH);
    if (results.value == off3 )
       digitalWrite(LED3, LOW);
    if (results.value == on4 )
       digitalWrite(LED4, HIGH);
    if (results.value == off4 )
       digitalWrite(LED4, LOW); 
    if (results.value == on5 )
       digitalWrite(LED5, HIGH);
    if (results.value == off5 )
       digitalWrite(LED5, LOW); 
    if (results.value == on6 )
       digitalWrite(LED6, HIGH);
    if (results.value == off6 )
       digitalWrite(LED6, LOW);        
    last = millis();      
irrecv.resume(); // Receive the next value
  }
}
```
![image](https://user-images.githubusercontent.com/70280105/133312517-13ca90c8-122d-4937-bd8b-8c5b380860d3.png)

## Experment 11 - Potentiometer analog Value Reading

### code
```int potpin=0;// initialize analog pin 0
int ledpin=13;// initialize digital pin 13
int val=0;// define val, assign initial value 0
void setup()
{
pinMode(ledpin,OUTPUT);// set digital pin as “output”
Serial.begin(9600);// set baud rate at 9600
}
void loop()
{
digitalWrite(ledpin,HIGH);// turn on the LED on pin 13
delay(50);// wait for 0.05 second
digitalWrite(ledpin,LOW);// turn off the LED on pin 13
delay(50);// wait for 0.05 second
val=analogRead(potpin);// read the analog value of analog pin 0, and assign it to val 
Serial.println(val);// display val’s value
}
```
![image](https://user-images.githubusercontent.com/70280105/133313650-02a49b2e-90db-45ac-9790-aba673e557e9.png)

## Experment 12 - 7 Segment Display

### code
```int a=7;// set digital pin 7 for segment a
int b=6;// set digital pin 6 for segment b
int c=5;// set digital pin 5 for segment c
int d=10;// set digital pin 10 for segment d
int e=11;// set digital pin 11 for segment e
int f=8;// set digital pin 8 for segment f
int g=9;// set digital pin 9 for segment g
int dp=4;// set digital pin 4 for segment dp
void digital_0(void) // display number 5
{
unsigned char j;
digitalWrite(a,HIGH);
digitalWrite(b,HIGH);
digitalWrite(c,HIGH);
digitalWrite(d,HIGH);
digitalWrite(e,HIGH);
digitalWrite(f,HIGH);
digitalWrite(g,LOW);
digitalWrite(dp,LOW);
}
void digital_1(void) // display number 1
{
unsigned char j;
digitalWrite(c,HIGH);// set level as “high” for pin 5, turn on segment c
digitalWrite(b,HIGH);// turn on segment b
for(j=7;j<=11;j++)// turn off other segments
digitalWrite(j,LOW);
digitalWrite(dp,LOW);// turn off segment dp
}
void digital_2(void) // display number 2
{
unsigned char j;
digitalWrite(b,HIGH);
digitalWrite(a,HIGH);
for(j=9;j<=11;j++)
digitalWrite(j,HIGH);
digitalWrite(dp,LOW);
digitalWrite(c,LOW);
digitalWrite(f,LOW);
}
void digital_3(void) // display number 3
{digitalWrite(g,HIGH);
digitalWrite(a,HIGH);
digitalWrite(b,HIGH);
digitalWrite(c,HIGH);
digitalWrite(d,HIGH);
digitalWrite(dp,LOW);
digitalWrite(f,LOW);
digitalWrite(e,LOW);
}
void digital_4(void) // display number 4
{digitalWrite(c,HIGH);
digitalWrite(b,HIGH);
digitalWrite(f,HIGH);
digitalWrite(g,HIGH);
digitalWrite(dp,LOW);
digitalWrite(a,LOW);
digitalWrite(e,LOW);
digitalWrite(d,LOW);
}
void digital_5(void) // display number 5
{
unsigned char j;
digitalWrite(a,HIGH);
digitalWrite(b, LOW);
digitalWrite(c,HIGH);
digitalWrite(d,HIGH);
digitalWrite(e, LOW);
digitalWrite(f,HIGH);
digitalWrite(g,HIGH);
digitalWrite(dp,LOW);
}
void digital_6(void) // display number 6
{
unsigned char j;
for(j=7;j<=11;j++)
digitalWrite(j,HIGH);
digitalWrite(c,HIGH);
digitalWrite(dp,LOW);
digitalWrite(b,LOW);
}
void digital_7(void) // display number 7
{
unsigned char j;
for(j=5;j<=7;j++)
digitalWrite(j,HIGH);
digitalWrite(dp,LOW);
for(j=8;j<=11;j++)
digitalWrite(j,LOW);
}
void digital_8(void) // display number 8
{
unsigned char j;
for(j=5;j<=11;j++)
digitalWrite(j,HIGH);
digitalWrite(dp,LOW);
}
void digital_9(void) // display number 5
{
unsigned char j;
digitalWrite(a,HIGH);
digitalWrite(b,HIGH);
digitalWrite(c,HIGH);
digitalWrite(d,HIGH);
digitalWrite(e, LOW);
digitalWrite(f,HIGH);
digitalWrite(g,HIGH);
digitalWrite(dp,LOW);
}
void setup()
{
int i;// set variable
for(i=4;i<=11;i++)
pinMode(i,OUTPUT);// set pin 4-11as “output”
}
void loop()
{
while(1)
{
digital_0();// display number 0
delay(1000);// wait for 1s
digital_1();// display number 1
delay(1000);// wait for 1s
digital_2();// display number 2
delay(1000); // wait for 1s
digital_3();// display number 3
delay(1000); // wait for 1s
digital_4();// display number 4
delay(1000); // wait for 1s
digital_5();// display number 5
delay(1000); // wait for 1s
digital_6();// display number 6
delay(1000); // wait for 1s
digital_7();// display number 7
delay(1000); // wait for 1s
digital_8();// display number 8
delay(1000); // wait for 1s
digital_9();// display number 9
delay(1000); // wait for 1s
}}
```
![image](https://user-images.githubusercontent.com/70280105/133313893-ca76971a-1b61-45f9-97b1-12352a615f64.png)

## IoT Challenge Assignments

### - Create a Thermometer using 6 LEDs and 1 LM35 Temperature Sensor

### Hardware needed

Component                    |Quantity
---------------------------- | -------------
UArduino UNO R3              |1
LED                          |6
100 Ω Resistor               |6
Temperature Sensor [TMP36]   |1

## code
```
void setup()
{
  pinMode(A5, INPUT);
  pinMode(3, OUTPUT);
  pinMode(4, OUTPUT);
  pinMode(5, OUTPUT);
  pinMode(6, OUTPUT);
  pinMode(7, OUTPUT);
  pinMode(8, OUTPUT);
}

void loop()
{
  if (-40 + 0.488155 * (analogRead(A5) - 20) >= -40) {
    digitalWrite(3, HIGH);
  }
  digitalWrite(3, LOW);
  if (-40 + 0.488155 * (analogRead(A5) - 20) >= -10) {
    digitalWrite(4, HIGH);
  }
  digitalWrite(4, LOW);
  if (-40 + 0.488155 * (analogRead(A5) - 20) >= 20) {
    digitalWrite(5, HIGH);
  }
  digitalWrite(5, LOW);
  if (-40 + 0.488155 * (analogRead(A5) - 20) >= 50) {
    digitalWrite(6, HIGH);
  }
  digitalWrite(6, LOW);
  if (-40 + 0.488155 * (analogRead(A5) - 20) >= 80) {
    digitalWrite(7, HIGH);
  }
  digitalWrite(7, LOW);
  if (-40 + 0.488155 * (analogRead(A5) - 20) >= 120) {
    digitalWrite(8, HIGH);
  }
  digitalWrite(8, LOW);
  delay(10);
}
```
https://user-images.githubusercontent.com/70280105/132737294-b6aa1316-eec2-4b91-b9fd-dab1f5328c05.mp4

## - Create a Digital Dice using 7 Segment Display and Push Button

### Hardware needed

Component                    |Quantity
---------------------------- | -------------
UArduino UNO R3              |1
Cathode 7 Segment Display    |2
220 Ω Resistor               |4
Pushbutton                   |1


## code
```
unsigned const int A = 13;
unsigned const int B = 12;
unsigned const int C = 11;
unsigned const int D = 10;
unsigned const int E = 9;
unsigned const int F = 8;
unsigned const int G = 7;


unsigned const int H = 0;
unsigned const int I = 1;
unsigned const int J = 2;
unsigned const int K = 3;
unsigned const int L = 6;
unsigned const int M = 5;
unsigned const int N = 4;


int b1 = A5;
int b1s;
int digit;

void setup(void)
{
  pinMode(A, OUTPUT);
  pinMode(B, OUTPUT);
  pinMode(C, OUTPUT);
  pinMode(D, OUTPUT);
  pinMode(E, OUTPUT);
  pinMode(F, OUTPUT);
  pinMode(G, OUTPUT);
  pinMode(H, OUTPUT);
  
  pinMode(H, OUTPUT);
  pinMode(I, OUTPUT);
  pinMode(J, OUTPUT);
  pinMode(K, OUTPUT);
  pinMode(L, OUTPUT);
  pinMode(M, OUTPUT);
  pinMode(N, OUTPUT);
  
  pinMode(b1, INPUT_PULLUP);
  
  randomSeed(analogRead(0));
}

//My Functions

void zero(void) {
  digitalWrite(A, LOW);
  digitalWrite(B, HIGH);
  digitalWrite(C, HIGH);
  digitalWrite(D, HIGH);
  digitalWrite(E, HIGH);
  digitalWrite(F, HIGH);
  digitalWrite(G, HIGH);
  digitalWrite(H, LOW);
}

void one(void) {
  digitalWrite(A, LOW);
  digitalWrite(B, LOW);
  digitalWrite(C, LOW);
  digitalWrite(D, HIGH);
  digitalWrite(E, LOW);
  digitalWrite(F, LOW);
  digitalWrite(G, HIGH);
  digitalWrite(H, LOW);
}

void two(void) {
  digitalWrite(A, HIGH);
  digitalWrite(B, LOW);
  digitalWrite(C, HIGH);
  digitalWrite(D, HIGH);
  digitalWrite(E, HIGH);
  digitalWrite(F, HIGH);
  digitalWrite(G, LOW);
  digitalWrite(H, LOW);
}

void three(void) {
  digitalWrite(A, HIGH);
  digitalWrite(B, LOW);
  digitalWrite(C, HIGH);
  digitalWrite(D, HIGH);
  digitalWrite(E, LOW);
  digitalWrite(F, HIGH);
  digitalWrite(G, HIGH);
  digitalWrite(H, LOW);
}

void four(void) {
  digitalWrite(A, HIGH);
  digitalWrite(B, HIGH);
  digitalWrite(C, LOW);
  digitalWrite(D, HIGH);
  digitalWrite(E, LOW);
  digitalWrite(F, LOW);
  digitalWrite(G, HIGH);
  digitalWrite(H, LOW);
}

void five(void) {
  digitalWrite(A, HIGH);
  digitalWrite(B, HIGH);
  digitalWrite(C, HIGH);
  digitalWrite(D, LOW);
  digitalWrite(E, LOW);
  digitalWrite(F, HIGH);
  digitalWrite(G, HIGH);
  digitalWrite(H, LOW);
}

void six(void) {
  digitalWrite(A, HIGH);
  digitalWrite(B, HIGH);
  digitalWrite(C, HIGH);
  digitalWrite(D, LOW);
  digitalWrite(E, HIGH);
  digitalWrite(F, HIGH);
  digitalWrite(G, HIGH);
  digitalWrite(H, LOW);
}

void seven(void) {
  digitalWrite(A, LOW);
  digitalWrite(B, LOW);
  digitalWrite(C, HIGH);
  digitalWrite(D, HIGH);
  digitalWrite(E, LOW);
  digitalWrite(F, LOW);
  digitalWrite(G, HIGH);
  digitalWrite(H, LOW);
}

void eight(void) {
  digitalWrite(A, HIGH);
  digitalWrite(B, HIGH);
  digitalWrite(C, HIGH);
  digitalWrite(D, HIGH);
  digitalWrite(E, HIGH);
  digitalWrite(F, HIGH);
  digitalWrite(G, HIGH);
  digitalWrite(H, LOW);
}

void nine(void) {
  digitalWrite(A, HIGH);
  digitalWrite(B, HIGH);
  digitalWrite(C, HIGH);
  digitalWrite(D, HIGH);
  digitalWrite(E, LOW);
  digitalWrite(F, HIGH);
  digitalWrite(G, HIGH);
  digitalWrite(H, LOW);
}




void zero2(void) {
  digitalWrite(H, LOW);
  digitalWrite(I, HIGH);
  digitalWrite(J, HIGH);
  digitalWrite(K, HIGH);
  digitalWrite(L, HIGH);
  digitalWrite(M, HIGH);
  digitalWrite(N, HIGH);
}

void one2(void) {
  digitalWrite(H, LOW);
  digitalWrite(I, LOW);
  digitalWrite(J, LOW);
  digitalWrite(K, HIGH);
  digitalWrite(L, LOW);
  digitalWrite(M, LOW);
  digitalWrite(N, HIGH);
}

void two2(void) {
  digitalWrite(H, HIGH);
  digitalWrite(I, LOW);
  digitalWrite(J, HIGH);
  digitalWrite(K, HIGH);
  digitalWrite(L, HIGH);
  digitalWrite(M, HIGH);
  digitalWrite(N, LOW);
}

void three2(void) {
  digitalWrite(H, HIGH);
  digitalWrite(I, LOW);
  digitalWrite(J, HIGH);
  digitalWrite(K, HIGH);
  digitalWrite(L, LOW);
  digitalWrite(M, HIGH);
  digitalWrite(N, HIGH);

}

void four2(void) {
  digitalWrite(H, HIGH);
  digitalWrite(I, HIGH);
  digitalWrite(J, LOW);
  digitalWrite(K, HIGH);
  digitalWrite(L, LOW);
  digitalWrite(M, LOW);
  digitalWrite(N, HIGH);

}

void five2(void) {
  digitalWrite(H, HIGH);
  digitalWrite(I, HIGH);
  digitalWrite(J, HIGH);
  digitalWrite(K, LOW);
  digitalWrite(L, LOW);
  digitalWrite(M, HIGH);
  digitalWrite(N, HIGH);

}

void six2(void) {
  digitalWrite(H, HIGH);
  digitalWrite(I, HIGH);
  digitalWrite(J, HIGH);
  digitalWrite(K, LOW);
  digitalWrite(L, HIGH);
  digitalWrite(M, HIGH);
  digitalWrite(N, HIGH);

}

void seven2(void) {
  digitalWrite(H, LOW);
  digitalWrite(I, LOW);
  digitalWrite(J, HIGH);
  digitalWrite(K, HIGH);
  digitalWrite(L, LOW);
  digitalWrite(M, LOW);
  digitalWrite(N, HIGH);
}

void eight2(void) {
  digitalWrite(H, HIGH);
  digitalWrite(I, HIGH);
  digitalWrite(J, HIGH);
  digitalWrite(K, HIGH);
  digitalWrite(L, HIGH);
  digitalWrite(M, HIGH);
  digitalWrite(N, HIGH);

}

void nine2(void) {
  digitalWrite(H, HIGH);
  digitalWrite(I, HIGH);
  digitalWrite(J, HIGH);
  digitalWrite(K, HIGH);
  digitalWrite(L, LOW);
  digitalWrite(M, HIGH);
  digitalWrite(N, HIGH);

}

void displayDigit(int digit) {
 
    if (digit == 0) {
        zero();

    } else if (digit == 1) {
       one();

    } else if (digit == 2) {
       two();

    } else if (digit == 3) {
       three();

    } else if (digit == 4) {
       four();

    } else if (digit == 5) { 
       five();

    } else if (digit == 6) {
       six();

    } else if (digit == 7) {
       seven(); 

    } else if (digit == 8) {
       eight();

    } else if (digit == 9) {
        nine();
    }
    }
  
void displayDigit2(int digit2) {
 
    if (digit2 == 0) {
        zero2();

    } else if (digit2 == 1) {
       one2();

    } else if (digit2 == 2) {
       two2();

    } else if (digit2 == 3) {
       three2();

    } else if (digit2 == 4) {
       four2();

    } else if (digit2 == 5) { 
       five2();

    } else if (digit2 == 6) {
       six();

    } else if (digit2 == 7) {
       seven2(); 

    } else if (digit2 == 8) {
       eight2();

    } else if (digit2 == 9) {
        nine2();
    }
    }
  

// Start
void loop(void)
{
  b1s = digitalRead(b1);
  if (b1s == LOW) {
 
  int digit = random(1, 9);
  int digit2 = random(0,9);
  displayDigit(digit); 
  displayDigit2(digit2);
  }
}
```
https://user-images.githubusercontent.com/70280105/132725926-046ead14-3a54-43fb-bded-92066178e0ea.mp4



---


# LEVEL 2


## Experiment List

### Part A : Experiments Using Blynk IoT Platform

Exp No       | List
------------ | -------------
1|  Hello World LED Program Using Blynk App
2|  Push Button ON/OFF Status in Mobile App
3|  Light Meter using a Progress Bar
4|  Remote Soil Moisture Measurement 
5|  IR Sensor Interfacing to Blynk App
6|  Ultrasonic Distance Measurement 
7|  Home Automation using Relay Module

## Things Used

1. 1 x ESP 32 Development Board
2. 1 x HC-SR04 Ultrasonic Distance Sensor
3. 1 x Soil Moisture Sensor
4. 1 x IR Detection Module
5. 1 x 2 Channel Relay Module (5 Volt)
6. 6 X Female to Female Jumper 
7. 6 X Male to Male Jumper 
8. 1X Digital MultiMeter ( cheapest will work) (optional)
9. 1 x Mini Tester or +/- mini screwdriver (optional)

## Experiment 1 

### code
``` #include "thingProperties.h"

void setup() {
  // Initialize serial and wait for port to open:
  pinMode(15,OUTPUT);
  Serial.begin(9600);
  // This delay gives the chance to wait for a Serial Monitor without blocking if none is found
  delay(1500); 

  // Defined in thingProperties.h
  initProperties();

  // Connect to Arduino IoT Cloud
  ArduinoCloud.begin(ArduinoIoTPreferredConnection);
  
  /*
     The following function allows you to obtain more information
     related to the state of network and IoT Cloud connection and errors
     the higher number the more granular information you’ll get.
     The default is 0 (only errors).
     Maximum is 4
 */
  setDebugMessageLevel(2);
  ArduinoCloud.printDebugInfo();
}

void loop() {
  ArduinoCloud.update();
  // Your code here 
  
  
}

/*
  Since LED1 is READ_WRITE variable, onLED1Change() is
  executed every time a new value is received from IoT Cloud.
*/
void onLed1Change()  {
  // Add your code here to act upon Led1 change
  if(led1==HIGH)
  {
    digitalWrite(15,HIGH);
  }
    else
    {
      digitalWrite(15,LOW);
    }
  }
  ```
  
  

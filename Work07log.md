#### Main Work

We discussed how the device would interact and sketched it out. And several changes to the circuit diagram were made, programmed and explored to see if the newly learned sensors could be incorporated into the device without any problems.



#### Test Basic Circuits

PIR Project:



```
int led = 10;
int inputPin = 3;             
int sensorState = LOW;           
int val = 0;                    // variable for reading the pin status
 
void setup() {
 
  pinMode(led, OUTPUT); 
  pinMode(inputPin, INPUT);     
 
  Serial.begin(9600);
}
 
void loop(){
  val = digitalRead(inputPin);  
  if (val == HIGH) {           
    
    digitalWrite(led, HIGH);  
    delay(1000);

  } else {

      digitalWrite(led, LOW);  
       delay(1000);
    }
  }
```

![image](https://github.com/mylin04202/img/blob/main/pir.jpg)

Light dependent resistor Project:


```
int ledflicker = 4;  
int ledred = 5;   
int led01 = 6;  
int led02 = 7;  
int led03 = 8;  
int led04 = 9;  
int led05 = 10;  
int led06 = 11;  
int led07 = 12;
int led08 = 13;  

int val01 = 0;
int val02 = 0;
int ledval01 = 0;
int ledval02 = 0;

void setup() {
  
    pinMode(A5, INPUT);
    pinMode(A4, INPUT);
    pinMode(A3, INPUT);
   
    pinMode(ledred, OUTPUT);
    pinMode(ledred, OUTPUT);
    pinMode(led01, OUTPUT);
    pinMode(led02, OUTPUT);
    pinMode(led03, OUTPUT);
    pinMode(led04, OUTPUT);
    pinMode(led05, OUTPUT);
    pinMode(led06, OUTPUT);
    pinMode(led07, OUTPUT);
      pinMode(led08, OUTPUT);
    Serial.begin(9600);

}

// the loop routine runs over and over again forever:
void loop()
{
  
int sensorValue01=analogRead(A4);
Serial.println(sensorValue01);

  if(sensorValue01>=1000)

{
  digitalWrite(led02,LOW);
  digitalWrite(led04,LOW);
  digitalWrite(led07,LOW);
      digitalWrite(led08,LOW);
}
else
{
    digitalWrite(led02,HIGH);
  digitalWrite(led04,HIGH);
  digitalWrite(led07,HIGH);
    digitalWrite(led08,HIGH);

}
  delay(10); 
  
  int sensorValue02=analogRead(A5);
Serial.println(sensorValue02);

  if(sensorValue02>=1000)

{
 digitalWrite(led03,LOW);
  digitalWrite(led05,LOW);
  digitalWrite(led06,LOW);
}
else
{
    digitalWrite(led03,HIGH);
  digitalWrite(led05,HIGH);
  digitalWrite(led06,HIGH);
 
}
  delay(10);
  
    int sensorValue03=digitalRead(A3);

  if(sensorValue03==HIGH)

{
  digitalWrite(ledflicker,HIGH);
    delay(750);
      digitalWrite(ledflicker,LOW);
    delay(750);
      digitalWrite(ledflicker,HIGH);
    delay(750);
      digitalWrite(ledflicker,LOW);
    delay(750);
      digitalWrite(ledflicker,HIGH);
    delay(750);
      digitalWrite(ledflicker,LOW);
    delay(750);
      digitalWrite(ledflicker,HIGH);
    delay(750);
      digitalWrite(ledflicker,LOW);
    delay(750);
}
else
{
  digitalWrite(ledred,LOW);

}
  delay(10);  
  
}

```

![image](https://github.com/mylin04202/img/blob/main/ldr.jpg)

#### Sketch:

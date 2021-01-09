## WEEK 09 - WEEK 12 Work Log

#### Main Work

We drew up the final circuits. After meeting up we practiced soldering, then initially built the circuit, tested it, set up the external decorations and filmed the video.


#### Soldering Practice


![image](https://github.com/mylin04202/img/blob/main/WechatIMG1995.jpeg)


#### Circuits (Final version)


![image](https://github.com/mylin04202/img/blob/main/finall.jpg)


#### Schematic (drawn by Minyue Lin)

![image](https://github.com/mylin04202/img/blob/main/sch.png)



#### Appearance of the Project

![image](https://github.com/mylin04202/img/blob/main/P1030116.JPG)
![image](https://github.com/mylin04202/img/blob/main/P1030135.JPG)
![image](https://github.com/mylin04202/img/blob/main/P1030125.JPG)
![image](https://github.com/mylin04202/img/blob/main/P1030118.JPG)
![image](https://github.com/mylin04202/img/blob/main/P1030119.JPG)
![image](https://github.com/mylin04202/img/blob/main/P1030159.JPG)
![image](https://github.com/mylin04202/img/blob/main/P1030160.JPG)
![image](https://github.com/mylin04202/img/blob/main/P1030161.JPG)



#### Code

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

int inputPin = 2;  
int pirState = LOW;             // we start, assuming no motion detected
int val = 0;               

int val01 = 0;
int val02 = 0;
int ledval01 = 0;
int ledval02 = 0;


void setup() {
  // led那个9号串口是输出
  
    pinMode(A5, INPUT);
    pinMode(A4, INPUT);
    pinMode(inputPin, INPUT);  
  
    pinMode(ledflicker, OUTPUT);
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
  digitalWrite(led03,LOW);
  digitalWrite(led07,LOW);
      digitalWrite(led08,LOW);
}
else
{
    digitalWrite(led02,HIGH);
  digitalWrite(led03,HIGH);
  digitalWrite(led07,HIGH);
    digitalWrite(led08,HIGH);

}
  delay(10);
 
  
  
  
  int sensorValue02=analogRead(A5);
Serial.println(sensorValue02);

  if(sensorValue02>=1000)

{
 digitalWrite(led04,LOW);
  digitalWrite(led05,LOW);
  digitalWrite(led06,LOW);
}
else
{
    digitalWrite(led04,HIGH);
  digitalWrite(led05,HIGH);
  digitalWrite(led06,HIGH);
 
}
  delay(10);
  
    int sensorValue03=digitalRead(A3);

  if(sensorValue03==HIGH)

{
  digitalWrite(ledred,HIGH);
    delay(750);
      digitalWrite(ledred,LOW);
    delay(750);
      digitalWrite(ledred,HIGH);
    delay(750);
      digitalWrite(ledred,LOW);
    delay(750);
      digitalWrite(ledred,HIGH);
    delay(750);
      digitalWrite(ledred,LOW);
    delay(750);
      digitalWrite(ledred,HIGH);
    delay(750);
      digitalWrite(ledred,LOW);
    delay(750);


}
else
{
  digitalWrite(ledred,LOW);

}
  
  delay(10);
  
  val = digitalRead(inputPin);  // read input value
  if (val == HIGH) {            // check if the input is HIGH
    digitalWrite(ledflicker, HIGH);  // turn LED ON
  delay(1500);
      digitalWrite(ledflicker,LOW);
    delay(500);
      digitalWrite(ledflicker,HIGH);
    delay(1500);
      digitalWrite(ledflicker,LOW);
    delay(750);
      digitalWrite(ledflicker,HIGH);
    delay(1500);
      digitalWrite(ledflicker,LOW);
    delay(750);
      digitalWrite(ledflicker,HIGH);
    delay(1500);
  } else {
    digitalWrite(ledflicker, LOW); // turn LED OFF

  }
  
  
  // Delay a little bit to improve simulation performance
}

```








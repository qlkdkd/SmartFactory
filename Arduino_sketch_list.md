# Sketch 모음

```arduino
// LED Blink 실습 – 46쪽
void setup()
{
  pinMode(12, OUTPUT);
}

void loop()
{
  digitalWrite(12, HIGH);
  delay(2000); // Wait for 2000 millisecond(s)
  digitalWrite(12, LOW);
  delay(1000); // Wait for 1000 millisecond(s)
}

//LED Blink 실습 – 48쪽
void setup()
{
  pinMode(12, OUTPUT);
  pinMode(11, OUTPUT);
}

void loop()
{
  digitalWrite(12, HIGH);
  digitalWrite(11, LOW);
  delay(2000); // Wait for 2000 millisecond(s)
  digitalWrite(12, LOW);
  digitalWrite(11, HIGH);
  delay(2000); // Wait for 2000 millisecond(s)
}

 
//Push Button, LED Blink 실습 – 52쪽
int push_state;

void setup()
{
  pinMode(12, INPUT);
  pinMode(13, OUTPUT);
}

void loop()
{
  push_state=digitalRead(12);
  delay(10); // Delay a little bit to improve simulation performance
  digitalWrite(13,!	push_state);
}

//기울기 센서, LED Blink 실습 – 60쪽
int tilt_sw = 0;

void setup()
{
  pinMode(12, INPUT);
  pinMode(13, OUTPUT);
}

void loop()
{
  tilt_sw=digitalRead(12);
  delay(10); // Delay a little bit to improve simulation performance
  digitalWrite(13, !tilt_sw);
}

 
//통신 실습 – 66쪽
byte incommingData;

void setup()
{
  Serial.begin(9600);
}

void loop()
{
  if (Serial.available() > 0) {
    incommingData=Serial.read();
    Serial.write(incommingData);
  }
}

//가변저항, 통신 실습 – 72쪽
int potentio_value;
float voltage_value;

void setup()
{
  Serial.begin(9600);
}

void loop()
{
  potentio_value = analogRead(A0);
  delay(10);
  voltage_value = (potentio_value+0.5)*5.00/1024.00;
  Serial.print("sensor value = ");
  Serial.println(potentio_value);
  Serial.print("sensor volatage = ");
  Serial.println(voltage_value);
}

 
//조도센서, LED on/off 실습 – 78쪽
void setup()
{
  pinMode(12,OUTPUT);
  Serial.begin(9600);
}

void loop()
{
  int photo_value=analogRead(A0);  
  delay(10); // Delay a little bit to improve simulation performance
  Serial.println(photo_value);
  if (photo_value >= 150) {
    digitalWrite(12, HIGH);}
  else {
    digitalWrite(12, LOW);}
}

//온도센서, 통신 – 80쪽
void setup()
{
  Serial.begin(9600);
}

void loop()
{
  int sensorValue = analogRead(A0);
  float milliVoltage = (sensorValue+0.5)*5000.0/1024.0;
  float temperatureC = (milliVoltage - 500) / 10.0;
  Serial.println(temperatureC);
}

 
 가변저항으로 LED 밝기 조절 – 89쪽
void setup()
{
  pinMode(11, OUTPUT);
}

void loop()
{
  int sensorValue = analogRead(A0);
  int outputValue = round(sensorValue*255.0/1023.0);
  analogWrite(11, outputValue);
  delay(100); // Wait for 100 millisecond(s)
}

 DC모터 제어 – 93쪽
void setup()
{
  pinMode(9, OUTPUT);
}
void loop()
{
  analogWrite(9, 255);
  delay(1000);
  analogWrite(9, 127);
  delay(1000);
  analogWrite(9, 0);
  delay(1000);
}
```



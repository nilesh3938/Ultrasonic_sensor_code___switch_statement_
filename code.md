
const int trigPin = 2;
const int echoPin = 3;
long duration;
int distanceCm, distanceInch;
int Nilesh = 0;

void setup() {
  Serial.begin(9600);
pinMode(trigPin, OUTPUT);
pinMode(echoPin, INPUT);
}

void loop() {
  
digitalWrite(trigPin, LOW);
delayMicroseconds(2);
digitalWrite(trigPin, HIGH);
delayMicroseconds(10);
digitalWrite(trigPin, LOW);

duration = pulseIn(echoPin, HIGH);
distanceCm= duration*0.034/2;
distanceInch = duration*0.0133/2;

int val = digitalRead(3);

if (val <1)

{
  analogWrite ( 5, 5);
  delay (1000);
  Nilesh = Nilesh + 1 ;
}

else 

{
  analogWrite(6 , 50);
  delay(5000);
}

Serial.print(distanceCm);
Serial.print("cm");
delay (5000);

}

//Arduino_DIY_PullseSensor
//diy pulse sensor

int sensorPin1 = A0;
int sensorPin2 = A1;// select the input pin for LDR
int IRR = 7;
int sensorValue1 = 0;
int sensorValue2 = 1;
int Light = 12;
// variable to store the value coming from the sensor
void setup() {
pinMode(IRR, OUTPUT);
pinMode(Light, OUTPUT);
Serial.begin(9600); //sets serial port for communication
}
void loop() {
sensorValue1 = analogRead(sensorPin1); // read the value from the sensor
delay(50);
Serial.println(sensorValue1); //prints the values coming from the sensor on the screen
delay(50);
sensorValue2 = analogRead(sensorPin2);
delay(50);
Serial.println(sensorValue2); //prints the values coming from the sensor on the screen
delay(50);
digitalWrite(IRR, HIGH);
if( sensorValue2 > sensorValue1 + 2 ){
  digitalWrite(Light, HIGH);
}else{
  digitalWrite(Light, LOW);
}




}

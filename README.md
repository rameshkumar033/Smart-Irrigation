# Smart-Irrigation
Smart irrigation system
int sensorPin = A0;
int relayPin = 8;
int value;

void setup() {
  pinMode(relayPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  value = analogRead(sensorPin);
  Serial.println(value);

  if (value > 600) {
    digitalWrite(relayPin, LOW);  // Pump ON
  } else {
    digitalWrite(relayPin, HIGH); // Pump OFF
  }

  delay(1000);
}

# Internet-of-things


https://wokwi.com/projects/335608887482778195  1(LED)<br>
https://wokwi.com/projects/305566932847821378  (blink an led)<br>
https://wokwi.com/projects/335072097778795092  (we did ultra sonic)<br>
https://wokwi.com/projects/333800186223526484  (2)RGB <br>
https://wokwi.com/projects/335617269702853204  (Two ultra sonic sensor)<br>
https://wokwi.com/projects/334977710373732948  (servo moter- 1)<br>
https://wokwi.com/projects/337605583877177938  (DH22 with LCD)<br>



1.https://wokwi.com/projects/333716288653230676    (1)3LED<br>
2.https://wokwi.com/projects/333804621070860883    (red green blue)<br>
3.https://wokwi.com/projects/322062421191557714    (hello LCD)<br>
4.https://wokwi.com/projects/334979366855377490    (clock type - servomoter)<br>
5.https://wokwi.com/projects/334982086942261844    (servomoter with potentiometer)<br>
6.https://wokwi.com/projects/335705362914083411    (Servomotor with pushbutton)<br>
7.https://wokwi.com/projects/335065093102371411    (Buzzer with register)<br>
8.https://wokwi.com/projects/335068344588698194    (Buzzer with push button)<br>
9.https://wokwi.com/projects/335071568727114322    (Ultrasonicsensor)<br>
10.https://wokwi.com/projects/335074087297614419   (Ultrasonocsensor with buzzer)<br>
11.https://wokwi.com/projects/335611531295195730   (ultrasonic sensor with buzzer and LED)<br>
12.https://wokwi.com/projects/335701644446532180   (potentiometr using led)<br>
13.https://wokwi.com/projects/337602684471214674   (DHT22(Humidity and Temperature sensor)<br>
14.https://wokwi.com/projects/337604296859189842   (DHT22 + LCD(Humidity and Temperature sensor)<br>
15.https://wokwi.com/projects/340775764469219922   (LED_CHASER)<br>
16.https://wokwi.com/projects/340776572602548818   (LDR)<br>
17.https://wokwi.com/projects/340776926585029204   (LDR_LED)<br>







#define sensorPin 7<br>
#define relayPin 8<br>

// Variable to store the time when last event happened<br>
unsigned long lastEvent = 0;<br>
boolean relayState = false;    // Variable to store the state of relay<br>
<br>
void setup() {<br>
	pinMode(relayPin, OUTPUT);  // Set relay pin as an OUTPUT pin<br>
	pinMode(sensorPin, INPUT);  // Set sensor pin as an INPUT<br>
}<br>

void loop() {<br>
	// Read Sound sensor<br><br>
	int sensorData = digitalRead(sensorPin);<br>

	// If pin goes LOW, sound is detected<br>
	if (sensorData == LOW) {<br>

	// If 25ms have passed since last LOW state, it means that<br>
	// the clap is detected and not due to any spurious sounds<br>
	if (millis() - lastEvent > 25) {
		//toggle relay and set the output<br>
		relayState = !relayState;<br>
		digitalWrite(relayPin, relayState ? HIGH : LOW);<br>
	}<br>

	// Remember when last event happened<br>
	lastEvent = millis();<br>
	}<br>
}<br>






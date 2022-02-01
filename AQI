// Arduino IDE code 
#define BLYNK_PRINT Serial
#include <ESP8266WiFi.h>
#include <BlynkSimpleEsp8266.h>

BlynkTimer timer;

char auth[] = "OZyRdSq1Pf990XiiiTscSdEGkR1Mhdb";   //enter your token from email
char ssid[] = "MERCUSYS_0832";                              //enter your wifi username
char pass[] = "12345678";                          //enter your wifi password 

  
int mq135 = A0;     //smoke sensor is connected with the analog pin A0
int data = 0;

void sensorData()
{
  data = analogRead(mq135);           //read A0 pin of NodeMCU
  Blynk.virtualWrite(V2,data);        //virtual pin V2
  
}

void setup() {
  Serial.begin(9600);
  Blynk.begin(auth, ssid, pass,"188.166.206.43");  //PING blynk-cloud.com
  timer.setInterval(1000L, sensorData);
}

void loop() {
  Blynk.run();
  timer.run();
}

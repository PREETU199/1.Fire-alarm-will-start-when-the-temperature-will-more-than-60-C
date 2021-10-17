# 1.Fire-alarm-will-start-when-the-temperature-will-more-than-60-C
The alarm will started  automatically when  temperature  will above 60 degree.
# code of the project .


const int temperaturePin = 0; //the declaration of the variable
int buzzer = 12; 
//we will connect the buzzer to D12 on the arduino
void setup()
{

pinMode(buzzer, OUTPUT);
//set the pin connected to the buzzer as an output
}

void loop()
{float voltage, degreesC;
voltage = getVoltage(temperaturePin);
degreesC = (voltage - 0.5) * 100.0;

  if(degreesC>60)
  {
  digitalWrite(buzzer, LOW);    
  delay(500);  //delay half a second           
  tone(12, 10000, 100);
  }
}

float getVoltage(int pin)
{
  
  return (analogRead(pin) * 0.004882814);
}

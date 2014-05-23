SondaLM335
==========

Sonda de temperatura LM335 programada para Arduino.

// Sensor de temperatura.


int degC = 0;         
float T = 0;
float Tmax = -273;
float Tmin = 150;

void setup()
{
	Serial.begin(9600);
}

void loop()
{
	degC = analogRead(0);   // lee el pin analogico 0.
	T = 100.0 * (degC * 5.0 / 1024.0) - 273.15 - 3;


	Serial.print("Lectura PIN 0: ");
	Serial.print( degC);
	Serial.print(", Temperatura: ");
	Serial.print(T);
	Serial.print("C");

	if(T > Tmax){Tmax = T;}
	if(T < Tmin){Tmin = T;}
	Serial.print("     , Temperatura_max: "); Serial.print(Tmax); Serial.print("C");
	Serial.print("     , Temperatura_min: "); Serial.print(Tmin); Serial.println("C");
        


	delay(1000);
}

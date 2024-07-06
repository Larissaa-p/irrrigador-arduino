# Irrigador_Arduino

## Circuito no Tinkercad
![sensor de umidade](https://github.com/Larissaa-p/irrrigador-arduino/assets/163125769/4334ff4f-196b-4f82-8fb2-34012913cbb7)

[Link do circuito](https://www.tinkercad.com/things/2GPBdc4YIzb-sensor-de-umidade?sharecode=5vHtJcfMxRAFPbo-yMzKi65TftOvmEt958iAWoBlcfU)

### Código

```

const int sensorpin = A0;
const int sensorpower = 6;
const int pumppin = 9;

int sensor;

const int delayTime = 1; 

int wet = 800;
int dry = 500;


void setup(){ 
  pinMode(sensorpower,OUTPUT);
  pinMode(pumppin,OUTPUT);
  
  Serial.begin(9600);
}

void loop(){
  digitalWrite(sensorpower,HIGH);
  delay(10);
  
  sensor = analogRead(sensorpin);
  
  digitalWrite(sensorpower,LOW);
  
  Serial.println(sensor);
  
  if(sensor>wet){
    digitalWrite(pumppin,LOW);
  }
  else if(sensor<dry){
   digitalWrite(pumppin,HIGH);
  }

  delay(delayTime);
  
}

```
## Vídeo do projeto funcionando

[Link do vídeo](https://youtu.be/mI0etf5Ydtc)

## Créditos

Finio, Ben. "Build a Circuit to Automatically Water Your Plants." Science Buddies, 6 Dez. 2023, https://www.sciencebuddies.org/science-fair-projects/project-ideas/PlantBio_p055/plant-biology/arduino-automatic-plant-watering.

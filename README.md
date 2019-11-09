# Semaforo_Arduino
d267235@urhen.com
```
void setup() {
   // Luzes do Semaforo ligadas aos pinos 13, 12, 11
   pinMode(13, OUTPUT); // Vermelho
   pinMode(12, OUTPUT); // Amarelo
   pinMode(11, OUTPUT); // Verde
   // Luzes do Semaforo do Pedestre ligadas aos pinos 10, 9
   pinMode(10, OUTPUT); // Vermelho do Pedestre
   pinMode( 9, OUTPUT); // Verde do Pedestre
   // Botao do Pedestre
   pinMode( 3, INPUT); // Botão do Pedestre para acionar a travessia
}

void loop() {
   // Verde para os automoveis
   digitalWrite(13, 0); // Verm
   digitalWrite(12, 0); // Amar
   digitalWrite(11, 1); // Verd
   digitalWrite(10, 1); // Vermelho para o Pedestre
   digitalWrite( 9, 0); // Verde do Pedestre apagado
   // Verificar se apertou o botao
   if ( digitalRead(3) == 1 )
      {
     
      // Vermelho para os automoveis
      digitalWrite(13, 1);
      digitalWrite(12, 0);
      digitalWrite(11, 0);
      // Verde para os pedestres
      digitalWrite(10, 0);
      digitalWrite( 9, 1);
      delay(5500); // Aguardar o Pedestre atravessar
      // Piscar o Vermelho do Pedestre 10 vezes
      digitalWrite( 9, 0); 
      for (int i=1; i<=10; i++ )
          {
          // Piscando Vermelho para o pedestre
          digitalWrite(10, 1);
          delay(100);
          digitalWrite(10, 0);
          delay(100);
          }
     	digitalWrite(10, 1);
     
     	digitalWrite(13, 0);
      	digitalWrite(12, 0);
      	digitalWrite(11, 1);
        delay(5000);
     
     	 // Amarelo para os automoveis
        digitalWrite(13, 0);
        digitalWrite(12, 1);
        digitalWrite(11, 0);
        delay(1000);
      }
}
```

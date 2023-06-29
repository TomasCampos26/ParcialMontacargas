# DocumentacionDojo2
![ArduinoTinkercad (1)](https://github.com/TomasCampos26/ParcialMontacargas/assets/123908697/d69e5246-4c8f-49a0-a250-39338888852d)


## Integrantes 
- Campos Tomás

## Proyecto: Montacargas
![PARCIAL MONTACARGAS]![image](https://github.com/TomasCampos26/ParcialMontacargas/assets/123908697/e47fe0f0-e205-43fd-a611-5578cc4a5b1e)



## Descripción
El proyecto trata de una simulación de un montacargas. Con el botón 1 el montacargas sube un solo piso. Con el botón 2, baja un solo piso.
Y con el botón 3 para el circuito hasta que ya no lo presiones.

## Funciónes principales
Esta funcion se encarga de prender en el display el numero que le envias por parámetro.

~~~ C (lenguaje en el que esta escrito)
1.
void PrenderDisplay(int numero)
{
  digitalWrite(A, LOW);
  digitalWrite(B, LOW);
  digitalWrite(C, LOW);
  digitalWrite(D, LOW);
  digitalWrite(E, LOW);
  digitalWrite(F, LOW);
  digitalWrite(G, LOW);
  
  switch(numero)
  {
    case 0:
    digitalWrite(A, HIGH);
    digitalWrite(B, HIGH);
    digitalWrite(C, HIGH);
    digitalWrite(D, HIGH);
    digitalWrite(E, HIGH);
    digitalWrite(F, HIGH);
    break;
    
    case 1:
    digitalWrite(B, HIGH);
    digitalWrite(C, HIGH);
    break;
    
    case 2:
    digitalWrite(A, HIGH);
    digitalWrite(B, HIGH);
    digitalWrite(G, HIGH);
    digitalWrite(E, HIGH);
    digitalWrite(D, HIGH);
    break;
  
    case 3:
    digitalWrite(A, HIGH);
    digitalWrite(B, HIGH);
    digitalWrite(C, HIGH);
    digitalWrite(G, HIGH);
    digitalWrite(D, HIGH);
    break;
    
    case 4:
    digitalWrite(F, HIGH);
    digitalWrite(G, HIGH);
    digitalWrite(B, HIGH);
    digitalWrite(C, HIGH);
    break;  
    
    case 5:
    digitalWrite(A, HIGH);
    digitalWrite(F, HIGH);
    digitalWrite(C, HIGH);
    digitalWrite(G, HIGH);
    digitalWrite(D, HIGH);
    break;  
    
    case 6:
    digitalWrite(A, HIGH);
    digitalWrite(B, HIGH);
    digitalWrite(C, HIGH);
    digitalWrite(G, HIGH);
    digitalWrite(D, HIGH);
    break;  
    
    case 7:
    digitalWrite(A, HIGH);
    digitalWrite(C, HIGH);
    digitalWrite(D, HIGH);
    digitalWrite(E, HIGH);
    digitalWrite(F, HIGH);   
    digitalWrite(G, HIGH);
    break;  
    
    case 8:
    digitalWrite(A, HIGH);
    digitalWrite(B, HIGH);
    digitalWrite(C, HIGH);
    digitalWrite(D, HIGH);
    digitalWrite(E, HIGH);
    digitalWrite(F, HIGH);   
    digitalWrite(G, HIGH);
    break;  
    
    case 9:
    digitalWrite(A, HIGH);
    digitalWrite(B, HIGH);
    digitalWrite(C, HIGH);
    digitalWrite(D, HIGH);
    digitalWrite(F, HIGH);   
    digitalWrite(G, HIGH);
    break;
  } 
}

2.
void funcion_bomberos()
{
  digitalWrite(LED_AZUL, HIGH);
  digitalWrite(LED_VERDE, LOW);
  digitalWrite(LED_ROJO, LOW);
  while(digitalRead(boton_bomberos)== 0)
  {
    Serial.println("LLAMANDO A LOS BOMBEROS");   
  }
  while(digitalRead(boton_bomberos)== 1)
  {
    Serial.println("LLAMANDO A LOS BOMBEROS");   
  }
  pulsador_anterior = digitalRead (boton_bomberos); 
}

3.
void detener_montacargas()
{
  digitalWrite(LED_ROJO, HIGH);
  digitalWrite(LED_VERDE, LOW);
  digitalWrite(LED_AMARILLO, HIGH);
  while(digitalRead (boton3) == 0)// entra al primer while hasta que el boton sea 1
  {
    Serial.println("PARADA 1");
  }
  while(digitalRead (boton3) == 1)
  {
    Serial.println("PARADA 2");   
  }
  pulsador_anterior = digitalRead (boton3);
  digitalWrite(LED_AMARILLO, LOW);
  digitalWrite(LED_ROJO, LOW);
}

4.
void subirMontacargas()
{
  digitalWrite(LED_ROJO, LOW);
  digitalWrite(LED_VERDE, HIGH);
  numero += 1;
  
  for (int i = 0; i <= 3000; i += 10) 
  {
    if (digitalRead(boton3) == 0 && digitalRead(boton3) != pulsador_anterior)
    {
      detener_montacargas();
    }
    if(digitalRead(boton_bomberos) == 0 && digitalRead(boton_bomberos) != pulsador_anterior)
    {
      funcion_bomberos();
    }
    else if (digitalRead(boton3) == 1) //reset de pulsador anterior
    {
      pulsador_anterior = 1; 
    }
    digitalWrite(LED_VERDE, HIGH);
    delay(10); 
  }  
  digitalWrite(LED_VERDE, LOW);
}

5.
void bajarMontacargas()
{
  digitalWrite(LED_ROJO, LOW);
  digitalWrite(LED_VERDE, HIGH);
  numero -= 1;
   for (int i = 0; i <= 3000; i += 10) 
  {
    if (digitalRead(boton3) == 0 && digitalRead(boton3) != pulsador_anterior)
    {
      detener_montacargas();
    }
    if(digitalRead(boton_bomberos) == 0 && digitalRead(boton_bomberos) != pulsador_anterior)
    {
      funcion_bomberos();
    }
    else if (digitalRead(boton3) == 1)
    {
      pulsador_anterior = 1;
    }
    digitalWrite(LED_VERDE, HIGH);
    delay(10);
  }
  digitalWrite(LED_VERDE, LOW);
}
~~~

## 🥇 Link al proyecto:
- [Proyecto]https://www.tinkercad.com/things/d7a2zqCZ2sz-parcial-montacargasrecuperatorio/editel

---




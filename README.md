# DocumentacionDojo2
![ArduinoTinkercad (1)](https://github.com/TomasCampos26/ParcialMontacargas/assets/123908697/d69e5246-4c8f-49a0-a250-39338888852d)


## Integrantes 
- Campos Tomás

## Proyecto: Montacargas
![PARCIAL MONTACARGAS]!![image](https://github.com/TomasCampos26/ParcialMontacargas/assets/123908697/bae0f798-7a60-4260-a45d-d8355f67e3f2)




## Descripción
El proyecto trata de una simulación de un montacargas. Con el botón 1 el montacargas sube un solo piso. Con el botón 2, baja un solo piso.
Y con el botón 3 para el circuito hasta que ya no lo presiones.

##Código completo
~~~ C (lenguaje en el que esta escrito)
// C++ code
// CAMPOS TOMAS - DIV J


#define LED_ROJO 13
#define LED_VERDE 12
#define LED_AMARILLO 2
#define LED_AZUL 3
#define A 7
#define B 6
#define C A1
#define D A2
#define E A3
#define F 8
#define G 9
#define boton1 11
#define boton2 10
#define boton3 5
#define boton_bomberos 4

int numero = 0;
int pulsador_anterior = 1;

void setup()
{
  Serial.begin(9600);
  pinMode(LED_ROJO, OUTPUT);
  pinMode(LED_VERDE, OUTPUT);
  pinMode(LED_AMARILLO, OUTPUT);
  pinMode(LED_AZUL, OUTPUT);
  pinMode(A, OUTPUT);
  pinMode(B, OUTPUT);
  pinMode(C, OUTPUT);
  pinMode(D, OUTPUT);
  pinMode(E, OUTPUT);
  pinMode(F, OUTPUT);
  pinMode(G, OUTPUT);
  pinMode(boton1, INPUT_PULLUP);
  pinMode(boton2, INPUT_PULLUP);
  pinMode(boton3, INPUT_PULLUP);
  pinMode(boton_bomberos, INPUT_PULLUP);
}

void loop()
{
  digitalWrite(LED_ROJO, HIGH);
  digitalWrite(LED_AZUL, LOW);
  int estadoBoton1 = digitalRead(boton1);
  int estadoBoton2 = digitalRead(boton2);
  int estadoBoton3 = digitalRead(boton3);
  //int estadoBoton_bomberos = digitalRead(boton_bomberos);
  delay(100);
  Serial.println(numero);
  PrenderDisplay(numero);

  if (digitalRead (boton3) == 0 && digitalRead(boton3) != pulsador_anterior)
  {
    detener_montacargas();
  }
  if(digitalRead(boton_bomberos) == 0 && digitalRead(boton_bomberos) != pulsador_anterior)
  {
    funcion_bomberos();     
  }
  else if (digitalRead (boton3) == 1)
  	{
    	pulsador_anterior = 1; //para que no vuelva a entrar
  	}
  digitalWrite(LED_AMARILLO, LOW);
 
  if (estadoBoton1 == 0)
  {
    subirMontacargas();
  }
  if (estadoBoton2 == 0)
  {
    bajarMontacargas();
  }
}

-

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
~~~
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
~~~
~~~
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
~~~
~~~
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
~~~
~~~
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
~~~
~~~
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
- [Proyecto](https://www.tinkercad.com/things/d7a2zqCZ2sz-parcial-montacargasrecuperatorio/editel)

---




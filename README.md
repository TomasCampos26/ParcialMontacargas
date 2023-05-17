# DocumentacionDojo2
![Tinkercad](ArduinoTinkercad.jpg)


## Integrantes 
- Campos Tomás
- Atoche Luis
- Escobar Rodrigo
- Tomas Blanco Rivas


## Proyecto: Subte
![image](https://github.com/TomasCampos26/DocumentacionDojo2/assets/123908697/68755d25-31c7-4f27-b6ca-6ed75afce6d5)


## Descripción
El proyecto trata de una simulación de un subte, en la cual van prendiendo los leds indicando en que parada te
encontras actualmente (Constitución, San Juan, Independencia, Moreno), cuantas paradas te faltan para llegar a
la terminal y realiza un sonido al parar el subte y abrir sus puertas en el caso de que haya personas no videntes.

## Función principal
Esta funcion se encarga de prender en el display el numero que le envias por parámetro.

~~~ C (lenguaje en el que esta escrito)
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
  } 
}
~~~

## 🚅 Link al proyecto
- [proyecto](https://www.tinkercad.com/things/gO5GRBbJRg1-dojo-2/editel)

## :tv: Link al video del funcionamiento
- [video](https://youtu.be/AJGb5cAVgBU)

---




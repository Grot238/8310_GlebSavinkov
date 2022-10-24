#Отчёт 7
## Савинков Глеб
### 8310
[Ссылка на проект1.](https://www.tinkercad.com/things/f7weJwLzXu9-funky-lahdi-jofo/editel?sharecode=EHinjJiCk7kAWqEPRT9gWICpr82ozAHVDEFAgR1Y1HU)
![Funky Lahdi-Jofo](https://user-images.githubusercontent.com/114941628/197576978-a98437a4-53eb-465b-9eb7-b56ab3b8a0ee.png)
## Листинг программы

///1
```C++
#include<Keypad.h>
const byte ROWS = 4; 
const byte COLS = 4; 
char hexaKeys[ROWS][COLS] = 
{
{'D','#','0','*'},
{'C','9','8','7'},
{'B','6','5','4'},
{'A','3','2','1'}
};


byte rowPins[ROWS] = {7, 6, 5, 4}; 
byte colPins[COLS] = {11, 10, 9, 8}; 
Keypad customKeypad = Keypad( makeKeymap(hexaKeys), rowPins, colPins, ROWS, COLS);
void setup(){
Serial.begin(9600);
  pinMode(3, OUTPUT);
  pinMode(2, OUTPUT);
  pinMode(1, OUTPUT);
  pinMode(0, OUTPUT);
  pinMode(13, OUTPUT);
}
void loop(){
char customKey = customKeypad.getKey(); 
  if (customKey){
Serial.println(customKey);
}
   if (customKey=='8')
   {
    digitalWrite(3, HIGH);
      delay(500);
   }
  else
  {
    digitalWrite(3, LOW);
     }

  if (customKey=='9')
  {
    digitalWrite(2, HIGH);
    delay(500);
  }
  else
  {
    digitalWrite(2, LOW);
  }
    
   if (customKey=='7')
   {
    digitalWrite(13, HIGH);
     delay(500);
   }
  else
  {
    digitalWrite(13, LOW);
  }

}

```

## Пояснение
В данной работе нам надо пересобрать панель клавиатуры в коде, после чего подлеючить на них включение и выключение светодиодов.

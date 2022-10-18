#Отчёт 4
## Савинков Глеб
### 8310
[Ссылка на проект1.](https://www.tinkercad.com/things/fJklofwmcfR-grand-habbi/editel?sharecode=wt97V6N9o_HQQncNxtKAawXFSohmC0i3GH3HXnmBuK0)
![2022-10-18_20-17-53](https://user-images.githubusercontent.com/114941628/196500688-ab8627b8-1fcf-4993-9f98-3de19440c14d.png)
## Листинг программы

///4
```C++
int buttonState = 0;
int lastButtonState = 0;
int buttonPushCounter = 0;
int PIN_BUTTON = 2;
int buttonStote = digitalRead(PIN_BUTTON);
int counter;
void setup()
{
  pinMode(3, OUTPUT);
  pinMode(4, OUTPUT);
  pinMode(5, OUTPUT);
  pinMode(6, OUTPUT);
  pinMode(2, INPUT);
  pinMode(7, OUTPUT);
}

void loop()
{
  digitalWrite(3, LOW);
  digitalWrite(4, LOW);
  digitalWrite(5, HIGH);
  digitalWrite(6, HIGH);
  Serial.println(buttonStote);
    delay(50);
  buttonState = digitalRead(2);
  if (buttonState == HIGH) 
  {
    delay(500); 
    digitalWrite(5, LOW);
    digitalWrite(4, HIGH);
    digitalWrite(3, LOW);
    delay(3000); 
    digitalWrite(5, LOW);
    digitalWrite(4, LOW);
    digitalWrite(3, HIGH);
    delay(1000); 
    digitalWrite(6, LOW);
    digitalWrite(7, HIGH);
    delay(10000); 
    digitalWrite(7, LOW);
    for (counter = 0; counter < 7; ++counter) 
    {
    digitalWrite(6, HIGH);
    delay(500); 
    digitalWrite(6, LOW);
    delay(500); 
    }
    digitalWrite(6, LOW);
    }
    
 }
```

## Пояснение
Я долго работал и у меня были проблемы с подключением кнопки на плату, не смотря на код, она не читалась. После переподключения код начал работать, сам светофор, как в примере реализуем через состояние кнопки.

## Блок схема 
![блок 4](https://user-images.githubusercontent.com/114941628/196505547-c986e685-d51c-4483-bf04-fb6658df7942.png)


#Отчёт 3
## Савинков Глеб
### 8310
[Ссылка на проект1.](https://www.tinkercad.com/things/1HfEe7XpPT2-magnificent-jarv-gaaris/editel?sharecode=hFOXUq9evxB-SlTqL4qKQlRqyuIln7tPLWTg5tSujKg)
![Magnificent Jarv-Gaaris](https://user-images.githubusercontent.com/114941628/194938036-213ca7ff-71c8-4935-a5e8-61e2fa2d9c3d.png)
[Ссылка на проект2.](https://www.tinkercad.com/things/dC2ChQw5K4X-smooth-uusam-wolt/editel?sharecode=1t64SrozFPB6dexZvOxvNnffXOI1t4rJ2hSrkqhM6pg)
[Ссылка на проект3.](https://www.tinkercad.com/things/gWBXgQVSNMn-incredible-kup-snicket/editel?sharecode=xfDCuFw4aoPrtuRoh1FbFxyzEnsJ_3xlM6-0_zMlX48)
![Incredible Kup-Snicket](https://user-images.githubusercontent.com/114941628/194938859-7c4051ea-f07f-4ee2-bb6f-a154f6cbf23d.png)
## Листинг программы

///1
```C++
byte i;
byte LedMin = 2;
byte LedMax = 11;
void setup()
{
  for (i=LedMin;i<=LedMax;i=i+1)
  {
    pinMode(i,OUTPUT);
  }
}

void loop()
{
 for (i=LedMin;i<=LedMax;i=i+1)
 {
   digitalWrite(i,HIGH);
   delay(50);
 }
  for (i=LedMax;i>=LedMin;i--)
  {
    digitalWrite(i,LOW);
   delay(50);
  }
}
```

///2
```C++
byte i;
byte LedMin = 2;
byte LedMax = 11;
void setup()
{
  for (i=LedMin;i<=LedMax;i=i+2)
  {
    pinMode(i,OUTPUT);
  }
}

void loop()
{
 for (i=LedMin;i<=LedMax;i=i+2)
 {
   digitalWrite(i,HIGH);
   delay(50);
 }
  for (i=LedMax;i>=LedMin;i--)
  {
   digitalWrite(i,LOW);
   delay(50);
  }
}
```

///3
```C++
byte i; // задаём переменную для цифровых выходов
byte LedMin = 1; // первый пин со светодиодом
byte LedMax = 11; // последний пин со светодиодом
void setup()
{
// задаём пин с 1 по 11, как выход (OUTPUT)
  for (i=LedMin;i<=LedMax;i++)
  {
    pinMode(i,OUTPUT);
  }
}
void loop()
{
// последовательно зажигаем светодиоды
 for (i=LedMin;i<=LedMax;i++)
 {
   digitalWrite(i,HIGH);
   delay(50);
 }
 // последовательно гасим светодиоды
 for (i=LedMin;i<=LedMax;i++)
  {
   digitalWrite(i,LOW);
   delay(50);
  }
}
```

## Пояснение
В данном случае, мы меняем плату и подключение портов в таком порядке, чтобы наша программа работала и выполняла задуманные действия в соответствии с порядком выполнения.

## Блок схема 
![Блок 2](https://user-images.githubusercontent.com/114941628/194953681-72061e57-6462-4de5-b7ef-76d5630e8db1.png)

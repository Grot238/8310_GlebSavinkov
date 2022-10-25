#Отчёт 8
## Савинков Глеб
### 8310
[Ссылка на проект1.](https://www.tinkercad.com/things/7qC2KFWbQne-surprising-fyyran-krunk/editel?sharecode=s_BiZyJX5rcA_rYMou-nM4O8_FpSxXRZ8htfSUGXYpE)
![Surprising Fyyran-Krunk](https://user-images.githubusercontent.com/114941628/197868388-fd8eb787-df73-4562-9a12-09b2a29ef964.png)
## Листинг программы

///1
```C++
#include<LiquidCrystal.h>
#include<Keypad.h>

int i;
LiquidCrystal lcd(13, 12, 11, 10, 9, 8);

const byte ROWS = 3;
const byte COLS = 3;
char hexaKeys[ROWS][COLS] =
{
{'1','4','7',},
{'2','5','8',},
{'3','6','9',},

};
byte rowPins[ROWS] = {4, 3, 2 };
byte colPins[COLS] = {7, 6, 5 };

Keypad customKeypad = Keypad( makeKeymap(hexaKeys), rowPins, colPins, ROWS, COLS);

void setup() 
{
lcd.begin(16, 2);
}
void loop() 
{
  char customKey = customKeypad.getKey();
  switch (customKey)
  {
    case '1':
    lcd.clear();
    lcd.setCursor(0, 0);
    lcd.print('1');
    i=1;
    break;
    case '2':
    lcd.clear();
    lcd.setCursor(0, 0);
    lcd.print('2');
    i=2;
    break;
    case '3':
    lcd.clear();
    lcd.setCursor(0, 0);
    lcd.print('3');
    i=3;
    break;
    case '4':
    lcd.clear();
    lcd.setCursor(0, 0);
    lcd.print('4');
    i=4;
    break;
    case '5':
    lcd.clear();
    lcd.setCursor(0, 0);
    lcd.print('5');
    i=5;
    break;
    case '6':
    lcd.clear();
    lcd.setCursor(0, 0);
    lcd.print('6');
    i=6;
    break;
    case '7':
    lcd.clear();
    lcd.setCursor(0, 0);
    lcd.print('7');
    i=7;
    break;
    case '8':
    lcd.clear();
    lcd.setCursor(0, 0);
    lcd.print('8');
    i=8;
    break;
    case '9':
    lcd.clear();
    lcd.setCursor(0, 0);
    lcd.print('9');
    i=9;
    break;
  }
  if ( i%2==0)
  {
    lcd.setCursor(0, 1);
    lcd.print("Chetnoe");
  }
  else
  {
    lcd.setCursor(0, 1);
    lcd.print("Ne Chetnoe");
  }
}
```

## Пояснение
В работе я использовал элементы седьмой работы, я урезал значения кейборда до более удобных, вывод на жк экран проводится по адресу строк, у меня были проблемы с работой библиотек (по непонятным прчинам он ругался на их использование).

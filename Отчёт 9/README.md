#Отчёт 9
## Савинков Глеб
### 8310
[Ссылка на проект1.](https://www.tinkercad.com/things/7qC2KFWbQne-surprising-fyyran-krunk/editel?sharecode=s_BiZyJX5rcA_rYMou-nM4O8_FpSxXRZ8htfSUGXYpE)
![Copy of keyboard and screen](https://user-images.githubusercontent.com/114941628/198122000-510a167f-71ca-442d-a695-897064448445.png)
## Листинг программы

///1
```C++
#include<Keypad.h> 
#include<LiquidCrystal.h>

int pressing,right=0;

String password_stp_total="1489";
String password_stp_option;
LiquidCrystal lcd(13, 12, 11, 10, 9, 8);
const byte ROWS = 4; 
const byte COLS = 4;
char hexaKeys[ROWS][COLS] = 
{
{'1','4','7'},
{'2','5','8'},
{'3','6','9'},
};
byte rowPins[ROWS] = {4,3,2};
byte colPins[COLS] = {7,6,5}; 
Keypad customKeypad = Keypad( makeKeymap(hexaKeys), rowPins, colPins, ROWS, COLS); 
void setup(){
lcd.begin(16, 2);
Serial.begin(9600);
}
void loop(){
  if (password_stp_option!="1489")
  {
    lcd.begin(16, 2);
    lcd.print("enter password");

    while(1)
    {
      char customKey = customKeypad.getKey(); 
      if (customKey)
      {
          pressing++;
          lcd.clear();
          password_stp_option+=customKey;
          lcd.print(password_stp_option);
          if (customKey==password_stp_total[right])
          {
              right++;
          }
          else
          {
              right=0; 
          }
          if (pressing==4)
          {
              if (right==4)
              {
                lcd.clear();
                lcd.print("welcome");
                delay(1000);
                right=0;
                pressing=0;
                password_stp_option="1489";
                lcd.clear();
                break;
              }
              if (right<4)
              {
                lcd.clear();
                lcd.print("Invalid password");
                delay(1000);
                right=0;
                pressing=0;
                password_stp_option="";
                lcd.clear();
                break;
              }
          }
      }
  	}
  }  
  else
  {
    char customKey = customKeypad.getKey(); 
      if (customKey)
      {
        Serial.println(customKey);
        lcd.setCursor(0,0);
        lcd.print(customKey);
      if (customKey=='1'||customKey=='4'||customKey=='8'||customKey=='9')
        {
            lcd.setCursor(0,1);
            lcd.print("even");
        }
      else
        {
            lcd.setCursor(0,1);
            lcd.print("odd ");
        }
      }
  }
}

```

## Пояснение
В данной работе нам надо пересобрать панель клавиатуры в коде, после чего подлеючить на них включение и выключение светодиодов. Для дольнейшей работы задаём 
String password_stp_total="24685";
String password_stp_option;
Пароль 1489

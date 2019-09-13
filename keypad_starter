#include <Keypad.h>
int i = 0 , counter = 0 , buzzer = 12;
char code[] = "2406*";
const byte ROWS = 4; //four rows
const byte COLS = 4; //three columns
char keys[ROWS][COLS] = {
  {'1','2','3','A'},
  {'4','5','6','B'},
  {'7','8','9','C'},
  {'*','0','#','D'}
};

byte rowPins[ROWS] = {2, 3, 4, 5}; //connect to the row pinouts of the keypad
byte colPins[COLS] = {6,7,8,9}; //connect to the column pinouts of the keypad

Keypad keypad = Keypad( makeKeymap(keys), rowPins, colPins, ROWS, COLS );

void setup(){
   Serial.begin(9600);
   pinMode(10,OUTPUT);
   pinMode(11,OUTPUT);
   pinMode(buzzer,OUTPUT);
}
  
void loop(){
 while (i<5)
 {
    char key = keypad.getKey();
    // just print the pressed key
    if (key)
    {
          Serial.println(key);
        
                  if ( key == code[i] )
                  {  
                   counter++;
                  }
                  else
                  {
                   counter = 0;
                  }
         ++i;         
     }
        
        if(i == 5)
        {
         if(counter == 5 )
          {
          Serial.println("success");
         digitalWrite(10,HIGH);
         delay(500);
         for(i=0;i<100;i++)// output a frequency sound
          { 
          digitalWrite(buzzer,HIGH);// sound
          delay(7);//delay1ms 
          digitalWrite(buzzer,LOW);//not sound
          delay(7);//ms delay 
          }
          for(i=0;i<100;i++)// output a frequency sound
          { 
           digitalWrite(buzzer,HIGH);// sound
          delay(7);//delay1ms 
          digitalWrite(buzzer,LOW);//not sound
          delay(7);//ms delay 
          }
          delay(4000);
          digitalWrite(10,LOW);
          }
          else 
          {
          Serial.println("fail");
          digitalWrite(11,HIGH);
          for(i=0;i<80;i++)// output a frequency sound
          { 
          digitalWrite(buzzer,HIGH);// sound
          delay(1);//delay1ms 
          digitalWrite(buzzer,LOW);//not sound
          delay(1);//ms delay 
          }
          for(i=0;i<80;i++)// output a frequency sound
          { 
           digitalWrite(buzzer,HIGH);// sound
          delay(1);//delay1ms 
          digitalWrite(buzzer,LOW);//not sound
          delay(1);//ms delay 
          }
          delay(3000);
          digitalWrite(11,LOW);
          } 
            counter = 0;
            i = 0;
        }
      }
    }

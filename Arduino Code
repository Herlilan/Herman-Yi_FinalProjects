// include library //
#include <IRremote.h>

// define IR sensor pin //
int IRsensorPin = 13;

// define the some functions used by the library //
IRrecv irrecv(IRsensorPin);
decode_results results;

// define motor drive control pins //
int RightMotorForward = 8;    // IN1
int RightMotorBackward = 9;   // IN2
int LeftMotorForward = 10;     // IN3
int LeftMotorBackward = 11;    // IN4


void setup(){
  
  // initialize motor control pins as output //
  pinMode(LeftMotorForward,OUTPUT);
  pinMode(RightMotorForward,OUTPUT);
  pinMode(LeftMotorBackward,OUTPUT);
  pinMode(RightMotorBackward,OUTPUT);

  // start serial communication to see hex codes //
  Serial.begin(9600);
  irrecv.enableIRIn();
}

void loop(){
  
  // if the sensor is receive any signal //
  if (irrecv.decode(&results)){
 
  }
  
  // hex codes//
  if(results.value == 16730805) MotorForward();
  if(results.value == 16718055) MotorBackward();
  if(results.value == 16716015) TurnRight();
  if(results.value == 16734885) TurnLeft();
  if(results.value == 16726215) MotorStop();
  
}

// FORWARD //
void MotorForward(){
  digitalWrite(LeftMotorForward,HIGH);
  digitalWrite(RightMotorForward,HIGH);
  digitalWrite(LeftMotorBackward,LOW);
  digitalWrite(RightMotorBackward,LOW); 
}

// BACKWARD //
void MotorBackward(){
  digitalWrite(LeftMotorBackward,HIGH);
  digitalWrite(RightMotorBackward,HIGH);
  digitalWrite(LeftMotorForward,LOW);
  digitalWrite(RightMotorForward,LOW);
}

/* TURN RIGHT */
void TurnRight(){
  digitalWrite(LeftMotorForward,HIGH); 
  digitalWrite(RightMotorForward,LOW);
  digitalWrite(LeftMotorBackward,LOW);
  digitalWrite(RightMotorBackward,HIGH);
}

// TURN LEFT //
void TurnLeft(){
  digitalWrite(RightMotorForward,HIGH);  
  digitalWrite(LeftMotorForward,LOW);
  digitalWrite(LeftMotorBackward,HIGH);
  digitalWrite(RightMotorBackward,LOW);
}

// STOP //
void MotorStop(){
  digitalWrite(LeftMotorBackward,LOW);
  digitalWrite(RightMotorBackward,LOW);
  digitalWrite(LeftMotorForward,LOW);
  digitalWrite(RightMotorForward,LOW);
}

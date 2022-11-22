//  || ROBOT ARM 4 DOF MENGGUNAKAN SERVO
// IBNUL SAHGIANTO 1901021076 UNIVERSITAS BUMIGORA TEKNOLOGI INFORMASI MATARAM
#include <Servo.h>
// Mengaktifkan Servo 
Servo servo_x ;
Servo servo_y ;
Servo servo_z ;
Servo servo_capit ;
// menentukan derajat tiap servo
int derajat_x = 90;
int derajat_y = 90;
int derajat_z = 85;
int derajat_capit= 90;
// input joystick ke pin analog
#define joystick_kiri_x A0
#define joystick_kiri_y A1
#define joystick_kanan_x A2
#define joystick_kanan_y A3
void setup() 
{
  // Menentukan pin signal servo dari arduino
  Serial.begin(9600);
  servo_x.attach(6);
  servo_y.attach(9);
  servo_z.attach(3);
  servo_capit.attach(5);  
}
void loop() 
{
  // Menentukan nilai analog dari pin analog
  int nilai_joystick_kiri_x = analogRead(joystick_kiri_x); // A0
  int nilai_joystick_kiri_y = analogRead(joystick_kiri_y); // A1
  int nilai_joystick_kanan_x = analogRead(joystick_kanan_x); // A2
  int nilai_joystick_kanan_y = analogRead(joystick_kanan_y); // A3

  // Menentukan pertambahan nilai derajat dengan nilai analog
  if (nilai_joystick_kiri_x < 340) derajat_y -=7; 
  else if (nilai_joystick_kiri_x >680) derajat_y +=7;
       
  if(nilai_joystick_kiri_y <340) derajat_capit -=5;
  else if (nilai_joystick_kiri_y > 680) derajat_capit +=5;

  if(nilai_joystick_kanan_x)derajat_x +=7;
  else if (nilai_joystick_kanan_x >680) derajat_x -=7;

  if(nilai_joystick_kanan_y <340) derajat_z -=7;
  else if(nilai_joystick_kanan_y >680)derajat_z +=7;
  derajat_x = min(175, max(20, derajat_x));
  derajat_y = min(150, max(5, derajat_y));
  derajat_z = min(145, max(15, derajat_z));
  derajat_capit = min(120, max(40, derajat_capit));
  /* melihat nilai serial
  Serial.println(" Nilai derajat x : ");
  Serial.print(derajat_x);
  Serial.println("| nilai derajat y : ");
  Serial.print(derajat_y);
  Serial.println("| nilai derajat z : ");
  Serial.print(derajat_z);
  Serial.println("| nilai derajat capit : ");
  Serial.println  (derajat_capit);
  */
  // output nilai derajat untuk servo
  servo_capit.write(derajat_capit);
  servo_x.write(derajat_x);
  servo_y.write(derajat_y);
  servo_z.write(derajat_z);
  
}

# GPRSBee_LP_SMS2var

This code send SMS text with SMSdata. SMSdata is time stamped RTC temperature and battery voltage value using GPRSBee. Low power is implemented every SLPNG seconds defined in the code.

Message received: 2015/2/9 11:31:35 Temp:26.25, Volt:4.26

#Configuration
Send SMS every SLPNG seconds and go to sleep. SMS massage contains is date and hour + RTC temperature + Battery voltage
  
  The code uses Stalker + GPRSBee
  
  
  Stalker:
    Jumper INT PD2 welded in Stalker to Use Interruption with RTC
    Jumper PD5-En welded in Stalker to swtich on and off bee power
    Cable from Bee port #9 to GPRSBEE_PWRPIN. The GPRSbee uses DTR pin (pin 9)  for software ON/OFF. Switching on or off is simply a matter of momentarily switching DTR high.
   Cable from bee port 12 to XBEECTS_PIN. The CTS pin (pin 12) is used for power status.If the CTS pin is high the GPRSbee is on, if it is low it’s off.
   
   Cable CTS and PWRPin from GPRSBee to Stalker In pins
  
  GPRSBEE_PWRPIN (Stalker) <--> pin#9 (GPRSBee)
  
  XBEECTS_PIN    (Stalker) <--> pin#12 (GPRSBee)
  
  Port0 (Stalker) <--> pin#1 (GPRSBee) Tx
  
  Port1 (Stalker) <--> pin#2 (GPRSBee) Rx
    
  
  
  To read from serial monitor in the computer, in Diag.h #define enable_diag 1 otherwise #undef. Define wich ports are going to be used with serial monitor RX/TX DIAGPORT_TX/DIAGPORT_RX
  
  #define ENABLE_DIAG     1
  
  UartSBee Gnd <--> Gnd Stalker
  
  UartSBee Rx <--> DIAGPORT_TX Stalker
  
  UartSBee TX <--> DIAGPORT_RX Stalker
  
  To program Stalker unconnect pin0 and 1 or take gprsbee out. (sharing ports 0 and 1 from Stalker)
  

##Libraries
https://github.com/SodaqMoja/GPRSbee

##Hardware
Stalker V2.3 http://www.seeedstudio.com/wiki/Seeeduino_Stalker_v2.3

GPRSBee http://www.gprsbee.com

# ENVIROCLOCK: MULTIFUNCTION ALARM CLOCK WITH ROOM TEMPERATURE DISPLAY 

## OBJECTIVE:
EnviroClock is a simple project using LPC2148 that shows the currenttime, alarm, and room temperature on an LCD. Users can set or change 
the time and alarm using a keypad. When the alarm time is reached, a buzzer sounds. Thesystem combines clock,  temperature sensing, and 
alarm features in oneeasy-to-use device.

## REQUIREMENTS:

### HARDWARE REQUIREMENTS:
1. LPC2148
2. LCD
3. KEYPAD
4. LED’S
5. LM35
6. BUZZER
7. SWITCHES
 
### SOFTWARE REQUIREMENTS:
1. PROGRAMMING IN EMBEDDED C
2. KEIL C COMPILER
3. FLASH MAGIC 

## PROJECT WORK FLOW

###  Peripheral Initialization:
LCD, LEDs, Keypad, RTC, ADC (LM35), and External Interrupt are initialized before entering the main super loop.

###  Main Loop Operations:
1.Continuously read current date & time from RTC and display on LCD along with the day.
2.Read room temperature using LM35 sensor via ADC and display it on LCD.
3.Check if current time = alarm time → Activate buzzer.
4.Alarm stops when the user presses alarm stop button; otherwise auto-stops after 1 minute.

###  RTC Correction Using Interrupt:

● A dedicated switch triggers an external interrupt if RTC time is incorrect.
● Normal operation pauses; LCD shows a menu with:
      1.Edit RTC Info
      2.Set Alarm
      3.Exit

###  Editing RTC Information:
      ● Selecting EDIT RTC INFO shows a submenu to modify:
         ● Hours
         ● Minutes
         ● Seconds
         ● Day
         ● Date
         ● Month
         ● Year
         ● Exit
      ● User enters values using keypad.
      ● System validates:
         ● Hours (0–23)
         ● Min/Sec (0–59)
         ● Date (1–31 depending on month & leap year)
         ● Month (1–12)
      ● Invalid inputs → Error message + retry.
      ● Valid inputs → RTC registers updated; LCD confirms update.

###  Setting the Alarm:
      
    ●  User enters alarm time (HH:MM) via keypad.
      
    ●  System validates and stores the alarm time.

### Overall System Functionality:

●  Real-time clock with temperature display.
  
●  Alarm feature with stop control.
  
●  User-friendly editing menus via interrupt & keypad.
  
●  Interactive multifunction clock + environment monitor.


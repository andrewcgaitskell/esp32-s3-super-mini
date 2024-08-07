# esp32-s3-super-mini

# arduino ide

    Board - ESP32C3 Dev Module
    Port - /dev/ttyACM0
    USB CDC on Boot - enabled
    JTAG Adapter - Integrated USB JTAG

# pins

        cable up
        pcb with chip up
        
        left
        
        5
        6
        7
        8
        9
        10
        20
        21
        
        right
        
        5v
        g
        3.3
        4
        3
        2
        1
        0

| Attempt | #1    | #2    |
| :---:   | :---: | :---: |
| Seconds | 301   | 283   |


# setting up the board for loading

    Entering download mode:
    Press and hold the BOOT button of ESP32C3,
    then press the RESET button,
    release the RESET button, and then release the BOOT button
    
    at this time, ESP32C3 will enter the download mode.
    
    (You need to re-enter the download mode every time you connect,
    sometimes you press it once,
    the port is unstable and will disconnect,
    you can judge it by the port recognition sound)

# Product Parameters

    Powerful CPU: ESP32-C3, 32-bit RISC-V single-core processor, running at up to 160 MHz
    WiFi: 802.11b/g/n protocol, 2.4GhHz, supports Station mode, SoftAP mode, SoftAP+Station mode, mixed mode
    Bluetooth: Bluetooth 5.0
    Ultra-low power consumption: Deep sleep power consumption is about 43μA
    Rich board resources: 400KB SRAM, 384KB ROM, built-in 4Mflash.
    Chip model: ESP32C3FN4
    Ultra-small size: as small as a thumb (22.52x18mm) Classic form factor, suitable for wearable devices and small projects
    Robust security features: Cryptographic hardware accelerator supporting AES-128/256, hashing, RSA, HMAC, digital signature, and secure boot
    Rich interfaces: 1xI2C, 1xSPI, 2xUART, 11xGPIO (PWM), 4xADC
    Single-sided components, surface mount design
    Onboard LED blue light:GPIO8 Pinout


# useful examples

    https://www.nologo.tech/product/esp32/esp32c3SuperMini/

    use Chrome or Chromium to translate Chinese to English
    
# Digital Pin

    // define led according to pin diagram
    int led = 8;
    
    void setup() {
      // initialize digital pin led as an output
      pinMode(led, OUTPUT);
    }
    
    void loop() {
      digitalWrite(led, HIGH);   // turn the LED on 
      delay(1000);               // wait for a second
      digitalWrite(led, LOW);    // turn the LED off
      delay(1000);               // wait for a second
    }

# Digital PWM

    int ledPin = 8;    // LED connected to digital pin
    
    void setup() {
      // declaring LED pin as output
      pinMode(ledPin, OUTPUT);
    }
    
    void loop() {
      // fade in from min to max in increments of 5 points:
      for (int fadeValue = 0 ; fadeValue <= 255; fadeValue += 5) {
        // sets the value (range from 0 to 255):
        analogWrite(ledPin, fadeValue);
        // wait for 30 milliseconds to see the dimming effect
        delay(30);
      }
    
      // fade out from max to min in increments of 5 points:
      for (int fadeValue = 255 ; fadeValue >= 0; fadeValue -= 5) {
        // sets the value (range from 0 to 255):
        analogWrite(ledPin, fadeValue);
        // wait for 30 milliseconds to see the dimming effect
        delay(30);
      }
    }

# Analog Pin

    const int sensorPin = A5;
    const int ledPin =  8; 
    
    void setup() {
      pinMode(sensorPin, INPUT);  // declare the sensorPin as an INPUT
      pinMode(ledPin, OUTPUT);   // declare the ledPin as an OUTPUT
    }
    
    void loop() {
      // read the value from the sensor:
      int sensorValue = analogRead(sensorPin);
      // turn the ledPin on
      digitalWrite(ledPin, HIGH);
      // stop the program for <sensorValue> milliseconds:
      delay(sensorValue);
      // turn the ledPin off:
      digitalWrite(ledPin, LOW);
      // stop the program for for <sensorValue> milliseconds:
      delay(sensorValue);
    }



    



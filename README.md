# 🚀 Transforming Raspberry Pi Pico into a Bad USB Device

## 📋 Table of Contents
1. 🔍 Introduction
2. 🛠️ What is a Bad USB?  
3. 🖱️ Understanding Rubber Ducky and Ducky Script  
4. ⚠️ Risks and Dangers of Bad USB Devices  
5. ⚖️ Legal Considerations  
6. 🛡️ Protecting Against Bad USB Attacks  
7. 📜 Step-by-Step Guide: Converting Raspberry Pi Pico into a Bad USB  
   - Quick Setup  
   - Detailed Setup  
8. ⚙️ Exploring Additional Functionalities with GPIO Pins
   - Setup Mode
   - USB Enable/Disable Mode
10. 📚 Conclusion
11. 🔗 References  


## 🔍 Introduction  

Welcome to this comprehensive guide where we explore how to transform a **Raspberry Pi Pico** 🛡️ into a **Bad USB device** 🖱️. Bad USB devices mimic trusted peripherals like keyboards to execute automated commands, often for penetration testing or educational purposes.  

This tutorial will explain:  
- What **Bad USB devices** are 🖥️.  
- How they function.  
- Potential dangers ⚠️ and how to protect yourself 🛡️.  
- Legal considerations ⚖️.  
- Step-by-step instructions to convert a Raspberry Pi Pico into a Bad USB device 🛠️.  
- Bonus: Advanced uses with GPIO pins! ⚙️  


## 🛠️ What is a Bad USB?  

A **Bad USB** device is a USB peripheral that emulates trusted devices, such as keyboards or network adapters, to execute pre-programmed tasks. These devices are often used in cybersecurity to test system vulnerabilities.  

### Key Characteristics:  
- **Looks harmless**: Often disguised as a USB flash drive 🔌.  
- **Acts maliciously**: Executes unauthorized commands ⚠️.  
- **Hard to detect**: Recognized as a "trusted" device by the operating system 🖥️.  


## 🖱️ Understanding Rubber Ducky and Ducky Script  

### 🐤 What is a Rubber Ducky?  
The **USB Rubber Ducky**, developed by Hak5, is a keystroke injection tool. It resembles a USB stick but operates as a programmable keyboard that can type at superhuman speeds 💨.  

### 📝 What is Ducky Script?  
**Ducky Script** is the scripting language used to program Rubber Ducky devices. It allows users to define sequences of keystrokes, delays, and special commands 🖋️.  

#### Example Ducky Script:  
```
REM Open Notepad
DELAY 1000
GUI r
DELAY 500
STRING notepad
ENTER
```
This script opens Notepad on a Windows machine and is executed in seconds ⏱️.  


## ⚠️ Risks and Dangers of Bad USB Devices  

Bad USB devices pose significant risks:  
- **Data theft**: They can steal sensitive information like credentials 🔑.  
- **Malware installation**: They can install backdoors or viruses 🐛.  
- **System compromise**: Execute commands to disrupt operations 🛑.  

> ⚠️ **Note**: These devices are difficult to detect and mitigate without proper security measures.  


## ⚖️ Legal Considerations  

**Using Bad USB devices without consent is illegal** 🚨. They should only be used for authorized penetration testing or educational purposes. Unauthorized use may result in:  
- Legal consequences ⚖️.  
- Reputation damage 🚫.  

> ✅ **Always ensure you have explicit permission before conducting security tests!**  


## 🛡️ Protecting Against Bad USB Attacks  

### How to Stay Safe:  
1. 🚫 **Avoid connecting unknown USB devices**.  
2. 🛡️ **Use USB protection tools** like endpoint security solutions.  
3. 🔒 **Educate users** about the dangers of Bad USB devices.  
4. 📜 **Implement device whitelisting** to limit USB device connections.  


## 🔧 What You'll Need:  
- Raspberry Pi Pico board 🔌.  
- Micro USB cable 📎.  
- Computer with internet access 🌐.  

## 🔧 Quick Setup: 

### 1. **Download CircuitPython**  
   - Go to the [CircuitPython download page](https://circuitpython.org/board/raspberry_pi_pico/) 🌐.  
   - Download the latest `.UF2` file for the Pico 💾.  

### 2. **Install CircuitPython**  
   - Hold the **BOOTSEL** button while connecting the Pico to your computer ⚙️.  
   - Drag and drop the `.UF2` file onto the **RPI-RP2** drive 🖥️.  
   - The Pico will reboot and appear as `CIRCUITPY` 💡.  

### 3. **Set Up HID Functionality**  
   - Download the [Adafruit HID library](https://github.com/adafruit/Adafruit_CircuitPython_HID) 📦.  
   - Copy the `adafruit_hid` folder to the `lib` directory on the `CIRCUITPY` drive 📂.  

### 4. **Write Your Payload**  
   - Create a Python script using the Adafruit HID library to execute a Ducky Script payload, or download the preconfigured script from [here](https://github.com/dbisu/pico-ducky/blob/main/code.py) 🎯.  
   - Save the script as `code.py` on the `CIRCUITPY` drive 🖋️.  

   **Example**:  
   ```python  
   import time  
   import board  
   import usb_hid  
   from adafruit_hid.keyboard import Keyboard  
   from adafruit_hid.keycode import Keycode  

   keyboard = Keyboard(usb_hid.devices)  

   time.sleep(1)  
   keyboard.press(Keycode.GUI, Keycode.R)  # Open Run  
   keyboard.release_all()  
   time.sleep(0.5)  
   keyboard.write("notepad\n")
   ```
   > Note: This script simulates the execution of a Ducky Script payload. Make sure to replace this with the payload you want to run.

### 5. **Find or Create a Ducky Script**  
   - You can find an existing Ducky Script payload [here](https://github.com/dbisu/pico-ducky/blob/main/payload.dd) 🌐, or create your own using Ducky Script.  
   - Save the Ducky Script as `payload.dd` in the root folder of your Pico 💾.
     
   > **Note**: Currently, the pico-ducky only supports DuckyScript 1.0, and some features of 3.0 ⚠️.

### 6. **Be Careful with Setup Mode**  
   - Ensure the device is in setup mode before you disconnect it from your computer ⚙️.  
   - If the device isn't in setup mode, it will reboot automatically 🔄 and execute the script within half a second 💨.  
   - Make sure to double-check before disconnecting the device to prevent unwanted execution of the payload 🚨.
.
### 7. **Test the Device Safely**  
   - After setting up the payload, safely test the device in an isolated environment 🛡️ (e.g., using a virtual machine or a non-essential system) to avoid potential harm to your computer 💻.  
   - Reconnect the Pico to the computer ⚡. The device will automatically execute the payload, so ensure you're in a safe environment before proceeding 🔐.



## 🔍 Detailed Setup

### 1. **Clone the Repository**  
   - Clone the repository to get preconfigured files:
     ```bash
     git clone https://github.com/dbisu/pico-ducky.git
     ```
   - This will provide you with the necessary scripts and files to get started.


### 2. **Download CircuitPython**  
   - Get the appropriate `.UF2` file for your Raspberry Pi Pico model:
     - [Raspberry Pi Pico](https://circuitpython.org/board/raspberry_pi_pico/) 🌐
     - [Raspberry Pi Pico W](https://circuitpython.org/board/raspberry_pi_pico_w/) 🌐
     - [Raspberry Pi Pico 2](https://circuitpython.org/board/raspberry_pi_pico_2/) 🌐
     - [Raspberry Pi Pico 2W](https://circuitpython.org/board/raspberry_pi_pico_2w/) 🌐
   - Make sure to download the latest version to ensure compatibility.


### 3. **Install CircuitPython**  
   - To install CircuitPython on your Pico, follow these steps:
     1. Hold down the **BOOTSEL** button on the Pico while connecting it to your computer ⚙️.
     2. After the Pico is connected, it will appear as a storage device called `RPI-RP2` 🖥️.
     3. Copy the downloaded `.UF2` file to the `RPI-RP2` drive.
     4. Once the file is copied, the device will reboot and will appear as `CIRCUITPY` 💡.

### 4. **Download Libraries**  
   - Download the [Adafruit CircuitPython Bundle](https://github.com/adafruit/Adafruit_CircuitPython_Bundle/releases) and extract the files.
   - From the extracted folder, copy the following libraries to the `lib` folder on your Pico:
     - `adafruit_hid`  
     - `adafruit_debouncer.mpy`  
     - `adafruit_ticks.mpy`  
     - `asyncio`  
     - `adafruit_wsgi`

### 5. **Add Required Files**  
   - After cloning the repo, copy the following files from the cloned repository to the root folder of your Pico:
     - `boot.py`
     - `duckyinput.py`
     - `code.py`
     - `webapp.py`
     - `wsgiserver.py`
   - These scripts are essential for making the Pico work as a Bad USB device.

### 6. **Configure Wi-Fi (Pico W Only)**  
   - If you're using a **Pico W** model and want to configure Wi-Fi, create a file named `secrets.py` in the root of your Pico and add the following content:
     ```python
     secrets = {
         'ssid': "YourAPName",
         'password': "YourAPPassword"
     }
     ```
   - Replace `"YourAPName"` and `"YourAPPassword"` with the actual credentials of your Wi-Fi network.

### 7. **Add Payload Script**  
   - Save your **Ducky Script** payload as `payload.dd` on the Pico.  
   > **Note**: Currently, the setup supports **DuckyScript 1.0** and partial **DuckyScript 3.0**.

### 8. **Run and Test**  
   - After everything is set up, disconnect and reconnect the Pico to execute the payload automatically.
   - The device will run the payload script when reconnected, simulating the keystrokes or actions defined in the DuckyScript.


## ⚙️ Exploring Additional Functionalities with GPIO Pins  

The GPIO pins on the Raspberry Pi Pico offer flexibility for advanced features:  

- **Custom Triggers**: Use buttons or switches to control payload execution 🔘.  
- **Status LEDs**: Indicate device state (e.g., ready, running, or error) 💡.  
- **Multi-Payload Support**: Implement multiple payloads based on GPIO pin states 🔀.  

### 🛠️ Setup Mode  

To edit the payload, enter setup mode by connecting **pin 1 (GP0)** to **pin 3 (GND)**. This will stop the Pico-Ducky from injecting the payload on your own machine.  

**Steps**:  
1. Use a jumper wire to connect **GP0** and **GND**.  
2. This will enable setup mode and prevent unintended payload execution.  

<img src="https://github.com/dbisu/pico-ducky/blob/main/images/setup-mode.png?raw=true">

### 🔒 USB Enable/Disable Mode  

If you want the Pico-Ducky to operate stealthily without appearing as a USB mass storage device, follow these instructions:  

1. **Enter Setup Mode**:  
   - Connect **GP0** to **GND** using a jumper wire.  

2. **Upload Payload**:  
   - Copy your payload script to the Pico-Ducky.  

3. **Disconnect**:  
   - Safely disconnect the Pico from your host PC.  

4. **Stealth Mode**:  
   - Connect a jumper wire between **pin 18 (GND)** and **pin 20 (GPIO15)**.  
   - This prevents the Pico-Ducky from showing up as a USB drive when plugged into the target computer.  

5. **Reprogram Mode**:  
   - Remove the jumper wire and reconnect the Pico to your PC to reprogram.  

<img src="https://github.com/dbisu/pico-ducky/blob/main/images/usb-boot-mode.png?raw=true">

### ⚙️ Default Modes  

- **Pico**: USB mass storage is enabled by default.  
- **Pico W**: USB mass storage is disabled by default.  

These configurations enhance security and flexibility for advanced use cases. 🔒


## 📚 Conclusion
Converting a Raspberry Pi Pico into a Bad USB demonstrates the importance of cybersecurity awareness 🛡️. While these devices have legitimate uses, they must be handled responsibly and ethically ⚖️. Stay informed, stay safe!

## 🔗 References

- [CircuitPython Download Page for Raspberry Pi Pico](https://circuitpython.org/board/raspberry_pi_pico/) 🌐  
- [Adafruit HID Library](https://github.com/adafruit/Adafruit_CircuitPython_HID) 📦  
- [Pico-Ducky Repository](https://github.com/dbisu/pico-ducky) 🔗  
- [DuckyScript 1.0 and 3.0 Documentation](https://github.com/hak5darren/USB-Rubber-Ducky/blob/master/docs/DuckyScript_Reference.md) 📝

## 📝 Credits

A large part of the information and setup process in this guide was sourced from the [pico-ducky repository](https://github.com/dbisu/pico-ducky/tree/main). Many thanks to the contributors for their excellent work in creating and documenting the project. Here's a breakdown of what was sourced:

- **Code for transforming Raspberry Pi Pico into a Bad USB device** 💻
- **Detailed setup instructions** 📖
- **DuckyScript implementation and examples** 🖥️

Check out their repository for more details and additional resources! 🚀

## ⚠️ Important Notice

⚠️ **Warning**: This repository and the instructions provided are for educational purposes only.  
Using a Raspberry Pi Pico as a Bad USB device can cause serious security risks if misused.  
Always be cautious and respect legal boundaries when working with these tools.  
The creator of this repository is not responsible for any misuse of the information shared.  
Use at your own risk!

---

Thank you for exploring this project! Always prioritize security and ethical practices when learning about hacking and cybersecurity.  
Stay safe, stay informed, and keep learning! 🚀


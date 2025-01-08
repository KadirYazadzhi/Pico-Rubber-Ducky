# 🚀 Transforming Raspberry Pi Pico into a Bad USB Device

## 📋 Table of Contents
1. [🔍 Introduction](#-introduction)  
2. [🛠️ What is a Bad USB?](#️-what-is-a-bad-usb)  
3. [🖱️ Understanding Rubber Ducky and Ducky Script](#understanding-rubber-ducky-and-ducky-script)  
4. [⚠️ Risks and Dangers of Bad USB Devices](#risks-and-dangers-of-bad-usb-devices)  
5. [⚖️ Legal Considerations](#legal-considerations)  
6. [🛡️ Protecting Against Bad USB Attacks](#protecting-against-bad-usb-attacks)  
7. [📜 Step-by-Step Guide: Converting Raspberry Pi Pico into a Bad USB](#step-by-step-guide-converting-raspberry-pi-pico-into-a-bad-usb)  
8. [⚙️ Exploring Additional Functionalities with GPIO Pins](#exploring-additional-functionalities-with-gpio-pins)  
9. [📚 Conclusion](#conclusion)  
10. [🔗 References](#references)  

---

## 🔍 Introduction  

Welcome to this comprehensive guide where we explore how to transform a **Raspberry Pi Pico** 🛡️ into a **Bad USB device** 🖱️. Bad USB devices mimic trusted peripherals like keyboards to execute automated commands, often for penetration testing or educational purposes.  

This tutorial will explain:  
- What **Bad USB devices** are 🖥️.  
- How they function.  
- Potential dangers ⚠️ and how to protect yourself 🛡️.  
- Legal considerations ⚖️.  
- Step-by-step instructions to convert a Raspberry Pi Pico into a Bad USB device 🛠️.  
- Bonus: Advanced uses with GPIO pins! ⚙️  

---

## 🛠️ What is a Bad USB?  

A **Bad USB** device is a USB peripheral that emulates trusted devices, such as keyboards or network adapters, to execute pre-programmed tasks. These devices are often used in cybersecurity to test system vulnerabilities.  

### Key Characteristics:  
- **Looks harmless**: Often disguised as a USB flash drive 🔌.  
- **Acts maliciously**: Executes unauthorized commands ⚠️.  
- **Hard to detect**: Recognized as a "trusted" device by the operating system 🖥️.  

---

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

---

## ⚠️ Risks and Dangers of Bad USB Devices  

Bad USB devices pose significant risks:  
- **Data theft**: They can steal sensitive information like credentials 🔑.  
- **Malware installation**: They can install backdoors or viruses 🐛.  
- **System compromise**: Execute commands to disrupt operations 🛑.  

⚠️ **Note**: These devices are difficult to detect and mitigate without proper security measures.  

---

## ⚖️ Legal Considerations  

**Using Bad USB devices without consent is illegal** 🚨. They should only be used for authorized penetration testing or educational purposes. Unauthorized use may result in:  
- Legal consequences ⚖️.  
- Reputation damage 🚫.  

✅ **Always ensure you have explicit permission before conducting security tests!**  

---

## 🛡️ Protecting Against Bad USB Attacks  

### How to Stay Safe:  
1. 🚫 **Avoid connecting unknown USB devices**.  
2. 🛡️ **Use USB protection tools** like endpoint security solutions.  
3. 🔒 **Educate users** about the dangers of Bad USB devices.  
4. 📜 **Implement device whitelisting** to limit USB device connections.  

---

## 📜 Step-by-Step Guide: Converting Raspberry Pi Pico into a Bad USB  

### 🔧 What You'll Need:  
- Raspberry Pi Pico board 🔌.  
- Micro USB cable 📎.  
- Computer with internet access 🌐.  

### 🛠️ Steps:  

1. **Download CircuitPython**  
   - Go to the [CircuitPython download page](https://circuitpython.org/board/raspberry_pi_pico/) 🌐.  
   - Download the latest `.UF2` file for the Pico 💾.  

2. **Install CircuitPython**  
   - Hold the **BOOTSEL** button while connecting the Pico to your computer ⚙️.  
   - Drag and drop the `.UF2` file onto the **RPI-RP2** drive 🖥️.  
   - The Pico will reboot and appear as `CIRCUITPY` 💡.  

3. **Set Up HID Functionality**  
   - Download the [Adafruit HID library](https://github.com/adafruit/Adafruit_CircuitPython_HID) 📦.  
   - Copy the `adafruit_hid` folder to the `lib` directory on the `CIRCUITPY` drive 📂.  

4. **Write Your Payload**  
   - Create a Python script using the Adafruit HID library to simulate keystrokes 🎯.  
   - Save the script as `code.py` on the `CIRCUITPY` drive 🖋️.  

   **Example Payload**:  
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
5. Test the Device
  - Reconnect the Pico to the computer. It will automatically execute the payload! 🎉

## ⚙️ Exploring Additional Functionalities with GPIO Pins
The GPIO pins on the Raspberry Pi Pico offer flexibility for advanced features:

- **Custom Triggers**: Use buttons or switches to control payload execution 🔘.
- **Status LEDs**: Indicate device state (e.g., ready, running, or error) 💡.
- **Multi-Payload Support**: Implement multiple payloads based on GPIO pin states 🔀.

**Example: GPIO-Based Trigger**
Connect a button to a GPIO pin and modify the script to wait for a button press before executing the payload.

## 📚 Conclusion
Converting a Raspberry Pi Pico into a Bad USB demonstrates the importance of cybersecurity awareness 🛡️. While these devices have legitimate uses, they must be handled responsibly and ethically ⚖️. Stay informed, stay safe!

## 🔗 References


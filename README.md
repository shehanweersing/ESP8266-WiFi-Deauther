# ESP8266-WiFi-Deauther

# 📡 ESP8266 WiFi Deauther Project

**An educational project to understand WiFi security and the 802.11 deauthentication vulnerability.**

## ⚠️ Disclaimer
**This project is intended for educational purposes and testing on your OWN networks only.**
Using this tool on networks you do not own or have permission to test is **illegal** and constitutes a Denial of Service (DoS) attack. The author takes no responsibility for any misuse of this information.

---

## 🧐 What is this?
This project uses an **ESP8266** development board (NodeMCU) to run the open-source [Deauther firmware](https://github.com/SpacehuhnTech/esp8266_deauther) created by Spacehuhn.

Many people confuse this tool with a "WiFi Jammer," but it is actually a **Deauthentication Tool**.
* **Jammer:** Creates noise on the 2.4GHz spectrum to physically block signals (Illegal).
* **Deauther:** Sends specific WiFi management packets (frames) that tell a device to disconnect from a router.

This tool demonstrates a flaw in the older 802.11 WiFi standard where these "management frames" are not encrypted, allowing anyone to spoof them.

## 🛠️ Hardware Used
* **Microcontroller:** NodeMCU (ESP8266) / Wemos D1 Mini
* **Cable:** Micro-USB Data Cable
* **Computer:** Windows PC (for flashing)

## ⚡ How It Works
The attack works by exploiting the lack of encryption in management frames on older WiFi networks.
1.  **Scan:** The ESP8266 listens for WiFi access points and connected clients.
2.  **Spoof:** It mimics the MAC address of the target router.
3.  **Attack:** It sends a "Deauthentication Frame" to the target device (client).
4.  **Result:** The client believes the router sent the request and disconnects immediately.

## 📥 Installation Guide
To replicate this project, follow these steps:

### Step 1: Drivers
Ensure your computer can talk to the ESP8266. You likely need one of these drivers:
* **CP2102** (for square chips)
* **CH340** (for rectangular chips)

### Step 2: Flashing Firmware
The easiest method is using the web installer:
1.  Connect the ESP8266 to the PC.
2.  Go to [esp.deauther.com](https://esp.deauther.com).
3.  Click **Connect** and select the correct COM port.
4.  Click **Install Deauther**.

## 🎮 How to Use
1.  Power up the ESP8266.
2.  Connect your phone/PC to the WiFi network named **`pwned`** (Password: `deauther`).
3.  Open a browser and go to `192.168.4.1`.
4.  **Scan** for networks.
5.  **Select** your own test network.
6.  Go to the **Attack** tab and start the "Deauth" attack.

## 🛡️ How to Protect Yourself
The only way to stop this attack is to use the **802.11w** standard (Protected Management Frames).
* Most modern routers have this feature, but it is often disabled by default to support older devices.
* If 802.11w is enabled, the device will ignore the fake disconnect packets because they are not properly signed by the router.

## 👏 Credits
* **Firmware Creator:** [SpacehuhnTech](https://github.com/SpacehuhnTech)
* **Project Documentation:** [Your Name/GitHub Handle]

---
*Created for educational exploration of cybersecurity concepts.*

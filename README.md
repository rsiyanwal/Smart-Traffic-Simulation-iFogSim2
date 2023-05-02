## Download
Download the **SmartTrafficSimulation.jar** from the release Smart-Traffic-Evaluation-v1.0.1.

## iFogSim information (Not needed for the Release to work)
By adjusting parameters such as MIPS, RAM, bandwidth, busy power, and idle power, we identified the most suitable devices for our use case and determined the most energy-efficient devices with the lowest latency. A generic input for a simulation task in iFogSim is as follow,
| Input Name | Input Type | Description |
| ---------- | ---------- | ----------- |
| MIPS | int | Million Instructions Per Second|
| RAM (MB) | int | Random Access Memory |
| Uplink Bandwidth (MB) | int/float | The upload speed of the network to which your device is connected |
| Downlink Bandwidth (MB) | int/float | The download speed of the network to which your device is connected |
| Level | int | Level of the Device in your fog-architecture (0 means Cloud) |
| Rate Per MIPS | int/float | Amount payable per MIPS |
| Busy Power (W) | float | Max power consumption of your device |
| Idle Power (W) | float | Min power consumption of your device|

Table below lists the specifications of Raspberry Pi models, and specifications of other devices.
| Devices | NodeMCU | RPi2 | RPi3 | RPi3B+ | RPi3A+ | RPi4B | Jetson NX | NUC 11 | LP Delta | PN50 |
| ------- | ------- | ---- | ---- | ------ | ------ | ----- | --------- | ------ | -------- | ---- |
| MIPS | 80 | 298.7 | 460.9 | 526.7 | 536.23 | 2037.3 | 36288 | 44000 | 3500 | 20000 |
| RAM | 4 | 512 | 1024 | 1024 | 512 | 4096/8192 | 16384 | 65536 | 4096 | 32768 | 
| UpBw | - | 24.4 | 49.2 | 97.6 | 93.7 | 114 | 600 | 2400 | 1000 | 2400 |
| DwBw | 2 | 17 | 17 | 62.45 | 62.45 | 62.45 | - | - | - | - |
| Busy Pw | 0.41 | 5.9 | 5.9 | 6.4 | 5.4 | 7.6 | 30 | 40 | 15 | 60 |
| Idle Pw | 0.0016 | 2.1 | 2.1 | 2.9 | 1.2 | 3.4 | 10 | 10 | 5 | 10 | 


## Arguements for the Simulation Jar File
To execute the simulation JAR file, you need to provide five integer arguments, which are: the count of proxy servers, the number of fog nodes per proxy server, the number of cameras per fog node, the device type of the proxy server, and the device type of the fog node. 

Although all arguments are integers, selecting a device type requires inputting an integer code corresponding to the desired device. The device types are encoded as follows:

| Integer Code | Device Type |
| ------------ | ----------- |
| 1 | Raspberry Pi 2 |
| 2 | Raspberry Pi 3 |
| 3 | Raspberry Pi 3B+ |
| 4 | Raspberry Pi 3A+ |
| 5 | Raspberry Pi 4B 4GB |
| 6 | Raspberry Pi 4B 8GB |
| 7 | Nvidia Jetson NX |
| 8 | Intel NUC 11 |
| 9 | LattePanda Delta |
| 10 | Asus PN50 |

## Examples
Suppose you want to get the simulation for the following setting:
| Arguements | Value |
| ----------------------- | - |
| Number of Proxy Servers | 1 |
| Numver of Fog Nodes per Proxy Server | 4 |
| Number of Cameras per Fog Node | 16 |
| Proxy Server Device | Raspberry Pi 4B 4GB |
| Fog Node Device | Intel NUC 11 |

Then your command will be as follow,
```
java -jar SmartTrafficSimulation.jar 1 4 16 5 8
```
You can execute the command on linux terminal or PowerShell or CMD

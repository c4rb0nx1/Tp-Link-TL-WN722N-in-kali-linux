## Monitor Mode & Packet injection with Tp-Link "TL-WN722N" v2/v3 20 in kali linux Fix the TP-Link TL-WN722N (v2/v3) WiFi Adapter in Kali Linux so you can use it for monitoring WiFi networks. 

You can get the adapter to inject packets and set monitor mode once you update the drivers as mention!

### Use these commands to get the adapter working on Kali for packet injection and monitoring:
### Commands:
```python
sudo apt update
sudo apt upgrade
sudo apt install bc
sudo apt-get install build-essential 
sudo apt-get install libelf-dev 
```

If the below command shows errors try "sudo apt dist-upgrade" and execute the given below command  
```python 
sudo apt-get install linux-headers-`uname -r` 
```

```python
sudo apt install dkms
sudo rmmod r8188eu.ko
git clone https://github.com/aircrack-ng/rtl8188eus
cd rtl8188eus
sudo -i
echo "blacklist r8188eu" > "/etc/modprobe.d/realtek.conf"
exit
sudo reboot
sudo apt update
cd rtl8188eus
sudo make
sudo make install
sudo modprobe 8188eu
```

!To enable Monitor mode and test packet injection:
!=================================================
```python
sudo ifconfig wlan0 down
sudo airmon-ng check kill
sudo iwconfig wlan0 mode monitor
sudo ifconfig wlan0 up
iwconfig                             
sudo aireplay-ng --test wlan0
```


if the above method did not work then you may try this : 
```python https://github.com/KanuX-14/rtl8188eus ```

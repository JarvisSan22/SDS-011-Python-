# SDS-011-Python Repoisitory
Author: Danien Jarvis
Contacts: ee18dj@leeds.ac.uk or Jarvissan21@gmail.com

Python repository for the SDS011 on a RPI3. Functions for use with a GPS, DHT22 and Blinkt LED lights. 

# Repository details 
1. **AQ** {Logging scipts, go into this folder for run details}
   - **Data** {Folder to store data files }
   - **Scripts** 
     - 2 **DHT** {DHT repository}
     - 2 **DHT.py** {DHT 11 and 22 script}
     - 2 **GPS2.py** {GPS scipts}
     - 2 **sds_rec.py** {SDS011 get data sripts}
     - 2 **start.py**  {Start recording and logg data script}
     - 2 **status.py** {RPI3 status scripts, checks if running, and updates time}
     - 2 **variables.py** {RPI3 and sensors varaible script}
1. **AQ-Plot** {Plotter scripts, go into this folder for details on how to run}
   - **AQDataplot.py** {Main plotter scripts}
   - **AQMapfunctions.py** {Map plotting functions}
   - **AQfunctions.py** {Data file reading functions}
   - **Genlivehtml.py** {HTML interfacte functions}


  


# RPI3 set up 
```
sudo apt-get update
sudo apt-get upgrade
```

**WIfi set up** 
```
sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
```
add network

**Download this repository**
git clone https://github.com/JarvisSan22/SDS-011-Python



# GPS Set up 
GPS Dongle G-mouse, set up video for setting up the dolge GPS as the RPI3 clock !!!
https://www.youtube.com/watch?v=Oag9qYuhMGg
Buy link:

1st get gps module
```
sudo apt-get install gpsd gpsd-clients python-gps chrony
```
2nd  in terminal 
```
sudo nano /etc/default/gpsd
```
set the following
``` 
START_DAEMON=”true”
USBAUTO=”true”
DEVICES=”/dev/ttyACM0″
GPSD_OPTIONS=”-n”
```
3rd  in the terminal 
```
sudo nano /etc/chrony/chrony.conf
```
Add the following line to the end of the file:

```
refclock SHM 0 offset 0.5 delay 0.2 refid NMEA
```
3rd Reboot the RPI3 ""sudo reboot""

4th  check that both are active in the terminal
```
systemctl is-active gpsd
systemctl is-active chronyd
su
```
5th see the data
```
gpsmon -n
```



# Team viewer from Terminal 
https://pimylifeup.com/raspberry-pi-teamviewer/
1st set up  in terminal 
```
sudo dpkg -i teamviewer-host_armhf.deb
```
if that gives errors ""sudo apt --fix-broken install""

2nd set password 
```
sudo teamviewer passwd  {Your password}
```


3rd get ID
```teamviewer info```
if  TeamViewer ID is blank ""



# Blinkt set up install
Buy link: https://shop.pimoroni.com/products/blinkt
1st get the blinkt packages  
```
curl https://get.pimoroni.com/blinkt | bash
```
2nd fit the blinket o


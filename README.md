Freeboard Navigation Instruments and Chartplotter
=================================================

Freeboard is a new way to provide marine instruments and navigation tools over WIFI with low cost open hardware (Arduino and Raspberry Pi).

Freeboard interface pcb is available for hardware interfacing on your boat. See https://www.42.co.nz/freeboard/technical/interfacing/freeboardinterfaceboardv1.2/index.html

Goals
-----

 * minimal cost
 * maximum interoperability
 * support compass, wind, log, autopilot, charts, and other common uses.
 * use low cost commodity hardware for sensors and processors
 * support modern devices (PC, tablets, cellphones)
 * support for many simultaneous users
 * total system cost (less clients) <USD500
 * use common KAP/BSB or ENC map formats (US NOAA Raster charts work)
 * low power usage (currently 0.4A at 12v)

Thats achieved in a totally unique way, by providing the instruments and chartplotter via a web page over a local wifi link on your boat, so that any device with a web browser can access them.

This is the main server for the Freeboard server project.  

Install
-------

For a PC:

Select a suitable root directory, with no spaces in the path! eg /home/robert or C:\boat
Make sure you have sun (oracle) java7+ installed in the path somewhere
Make sure you have git installed
```
git clone --depth=1 https://github.com/rob42/freeboard-server.git
cd freeboard-server
./startpc.sh (or startpc.bat on windows)
```

For a Raspberry Pi (running Raspbian Jessie):

see [README_install_Pi](README_install_Pi.md)

See http://www.42.co.nz/freeboard for more.


Updating
--------

Login as you did before, (the pi or pc needs to be connected to the internet)
```
cd freeboard-server
```
make a note of your current version in case you want to revert
```
git reflog
```
You will see something like :
```
pi@mot:~/freeboard-server$ git reflog
6a096cd HEAD@{0}: commit: Fix merge, disable defunct autoincrement plugin
9b2f926 HEAD@{1}: 9b2f9267ad6f827c268e17ecc156b987fec96fab: updating HEAD
etc
```
Write down the first ref key (6a096cd).
```
git pull
```
This should bring in any updates, but not affect your settings. Dont worry if bad stuff happens, git can roll back and forwards!
To revert use :
```
git reset --hard 6a096cd
```
You did write down the ref key didnt you :-)




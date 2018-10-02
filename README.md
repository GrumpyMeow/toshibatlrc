# ToshibaTLRC Python Package

Installation
------------

-  ``pip3 install git+https://github.com/grumpymeow/toshibatlrc.git``

About
=====

``ToshibaTLRC`` is a Python library for remote communication with Toshiba TL-series TVs 

Requirements
============

Python 3.3 or 3.4 is required.

Usage
=====

```python

#new instance for TV at 192.168.1.25
toshibatlrc = ToshibaTLRC('192.168.1.25')

#connect to the instance (or register)
pin = '1878'
toshibatlrc.connect(pin, 'my_device_id', 'my device name')

#check connection
if toshibatlrc.is_connected():

  #get power status
  power_status = toshibatlrc.get_power_status()
  print (power_status)

  #get playing info
  playing_content = toshibatlrc.get_playing_info()

  #print current playing channel
  print (playing_content.get('title'))

  #get volume info
  volume_info = toshibatlrc.get_volume_info()

  #print current volume
  print (volume_info.get('volume'))

  #change channel
  toshibatlrc.play_content(uri)
  
  #get app list
  app_info = toshibatlrc.load_app_list()
  print (app_info)
  
  #start a given app
  toshibatlrc.start_app("Netflix")

  #turn off the TV
  toshibatlrc.turn_off()


# kdevice-gabbler-finder
A bash tool to find new devices on your LAN network.

If there are devices on your lan network with [kdevice-gabbler](https://github.com/lemyskaman/kdevice-gabbler) properly installed, then this script will help you to find them.

## How it Wokrs
When is runing this script will make curl requests in a loop, varying the tail (last segment of a ip address) from 0 to 255, displaying a list with the ip and the hostname of any device in your lan with [kdevice-gabbler](https://github.com/lemyskaman/kdevice-gabbler) running.

## Setup
Fisrt grab a copy of the project 

    $ git clone https://github.com/lemyskaman/kdevice-gabbler.git

 then get in the project folder

    $ cd kdevice-gabbler

Then if you have **curl** installed just run the script as any other executable file

    $ ./kdevice-gabbler-finder

or 
    
    $ bash kdevice-gabbler-finder


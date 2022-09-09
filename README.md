# kdevice-gabbler-finder
A bash tool to find new devices on your LAN network.

Lets say you connect your screenless [raspberry-pi](https://www.raspberrypi.com/products/raspberry-pi-4-model-b/) sbc to a local network, or you just started your headless virtual machine with a bridged network adapter. Then you need  

When runned this script will make curl requests in a loop, varying the tail (last segment of a ip address) from 0 to 255, using your current local network ip as reference. 



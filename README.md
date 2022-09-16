# kdevice-gabbler-finder
A bash tool to find new devices on your LAN network.

If there are devices on your lan network with [kdevice-gabbler](https://github.com/lemyskaman/kdevice-gabbler) properly installed, then this script will help you to find them.

## How it Wokrs
When is runing this script will make curl requests in a loop, varying the tail (last segment of a ip address) from 0 to 255, displaying a list with the ip and the hostname of any device in your lan with [kdevice-gabbler](https://github.com/lemyskaman/kdevice-gabbler) running.

## Dependencies 
The computer that runs this bash script must count with the curl command application, in debian derivative linux computers you can install it with apt like so:

    $ sudo apt install curl

## Usage
Fisrt grab a copy of the project 

    $ git clone https://github.com/lemyskaman/kdevice-gabbler.git

Then get in to the project folder

    $ cd kdevice-gabbler

Look throug the network interfaces, for the one you know that shares the same network where another device running [kdevice-gabbler](https://github.com/lemyskaman/kdevice-gabbler) is connected

    $ ifconfig

The above command should output something similar to this:

    gif0: flags=8010<POINTOPOINT,MULTICAST> mtu 1280
    stf0: flags=0<> mtu 1280
    en0: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
        options=50b<RXCSUM,TXCSUM,VLAN_HWTAGGING,AV,CHANNEL_IO>
        ether ac:87:a3:01:5d:57 
        inet6 fe80::16:f122:554b:f36b%en0 prefixlen 64 secured scopeid 0x4 
        inet6 fd00::186a:aac4:c757:6b43 prefixlen 64 autoconf secured 
        inet6 2806:106a:19:85c:1081:5d6:e777:ab2a prefixlen 64 autoconf secured 
        inet6 2806:106e:19:85c:c094:6598:18ad:629 prefixlen 64 autoconf temporary 
        inet 192.168.1.78 netmask 0xffffff00 broadcast 192.168.1.255
        nd6 options=201<PERFORMNUD,DAD>
        media: autoselect (100baseTX <full-duplex,flow-control,energy-efficient-ethernet>)
        status: active
    en1: flags=8823<UP,BROADCAST,SMART,SIMPLEX,MULTICAST> mtu 1500
        options=400<CHANNEL_IO>
        ether 6c:40:08:a6:2b:d0 
        nd6 options=201<PERFORMNUD,DAD>
        media: autoselect (<unknown type>)
        status: inactive
    en2: flags=8963<UP,BROADCAST,SMART,RUNNING,PROMISC,SIMPLEX,MULTICAST> mtu 1500
        options=460<TSO4,TSO6,CHANNEL_IO>
        ether 82:15:01:83:b8:40 
        media: autoselect <full-duplex>
        status: inactive

Interfaces names of above list are the ones before (:) gif0, stf0, en0, en1,  and so one 

Next you just run this script:

    $ ./kdevice-gabbler-finder <network interface name>
    
or

    $ bash kdevice-gabbler-finder <network interface name>

Where "network interface name" is the one connected to the network you want to search for a [kdevice-gabbler](https://github.com/lemyskaman/kdevice-gabbler) device

    


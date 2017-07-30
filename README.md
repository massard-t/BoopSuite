BoopSuite
===

# Synopsis:

BoopSuite is an up and coming suite of wireless tools designed to be easy to use
and powerful in scope, that support both the 2 and 5 GHz spectrums. Written
purely in python. A handshake sniffer (CLI and GUI), a monitor mode enabling
script and a deauth script are all parts of this suite with more to come.

![This Used To Be An Image But Now It Is Not. :(](Images/Run.png "BoopSuite")

## Another Wireless pentesting suite.

+ A wireless sniffer
+ Two gui's for the wireless sniffer (old/new)
+ A wireless deauther
+ A monitor mode enabler and disabler

### Note:

I hope my project can aid everyone in their pentesting needs, and this project
is going to continue to grow as I add new handlers for additional packet types.

Changelog located in CHANGELOG file.

Hopefully others find it useful. If you do please email me and let me know I
would love to hear about it.

[![Donate](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=43LHEBX448Y48&lc=US&item_name=M1ND%2dB3ND3R&currency_code=USD&bn=PP%2dDonationsBF%3abtn_donateCC_LG%2egif%3aNonHosted)


## What else is coming?

I am going to add scripts to do the following:
+ BoopCoil   - Deauth attack detector
+ BoopDate   - A script to update boopsuite

More ideas are welcome.
Email me @: jacobsin1996@gmail.com

# Examples:

![This Used To Be An Image But Now It Is Not. :(](Images/Running.png "BoopSuite")

#### To start sniffing:

`boopsniff -i wlan1mon`

#### To specify a channel:

`boopsniff -i wlan1mon -c 6`

#### Boop also works on the 5ghz spectrum if you have a supporting card:

`boopsniff -i wlan1mon -f 5`

#### If some processes are interfering then you can preemptively kill them with:

`boopsniff -i wlan1mon -k`

#### If you want to see unassociated clients:

`boopsniff -i wlan1mon -u`

#### If you want to filter by a specific AP mac address:

`boopsniff -i wlan1mon -a xx:xx:xx:xx:xx:xx`

#### To launch a deauth attack:

`boopstrike -i wlan1mon`

#### Deauth the 5ghz spectrum:

`boopstrike -i wlan1mon -f 5`

#### Deauth a single AP:

`boopstrike -i wlan1mon -a xx:xx:xx:xx:xx:xx`

#### Deauth everyone except one Access Point:

`boopstrike -i wlan1mon -s xx:xx:xx:xx:xx:xx`

#### New Update includes a gui tool:

`boopsniff_gui`

#### Set card to monitor mode:

`boop -i wlan1`

#### Set card to managed mode:

`boop -i wlan1mon`

#### Set card to a specific name:

`boop -i wlan1 -n boop1`

note: will enable or disable monitor mode accordingly.

#### Set channel on card:

`boop -i wlan1 -c 11`

Note: Will do error checking if you specify a channel the card doesnt support and is ready for cards supporting the 5GHz network.

#### Kill any interfering tasks:

`boop -i wlan1 -k`

#### Put it all together:

`boop -i wlan1 -n boop1 -c 11 -k`

NOTE: boop will always switch the mode from managed to monitor and vice versa.

I'm working on updating the GUI so it will be much cleaner and way better looking,
stay tuned.

![This Used To Be An Image But Now It Is Not. :(](Images/GUI.png "BoopSuite")

Note: all pcap files will be saved in the directory ~/pcaps

# Computer Usage

The sniffer which is the heaviest CPU part uses really low CPU and memory,
memory which is going to shrink in upcoming versions.

![This Used To Be An Image But Now It Is Not. :(](Images/Top.png "BoopSuite")

#### More options are coming in the future.

# Installation:

#### To install open a terminal and type:

```
git clone https://github.com/M1ND-B3ND3R/BoopSuite.git
cd BoopSuite
pip install -r requirements.txt
chmod +x install.py
./install.py
```

The setup includes creating symbolic links for the tool so it can be run from
anywhere.

# Upgrade:

#### To upgrade open a terminal and type:

##### Requires root to install

Root is dangerous so always check packages before running them as root.
My code is not malicious, however, you should always be wary.

```
git clone https://github.com/M1ND-B3ND3R/BoopSuite.git
cd BoopSuite
chmod +x install.py
./install.py
```

# Reference:

The top line is formatted as follows for the sniffer:

`[+] Time: TIME_ELAPSED Slithering: [CHANNEL] - [boopstrike: RECENT HANDHAKE CAPTURED] - [AMOUNT OF HANDSHAKES]`

Next line is the start of the Access Point table and is formatted as follows:

`[Mac address] [Encryption] [Channel] [Vendor] [Signal] [Beacons] [SSID]`

The Line that starts the client table is formatted as follows:

`[Mac address] [AP Mac address] [Noise] [Signal] [AP SSID]`


# Contributors:

+ M1ND-B3ND3R
+ Sean Bangerter - Proofing my readme
+ Boop - My pet ball python

# Motivation:

I am motivated by the want to be better. To prove others wrong and to prove
to myself that I can do things that were previously impossible to me.

# In Progress:

+ Wireless card discovery in VM for kali.

+ Code Fixes will be happening.

# License:

MIT License
(c) Jarad Dingman, 2017

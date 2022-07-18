# AutoPortConfig-PIAandTransmission
This repo is pretty simple, it is just to auto configure transmission (p2p software) with the port updates provided by PIAs manual connections script. Not affiliated with PIA but built on top of their scripts with just some minor modifications to accomodate my use case.

Still working on making this fully functional but here is where I am at, I was mainly concerned with getting it functional for my use case.

WIP: 
- Fix permissions
- Configure full suite of customizations via arguments
- Test/Configure OpenVPN
- Manual region selection
- Test and Add directions for a cronjob on boot.
- Add flags for transmission credentials.

Directions: copy the repo, navigate into the root repo folder, until permissions are fixed you may need to run (MAKE SURE YOU'RE IN THE REPO FOLDER LOL):

sudo chmod 755 *

Next you want to configure you username and password for transmission. Edit the port forwarding file with:

nano port_forwarding.sh

Then edit lines 22 and 23 to include your username/password for transmission, at the moment the default username and password is setup in the script.

Typical usage would be something like this:

sudo bash ./run_setup.sh -u YOURPIAUSERNAME -p 'YOURPIAPASSWORD' -f true -i y -s n -v w

-u is your username
-p is your password
-f is true or false for port forwarding
-i is y for yes or n for no for whether or not to disable IPv6
-s is for yes or no for whether you want to manually select a server, manual selection is not set up with the script yet.
-v is for wireguard or openvpn, only wireguard has been tested.


```
▓▓▓▓▓▓▓▓▓▓▓▓▓ ▓▓▓▓ ▓▓▓▓     ▓▓▓▓ ▓▓▓▓     ▓▓▓▓ ▓▓▓▓ ▓▓▓▓▓▓▓▓▓▓▓▓▓ ▓▓▓▓
▓▓▓▓     ▓▓▓▓      ▓▓▓▓     ▓▓▓▓ ▓▓▓▓▓▓   ▓▓▓▓      ▓▓▓▓              
▓▓▓▓▓▓▓▓▓▓▓▓▓ ▓▓▓▓ ▓▓▓▓     ▓▓▓▓ ▓▓▓▓ ▓▓▓ ▓▓▓▓ ▓▓▓▓ ▓▓▓▓▓▓▓▓▓     ▓▓▓▓
▓▓▓▓          ▓▓▓▓ ▓▓▓▓     ▓▓▓▓ ▓▓▓▓   ▓▓▓▓▓▓ ▓▓▓▓ ▓▓▓▓          ▓▓▓▓
▓▓▓▓          ▓▓▓▓ ▓▓▓▓▓▓▓▓▓▓▓▓▓ ▓▓▓▓     ▓▓▓▓ ▓▓▓▓ ▓▓▓▓          ▓▓▓▓

```

## piunifi.sh
A bash script to automate the setup and configuration of a Raspberry Pi for use as a UniFi Controller for Ubiquiti network devices.

## IMPORTANT  
**If you already have a Unifi Controller running on the same network which you intend to replace with this piunifi you should backup the network settings from the existing controller to a file. This file can then be imported into the piunifi controller. Otherwise you will have to reset all your network devices to adopt them under the new piunifi controller.**

## Usage
**Method 1:** Clone and run locally. You can edit and modify script to suit using this method.

`git clone https://github.com/piscripts/piunifi.git`

`sudo bash piunifi/piunifi-setup.sh`

**Method 2 (Quick easy setup):** Just use the curl or wget command lines shown below for a one-step install.

`sudo bash -c "$(curl -fsSL https://raw.githubusercontent.com/bradmarkley/piunifi/main/piunifi.sh)"`

`sudo bash -c "$(wget -O- https://raw.githubusercontent.com/bradmarkley/piunifi/main/piunifi.sh)"`

## Known issues

You will need to ignore the browser SSL certificate error when accessing UniFi controller web interface. If you are accessing from a trusted private internal network this may not be an issue. However, if intend on access securely from an external/public network you should install a valid SSL certificate. There are a number of existing articles and videos on how to do this.

## Troubleshooting

Give the unifi service a few minutes to start upon reboot.  
The web interface is accessed on port 8443 and you must use https not http (Example: https://IPADDRESSOFPI:8443)  

If you still cannot access the web interface try checking the status of the service with the following command:  
`sudo systemctl status unifi`

The command output should contain `Starting unifi...` and eventually `Started unifi.`  
Otherwise check for errors in the status output.

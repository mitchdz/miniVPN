## miniVPN

This project is following SEEDLabs VPN-labs. To execute the lab, multiple virtual machines will need to be created. The table below shows the networking table that we try to achieve.

| machine | IP |
| ------- | -- |
| client | **10.0.2.7 (NAT)** |
| server | **10.0.2.8 (NAT)** & **192.168.60.1 (vpnnet)** |
| target | **192.168.60.101 (vpnnet)** |

The following software versions are utilized:
* hypervsior - Virtualbox 5.2.34_Ubuntu r133883
* guest OS - ubuntu-18.04.4-desktop-amd64


## VirtualBox settings

Do the following instructions through Virtualbox in order to set up the internal network between the server and the target

# 1. Server

* open up the settings of the **server** virtual machine

* click `Network` in the left column

* Open `Adapter 2` tab on the top (Leave Adapter 1 alone)

* Create an internal network by changing the `Attached to:` dropdown to `Internal Network`, and then give the network a name. We used vpnnet.

<img src="virtualbox-media/networking_server.png" alt="Gateway Settings" style="width: 460px;"/>

# 2. Target
* open up the settings of the **target** virtual machine

* click `Network` in the left column

* Open `Adapter 2` tab on the top (Leave Adapter 1 alone)

* Create an internal network by changing the `Attached to:` dropdown to `Internal Network`, and then give the network a name. We used vpnnet.

<img src="virtualbox-media/networking_target.png" alt="Gateway Settings" style="width: 460px;"/>


## Setting up networking in the virtual machine
# 1. Server
Log into your server machine and on the top right click the icon to open the dropdown menu.

<img src="virtualbox-media/setting_up_server_1.png" alt="Gateway Settings" style="width: 460px;"/>

You will notice that there are two 'ethernet' connections, and they will most likely be different names for you. We notice there that enp0s3 is up which is the NAT network, and enp0s8 is down which is the vpnnet network.

<img src="virtualbox-media/setting_up_server_2.png" alt="Gateway Settings" style="width: 460px;"/>

Click the `Wired Settings` option for the second ethernet option.

<img src="virtualbox-media/setting_up_server_3.png" alt="Gateway Settings" style="width: 460px;"/>

You will notice that two connections again , click the cog icon to the right of enp0s8 (the adapter name may be different for you)

Follow each step:
* click the `IPv4` tab on the top

* check off `Manual` in the IPv4 Method section instead of 'Automatic(DHCP)'

* Write the following networking settings shown below, and then click apply.

<img src="virtualbox-media/setting_up_server_4.png" alt="Gateway Settings" style="width: 460px;"/>

\

Now follow the same steps on the other network interface. In this case, the name was enp0s3.

<img src="virtualbox-media/setting_up_server_alt.png" alt="Gateway Settings" style="width: 460px;"/>

# 2. Target
Similar to Server, set up the networking as such:

<img src="virtualbox-media/setting_up_target_1.png" alt="Gateway Settings" style="width: 460px;"/>

# 3. Client
Similar to Server, set up the networking as such:
<img src="virtualbox-media/setting_up_client_1.png" alt="Gateway Settings" style="width: 460px;"/>


# Testing setup

Test that the server can ping the target:
* press `ctrl + alt + t` to open a terminal
* type in `ping -c 2 192.168.60.101`

You should get a response

<img src="virtualbox-media/setting_up_test_ping_server-target.png" alt="Gateway Settings" style="width: 460px;"/>










---
  ![UofA](images/UofA.jfif)

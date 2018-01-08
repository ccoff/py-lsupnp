py-lsupnp
=========
This is a Python 3 program that discovers all Universal Plug and Play (UPnP) devices on a network and lists them (lsupnp = list upnp). It does this by sending out an HTTP device discovery request to the SSDP multicast address and then listening for responses from UPnP devices.

For example, running this program on my home network reveals three UPnP devices: a NAS server, a Roku streaming player, and the router.

Tested on Linux and Windows; presumably Mac works also.

Usage
-----
Type `python3 py-lsupnp.py` at the command line. Alternatively, type `chmod 755 py-lsupnp.py` to enable starting the program directly (i.e., `./py-lsupnp.py`). The following command-line options are available:

**-p [port]**: Bind the source UDP port to the specified port number. This option is useful if you are running a firewall, because devices send their responses to the same UDP port that sent the discovery request. You can then add a firewall rule to allow device responses through on the specified port.

**-r**: Do a reverse DNS lookup on the IP address of any responding device.

**-t**: Specify the socket timeout interval in seconds.

**-v**: Display verbose information, such as raw HTTP headers and responses.


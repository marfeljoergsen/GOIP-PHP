# About

This small PHP program sends SMS messages using a GOIP GSM Gateway. The messages
are received through line command.

This is a standalone code snippet from a larger software project.

GOIP documentation (doc/goip_sms_Interface_en.pdf) is property of someone else,
most likely the GOIP manufacturer.

# System requirements
- A GOIP SMS Gateway
- Server with PHP > 5.4 working
- CLI access for the keepalive.php (not mandatory)

# Installation

1. Copy the project to a server that has IP access to the GOIP
2. Adjust GOIP's SMS settings (see screenshot in /doc)
3. Run keepalive.php to catch the port number (see screenshot in /doc)
4. Rename settings_dist.php as settings.php
5. Fill the blanks in settings.php
6. Start sending SMS messages through the line command

# Usage

## Sending messages

To send an SMS message, call the script like example below:

```
 $ php send.php 0121212123 "Hello World!"
```


## GOIP keep alive

keepalive.php listens to GOIP messages in a specific address and port (set in 
GOIP management) and responds to keepalive messages. This functionality is 
**NOT required** for sending SMS messages.

Usage: php keepalive.php SERVERIPADDRESS PORT

The IP address is the server's address that runs the keepalive.php as it binds 
to a specific address. Adjust the IP address and port accordingly with the
GOIP management. See screenshots from the doc directory. 

Use GNU Screen or similar to keep the script running on your server. On 
Windows just leave the terminal window open.

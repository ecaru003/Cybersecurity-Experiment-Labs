First attempt at a Man-in-the-Middle attack. 

Two physical devices (one Dell AIO, one Microsoft laptop) are connected by a Dell PowerConnect 2324.

The Dell AIO contains Ubuntu server VM, and is a Windows 10 host with Hyper-V.

The Ubuntu server is running a base installation of Apache2, using plain-text HTTP on port 80.

The goal was to employ ARP poisoning with IP forwarding to establish the laptop (attacker) as a MITM. 

The attack would be considered a success if:
    a) The host (Windows 10) does not have internet access disrupted
    b) The laptop is able to poison ARP entries and convince the switch to forward traffic intended for the Host to the laptop.
    c) The laptop is able to intercept traffic intended to arrive at the host (Windows 10)
    d) An HTTP packet is identified requesting the webpage (e.g., 'HTTP GET index.html' )

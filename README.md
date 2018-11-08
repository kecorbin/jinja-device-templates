# jinja-device-templates

An interactive script that builds device configurations based on user input using
[Jinja2](http://jinja.pocoo.org/docs/2.10/)

# Installation

1. Clone this repo

2. Install dependencies with `pip install -r requirements.txt`


# Single Device Sample

Generate config
```
$ python build_config.py
Enter Hostname: foo
Enter Loopback0 address e.g 1.1.1.1: 1.1.1.1
Enter Loopback0 mask e.g 255.255.255.255: 255.255.255.255
Enter SNMP read-only community: public
Enter SNMP read-write community: private
```

View Config
```
$ cat foo.cfg
hostname foo
!
interface Loopback0
 ip address 1.1.1.1 255.255.255.255
!
snmp-server community public ro
snmp-server community private rw
!%                                 
```

# Multiple Device Example

Alternatively, a CSV file can be used to easily to multiple devices.  

1. Modify devices.csv as necessary
2. Run from_csv.py

Python based command line client for VDC<br>
Requires apache libcloud 17.0 or newer,<br>
install with 'pip install apache-libcloud'<br>

```
 usage: vdcli [-h] [-a NAME] [-m RAM] [-t DCID] [-g IMGID] [-p VAPP] [-b | -j]
              [-v | -l | -c | -s | -d | -i | -x UUID | -r UUID]
 
 VDC CLI client
 
 optional arguments:
   -h, --help            show this help message and exit
   -a NAME, --create-name NAME
                         (create) node name
   -m RAM, --create-ram RAM
                         (create) node RAM size (MB)
   -t DCID, --create-dc DCID
                         (create) node datacenter id
   -g IMGID, --create-img IMGID
                         (create) node image id
   -p VAPP, --create-vapp VAPP
                         (create) node virtual app name
   -b, --verbose         verbose operation
   -j, --json            display json
   -v, --version         show program's version number and exit
   -l, --lversion        show libcloud's version and exit
   -c, --create-node     create node
   -s, --list-nodes      list machines
   -d, --list-datacenters
                         list datacenters
   -i, --list-images     list images
   -x UUID, --destroy-node UUID
                         destroy a node
   -r UUID, --reboot-node UUID
                         reboot a node
 
 Example node creation: ./vdcli --create-node --create-name "My VM" --create-
 ram 512 --create-dc 14 --create-img 1 --create-vapp "My VApp"
```

Before use, you must create a configuration file in your home directory called '.vdcli' <br>
This should contain the following:
```
[auth]
url=https://portal.claranet.com/api
username=<vdc username>
password=<vdc password>
```

If you wish to debug HTTP transactions, you may set the environment variable LIBCLOUD_DEBUG which should
be set to a file name to which the debug will be written to.

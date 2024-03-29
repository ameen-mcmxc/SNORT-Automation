# If you get error after "ldconfig" command

`
sudo find / -name ldconfig
`

`
export PATH=$PATH:/path/to/ldconfig
`


For example: -

`
export PATH=$PATH:/usr/sbin
`

## Add alias

`
alias snort='/path/to/bin/snort'
`


`
systemctl daemon-reload
`


`
alert icmp any any -> any any (msg:"ICMPv6 Spoofed Packet Detected"; icode:0; itype:0; ip6_src!= [2001:db8:ce:11b:0:cb00:7108:1b]; ether_src!= [00:0c:29:b3:80:01]; sid:1000001; rev:1;)
`


`
snort -T -c /etc/snort/snort.conf
`


`
snort -Q --daq dump -q  -R icmpv6_spoof.rules
`


## Snort 3


# To make sure the Snort 3 install knows where to find the appropriate LibDAQ that we installed earlier.

# LibDAQ is the "Data Acquisition Library", and at a high-level, it's an abstraction layer used by "modules" to communicate

# with both hardware and software network data sources.


`
alias snort='/etc/snort/bin/snort --daq-dir /usr/local/lib/daq_s3/lib/daq'
`



`snort --list-modules
`


`snort --help-module http_inspect 
`


`snort --help-module http_uri
`


`snort --help-config | grep http
`



## Inline Mode


`
export my_path=/etc/snort
`

`
snort -Q --daq afpacket -i "ens34:ens35"
`


`
snort -c $my_path/etc/snort/snort.lua
`


## In case of one set of rules, no need to add it in "snort.lua" file

`
snort -c $my_path/etc/snort/snort.lua -R icmp.rules -Q --daq afpacket -i "ens34:ens35
`
## You can also add it if you want

`
ips = { include = 'malware.rules' }
`


## In case of multiple rules required

Add the followings to the snort.lua file

`
ips = 
{
    rules = [[
        include /path/to/rulesfile1.rules
        include /path/to/rulesfile2.rules
        …
    ]]
}
`


## Alerts


`
snort -c $my_path/etc/snort/snort.lua -R icmp.rules -Q --daq afpacket -i "ens34:ens35" -A alert_talos
`

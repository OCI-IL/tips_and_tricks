# Instance Internal FW - OCI Linux Open Ports

OCI Linux images come with the FW on by default.
You must open the ports you want to use.

for example - opening port 8080

## Oracle Linux

```$ sudo firewall-cmd --zone=public --permanent --add-port=8080/tcp```

```$ sudo firewall-cmd --reload```


## Ubuntu Linux
The Ubuntu firewall is disabled by default.
However, you need to update your iptables configuration to allow HTTP traffic.
To update iptables, run the following commands:

```$ sudo iptables -I INPUT 6 -m state --state NEW -p tcp --dport 8080 -j ACCEPT```

```$ sudo netfilter-persistent save```

### Further Reading

https://blogs.oracle.com/developers/post/enabling-network-traffic-to-ubuntu-images-in-oracle-cloud-infrastructure
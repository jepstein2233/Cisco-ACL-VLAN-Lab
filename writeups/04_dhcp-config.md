I configured DHCP pools on the router so that devices in each VLAN would receive IP addresses automatically. Each pool was assigned the correct subnet and default gateway. I also excluded the gateway address to prevent them from being assigned to clients.
Both PCs successful received IP addresses from the router’s DHCP service. I verified connectivity to the default gateway on each VLAN and performed inter-VLAN ping tests. Successful responses confirmed that inter-VLAN routing was functioning correctly.


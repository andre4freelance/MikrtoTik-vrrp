# VRRP on MikroTik for DHCP Server Redundancy

This repository provides configuration examples for **MikroTik VRRP (Virtual Router Redundancy Protocol)** to achieve DHCP Server high availability.  
The scenario simulates an office LAN network where **RO-MAIN** acts as the primary router with VRRP priority 254, and **RO-BACKUP** serves as the standby router with VRRP priority 10. Both routers share a virtual IP address (192.168.1.1) that clients use as their default gateway and DHCP source.

This solution is highly suitable for office environments that require **high network availability** and **minimal downtime**.

---

## Topology

![Project topology](images/topology.png)

---

## Testing

### Normal Condition
When both links are active, the **RO-MAIN** router handles all DHCP and gateway traffic for clients on VLAN 10.

![Normal link state](images/link-normal.png)

### Failover Condition
When the distribution link on the primary router (RO-MAIN) is disconnected, the **RO-BACKUP** router takes over. Client devices experience only a **brief RTO (Request Timeout)**, demonstrating optimal network continuity.

![RO-MAIN link down - failover in action](images/link-from-RO-MAIN-down.png)

---

## Devices

- **Router**: MikroTik RouterOS 7.14.3
- **Switch**: Cisco NX-OS
---

## Links

Origin:  
<https://github.com/andre4freelance/MikroTik-vrrp>

LinkedIn post:  
<https://www.linkedin.com/posts/link-andre-bastian_mikrotik-cisco-lan-activity-7209202751929483265-GTMu?utm_source=share&utm_medium=member_desktop&rcm=ACoAAD73JlUBty-p-mBfMEW0-O4j0sv-e_PRQvc>

Facebook post:
<https://www.facebook.com/share/p/15SR1AjWQVx/>
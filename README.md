# Week 6 - VXLAN Overlay Data Centre Lab

Sim Jing Jia (4919)

## Design

The data centre consists of three hypervisors (hv1, hv2 and hv3) and three tenants: amber (VNI 110), teal (VNI 220) and violet (VNI 330). Amber and teal use overlapping IP address space, while VXLAN VNIs provide tenant isolation.

## Tenant Isolation

VXLAN separates tenant traffic using different VNIs. Tests confirmed that amber and teal could independently communicate with VMs using the same IP address without receiving each other's traffic.

## Flooding and MAC Learning

Broadcast traffic was replicated to the other hypervisors in the same VXLAN segment. The VTEPs learned remote MAC addresses from the received traffic. EVPN can replace much of this flood-and-learn process by distributing MAC and IP reachability information through a control plane.

## MTU

Two solutions were tested. Fix A used a tenant MTU of 1450 with an underlay MTU of 1500. Fix B used a tenant MTU of 1500 with an underlay MTU of 9000. Both were tested using ping and iperf3.

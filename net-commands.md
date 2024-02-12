
> ip route show
default via 172.30.214.190 dev wlx54b80a631667 proto dhcp metric 600
169.254.0.0/16 dev wlx54b80a631667 scope link metric 1000
172.30.214.160/27 dev wlx54b80a631667 proto kernel scope link src 172.30.214.167 metric 600

sudo lshw -class network
  *-network
       description: Ethernet interface
       product: RTL8111/8168/8411 PCI Express Gigabit Ethernet Controller
       vendor: Realtek Semiconductor Co., Ltd.
       physical id: 0
       bus info: pci@0000:02:00.0
       logical name: enp2s0
       version: 15
       serial: d4:5d:64:43:d7:25
       capacity: 1Gbit/s
       width: 64 bits
       clock: 33MHz
       capabilities: pm msi pciexpress msix bus_master cap_list ethernet physical tp mii 10bt 10bt-fd 100bt 100bt-fd 1000bt-fd autonegotiation
       configuration: autonegotiation=on broadcast=yes driver=r8169 driverversion=6.2.0-39-generic firmware=rtl8168h-2_0.0.2 02/26/15 latency=0 link=no multicast=yes port=twisted pair
       resources: irq:19 ioport:e000(size=256) memory:f7004000-f7004fff memory:f7000000-f7003fff
  *-network
       description: Wireless interface
       physical id: 7
       bus info: usb@1:4
       logical name: wlx54b80a631667
       serial: 54:b8:0a:63:16:67
       capabilities: ethernet physical wireless
       configuration: broadcast=yes driver=rtl8812au driverversion=v5.13.6-15-gc40b977e2.20210629 firmware=52.14 ip=172.30.214.167 link=yes multicast=yes wireless=IEEE 802.11AC

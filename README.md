# kiss-waydroid
kiss repo to package waydroid

# Install Repo
this repo need dependencies from kiss-community repo to build.

https://github.com/kiss-community/community

# DKMS modules
Use anbox-modules repo and dkms to install the modules necessary

https://github.com/choff/anbox-modules


# Kernel options you need to enable to netfilter

CONFIG_BRIDGE\
CONFIG_BRIDGE_IGMP_SNOPING\
CONFIG_BRIDGE_VLAN_FILTERING\
CONFIG_BRIDGE_NETFILTER\
CONFIG_NETFILTER_FAMILY_BRIDGE\
CONFIG_NF_TABLES_BRIDGE\
CONFIG_NFT_BRIDGE_META\
CONFIG_NFT_BRIDGE_REJECT\
CONFIG_NF_CONNTRACK_BRIDGE\
CONFIG_NETFILTER_XT_TARGET_CHECKSUM

# Kernel options you need to enable to cgroups
```
General setup  --->
  CPU/Task time and stats accounting  ---> 
  [*]   Pressure stall information tracking
  [*]     Require boot parameter to enable pressure stall information tracking
 [*] Control Group support  --->
  [*]   Freezer cgroup subsystem 
  [*]   Device controller for cgroups
  [*]   Cpuset support
  [*]     Include legacy /proc/<pid>/cpuset file
  [*]   Simple CPU accounting cgroup subsystem 
  [*]   Resource counters 
  [*]     Memory Resource Controller for Control Groups
  [*]       Memory Resource Controller Swap Extension
  [*]         Memory Resource Controller Swap Extension enabled by default
  [*]   Enable perf_event per-cpu per-container group (cgroup) monitoring
  [*]   Group CPU scheduler  --->
   [*]   Group scheduling for SCHED_OTHER 
   [*]   Group scheduling for SCHED_RR/FIFO   
  <*>   Block IO controller
 -*- Namespaces support
  [*]   UTS namespace
  [*]   IPC namespace
  [*]   User namespace (EXPERIMENTAL)
  [*]   PID Namespaces
  [*]   Network namespace 
 [*] Configure standard kernel features (expert users)  
[*] Networking support  --->
      Networking options  --->
      <M> 802.1d Ethernet Bridging
      <M> 802.1Q VLAN Support 
Device Drivers  --->
      [*] Network device support  --->
       <M>   MAC-VLAN support (EXPERIMENTAL)
       <M>   Virtual ethernet pair device
      Character devices  --->
       -*- Unix98 PTY support
       [*]   Support multiple instances of devpts
```

# Active PSI=1 in grub

insert psi=1 in this line

`GRUB_CMDLINE_LINUX_DEFAULT=''`

and update grub config

`doas grub-mkconfig -o /boot/grub/grub.cfg`

# Mount cgroups after start waydroid container

`doas mount -t cgroup2 none /sys/fs/cgroup/`

# kiss-waydroid
kiss repo to package waydroid

# Install
this repo need dependencies from kiss-community repo to build.

https://github.com/kiss-community/community

# Kernel options you need to enable to netfilter

CONFIG_BRIDGE
CONFIG_BRIDGE_IGMP_SNOPING
CONFIG_BRIDGE_VLAN_FILTERING
CONFIG_BRIDGE_NETFILTER
CONFIG_NETFILTER_FAMILY_BRIDGE
CONFIG_NF_TABLES_BRIDGE
CONFIG_NFT_BRIDGE_META
CONFIG_NFT_BRIDGE_REJECT
CONFIG_NF_CONNTRACK_BRIDGE
CONFIG_NETFILTER_XT_TARGET_CHECKSUM

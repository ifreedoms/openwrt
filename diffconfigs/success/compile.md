## 1. compilation background
compiling date:     20231021  
compiling system:   ubuntu-22.04.1  
compiling version:  openwrt-23.05  
compiling user:     homenode  

## 2. env prepare
sudo apt update  
sudo apt install build-essential clang flex bison g++ gawk gcc-multilib g++-multilib gettext git libncurses-dev libssl-dev python3-distutils rsync unzip zlib1g-dev file wget qemu-utils  

## 3. source code
git clone -b openwrt-23.05 https://github.com/ifreedoms/openwrt.git

## 4. update the feeds  
./scripts/feeds update -a  
./scripts/feeds install -a  // repeat execute for no warning  

## 5. make menuconfig
**Target System** (x86)  
**Subtarget** (Generic)  
**Target Profile** (Generic x86)  
**Target Images**  
&#8195;&#8195;tar.gz (cancel)  
&#8195;&#8195;Build VMware image files (VMDK) (NEW)  
**Base system**  
&#8195;&#8195;dnsmasq (cancel)  
&#8195;&#8195;dnsmasq-full  
&#8195;&#8195;&#8195;&#8195;Build with IPset support. # for support domain forward  
&#8195;&#8195;firewall4  
&#8195;&#8195;opkg  
**Administration**  
&#8195;&#8195;atop  
&#8195;&#8195;btop  
&#8195;&#8195;htop  
&#8195;&#8195;netdata  
&#8195;&#8195;sudo  
**Boot Loaders**  --->          
**Development**  --->  
&#8195;&#8195;ar  
&#8195;&#8195;autoconf  
&#8195;&#8195;automake  
&#8195;&#8195;diffutils  
&#8195;&#8195;gcc  
&#8195;&#8195;gdb  
&#8195;&#8195;make  
&#8195;&#8195;trace-cmd  
**Extra packages**  --->  
**Firmware**  --->  
**Fonts**  --->  
**Kernel modules**  --->  
&#8195;&#8195;Network Support  
&#8195;&#8195;&#8195;&#8195;kmod-tun  
**Languages**  --->  
**Libraries**  --->  
**LuCI**  --->  
&#8195;&#8195;Collections  
&#8195;&#8195;&#8195;&#8195;luci  
&#8195;&#8195;Modules  --->  
&#8195;&#8195;&#8195;&#8195;Translations --->  
&#8195;&#8195;&#8195;&#8195;&#8195;&#8195;Chinese Simplified (zh_Hans)  
&#8195;&#8195;&#8195;&#8195;luci-compat  (better install)  
&#8195;&#8195;&#8195;&#8195;luci-mod-dashboard  
&#8195;&#8195;Applications  
&#8195;&#8195;&#8195;&#8195;luci-app-ddns  
&#8195;&#8195;&#8195;&#8195;luci-app-firewall  
&#8195;&#8195;&#8195;&#8195;luci-app-netdata  
&#8195;&#8195;&#8195;&#8195;luci-app-openclash  
&#8195;&#8195;&#8195;&#8195;luci-app-opkg  
&#8195;&#8195;&#8195;&#8195;luci-app-qos  
&#8195;&#8195;&#8195;&#8195;luci-app-samba4  
&#8195;&#8195;&#8195;&#8195;luci-app-ssr-plus  
&#8195;&#8195;&#8195;&#8195;&#8195;Shadowsocks Client Selection (Shadowsocks-rust)  
&#8195;&#8195;&#8195;&#8195;&#8195;Shadowsocks Server Selection (Shadowsocks-libev)  
&#8195;&#8195;&#8195;&#8195;&#8195;V2ray-core Selection (Xray-core)  
&#8195;&#8195;&#8195;&#8195;&#8195;Include ChinaDNS-NG  
&#8195;&#8195;&#8195;&#8195;&#8195;Include MosDNS  
&#8195;&#8195;&#8195;&#8195;&#8195;Include Hysteria  
&#8195;&#8195;&#8195;&#8195;&#8195;Include Tuic-Client  
&#8195;&#8195;&#8195;&#8195;&#8195;Include Shadow-TLS  
&#8195;&#8195;&#8195;&#8195;&#8195;Include IPT2Socks  
&#8195;&#8195;&#8195;&#8195;&#8195;Include Kcptun  
&#8195;&#8195;&#8195;&#8195;&#8195;Include NaiveProxy  
&#8195;&#8195;&#8195;&#8195;&#8195;Include Redsocks2  
&#8195;&#8195;&#8195;&#8195;&#8195;Include Shadowsocks Simple Obfs Plugin  
&#8195;&#8195;&#8195;&#8195;&#8195;Include Shadowsocks V2ray Plugin  
&#8195;&#8195;&#8195;&#8195;&#8195;Include ShadowsocksR Libev Client  
&#8195;&#8195;&#8195;&#8195;&#8195;Include ShadowsocksR Libev Server  
&#8195;&#8195;&#8195;&#8195;&#8195;Include Trojan  
&#8195;&#8195;&#8195;&#8195;luci-app-ttyd  
&#8195;&#8195;Themes  
&#8195;&#8195;&#8195;&#8195;luci-theme-bootstrap  
&#8195;&#8195;&#8195;&#8195;luci-theme-material  
&#8195;&#8195;&#8195;&#8195;luci-theme-openwrt  
&#8195;&#8195;&#8195;&#8195;luci-theme-openwrt-2020  
&#8195;&#8195;Protocols  --  
&#8195;&#8195;Libraries  --  
**Mail**  --->  
**Multimedia**  --->  
**Network**  
&#8195;&#8195;BitTorrent  --->  
&#8195;&#8195;Download Manager  --->  
&#8195;&#8195;iperf3  
**Sound**  --->  
**Utilities**  --->  
&#8195;&#8195;Compression  
&#8195;&#8195;&#8195;&#8195;gzip  
&#8195;&#8195;&#8195;&#8195;unzip  
&#8195;&#8195;&#8195;&#8195;unrar  
&#8195;&#8195;Disc  
&#8195;&#8195;&#8195;&#8195;fdisk  
&#8195;&#8195;&#8195;&#8195;lsblk  
&#8195;&#8195;ilesystem  
&#8195;&#8195;&#8195;&#8195;ntfs-3g  
&#8195;&#8195;&#8195;&#8195;whereis  
&#8195;&#8195;&#8195;&#8195;which  
**Xorg** --->  

## 6. compile  
make -j1 download V=s  
make -j1 V=s  
# cri-o

VERSION=1.24
sudo curl -L -o /etc/yum.repos.d/devel:kubic:libcontainers:stable.repo https://download.opensuse.org/repositories/devel:kubic:libcontainers:stable/CentOS_7/devel:kubic:libcontainers:stable.repo

sudo curl -L -o /etc/yum.repos.d/devel:kubic:libcontainers:stable:cri-o:${VERSION}.repo https://download.opensuse.org/repositories/devel:kubic:libcontainers:stable:cri-o:${VERSION}/CentOS_7/devel:kubic:libcontainers:stable:cri-o:${VERSION}.repo

yum install cri-o cri-tools

systemctl enable crio
systemctl start crio

if worker node failes to join then try
echo 1 > /proc/sys/net/ipv4/ip_forward
modprobe br_netfilter
echo 1 > /proc/sys/net/bridge/bridge-nf-call-iptables




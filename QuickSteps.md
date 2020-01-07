RHEL 7.x/CentOS 7.x OS/ VM 
Configure Networking
Disable Kdump
Set-Hostname 
Disable NetworkManager
# systemctl stop NetworkManager
# systemctl disable NetworkManager
# systemctl mask NetworkManager
# yum -y remove NetworkManager
# systemctl enable network
# systemctl restart network
set Yum Repos
$ sudo yum update -y
$ sudo yum install -y centos-release-openstack-stein
$ sudo yum update -y
$ sudo yum install -y openstack-packstack
$ sudo packstack --allinone
Disable SELinux in /etc/selinux/config
Set your hostname and IP in /etc/hosts
Update packages
# yum update -y
# reboot
yum install -y openstack-packstack
packstack --gen-answerfile=/
root/packstack_answerfile_piysuh.yaml
vi /root/packstack_answerfile_piyush.yaml
```
update below parameter for installation 
CONFIG_HEAT_INSTALL=y
CONFIG_KEYSTONE_ADMIN_PW=admin
Here admin is the password for admin tenant.
CONFIG_PROVISION_DEMO=n
CONFIG_NTP_SERVERS=192.X.X.X
Update the ntp server IP. In the above mentioned IP is a
example.
CONFIG_COMPUTE_HOSTS=10.X.X.X,10.X.X.X,10.X.X.X
Add all compute hosts IPs with comma separated. In the
above 10.X.X.X will be all-in-one and other hosts will
be only compute servers
CONFIG_NEUTRON_OVS_BRIDGE_MAPPINGS=physnetone:br-ex
Here physnet is first physical interface as we have
consider eth0. If we consider second interface eth1 then
it should be “physnettwo:br-ex”
CONFIG_NEUTRON_OVS_BRIDGE_IFACES=br-ex:eth0
```
To run installation. 

packstack --answerfile=/root/packstack_answerfile_piyush.yaml

vi packstack_final_output.txt
**** Installation completed successfully ******

Here you are 

loging GUI 
http://10.X.X.X/dashboard

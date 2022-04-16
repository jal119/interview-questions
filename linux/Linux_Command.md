# LVM
===
## Procedures
----------
pvcreate /dev/sda ->make /dev/sda a PV

pvremove /dev/sda ->remove /dev/sda from lvm control

pvmove /dev/sda /dev/sdb ->will move active PEs in /dev/sda to /dev/sdb (check using PVS to see if /dev/sdb has enough free space to accomodate the PE from /dev/asa)

pvmove /dev/sda ->active PEs in /dev/sda will be moved to any free disk in the VG

vgcreate testvg /dev/sda ->create a vg by name test vg and add /dev/sda to it

vgextend testvg /dev/sdb ->make the vg bigger by adding anothet pv

vgreduce testvg /dev/sda ->release /dev/sda from the vg #before doing this move active PEs from the PV using pvmove command

vgremove testvg ->will remove the VG #make sure all volumes are removed before removing VG

lvcreate -L 100G -n testlv testvg ->to create a lv called testlv of 100G

mkfs.ext4 /dev/testvg/testlv ->create ext4 filesystem on testlv

## LVextension
-----------
lvextend -L +10G /dev/testvg/testlv -> make sure you have suffcient free space in the vg before extending- use vgs

lvextend -L 110G /dev/testvg/testlv ->you can also use absolute size

lvextend -L +100%FREE /dev/testvg/testlv ->extend the lv to use all free space in the VG

resize2fs /dev/testvg/testlv ->resizes the filesystem

lvextend -r -L +10G /dev/testvg/testlv ->will extend the lv and resize filesystem in one shot

## lvreduction
-----------
unmount the filesystem (check processes accesing the mount point using *fuser -vm /testmount* kill processes using *fuser -k /testmount*)

e2fsck -f /dev/testvg/testlv ->fsck the filesystem 

resize2fs /dev/testvg/testlv 90G ->reduces a 100G filesystem to 90G filesystem 

lvreduce -L -10G /dev/testvg/testlv ->reduce the LV by 10G - this space will now add up to the free space in the VG

lvreduce -L 90G /dev/testvg/testlv ->specifying the absolute size

## POINTS
------

never run fsck on a mounted filesystem #if required to run fsck on root fs take server to rescue mode

lvreduce should be done only after the filesystem has been resized using resize2fs

pvscan-scans for new PVs and display detailed info on each PV

pvs- lists current PVS along with space information

vgscan- scans for new VG and display detailed info on each VG

vgs- lists current VGs along with space information

lvscan -scans for new LV and display detailed info on each LV

lvs -lists current LVs along with space information

vgchange -an testvg ->deactivate all LVs in testvg

vgchange -ay testvg ->activate all LVs in testvg

vgchange -ay ->activate all LVs in all VGs

vgchange -an ->deactivate all LVs in all VGS -will work only in the volumes are unmounted

lvm config files are available in /etc/lvm/lvm.conf

backup of each vg is in /etc/lvm/backup and /etc/lvm/archive

vgcfgbackup - to create a new vg backup

vgcfgrestore - to restore a VG config from backup


# Troubleshooting
---------------
for duplicate PV issue set correct filter in /etc/lv/lvm.conf (a-allow a device,r-remove a device)

if a pv is misisng check if the disk is actually available, if available recreate the PV only to modify the missing PVID - if the disk itself is not available check for issues with multipath. engage san team  if required

if someone removed a LV or resized lv wrongs without resizing the filesystem do vgcfgrestore

if a volume is not mounting first try to mount manually using mount command (mount -t ext4 /dev/testvg/testlv /testmount). If it reports filesystem inconsistency run fsck. If it reports the LV is missing then check if all the volumes in the VG are activated (lvs will show) if not activate.



# Networking
==========

Procedures
----------

edit /etc/sysconfig/network-scripts/ifcfg-eth0

to assign IP, gateway. after assigning restart network service *chkconfig network on* *service network restart*

Bonding
-------

copy contents of /etc/sysconfig/network-scripts/ifcfg-eth0 to /etc/sysconfig/network-scripts/ifcfg-bond0

assign IP address to bond0 file

remove IP address assignemts from eth0 and eth1

set MASTER=bond0 and SLAVE=yes on eth0 and eth1 files

edit /etc/modprobe.conf and specify the alias, bonding mode, and monitoring

## bonding mode
------------
mode0 -round robin

mode1 -active failover

mode5 -transmit load balancing (only outgoing traffic is load balanced)

mode6 -adaptive load balancing (both outgoing/incoming traffic is load balanced)


load the bonding driver by running *modprobe bonding*

restart network *service network restart*

to create virtual NIC copy the config file and assign new ip- for eg. copy bond0 to bond0:0 and assign new IP to bond0:0

bond0 will have no mac address. the mac address of bond0 will be the mac address of the currently active slave

to check currently active slave and bonding status *cat /proc/net/bonding/bond0*

to switch the default slave from eth0 to eth1 *ifenslave -c bond0 eth1*

to remove eth1 from bond0 *ifenslave -d bondo eth1*

to add eth2 to bond0 *ifenslave bond0 eth2*

all changes made by ifenslave are temporary and NOT persistent accross reboots

to check links status,speed,duplex,autonegotiation status *ethtool eth0*

to change link speed or duplex or autoneg *ethtool -s eth0 speed 1000/100 duplex full/half autoneg on/off*

to check network status of active interfaces *ifconfig*

to check network status of all interfaces *ifconfig -a*


# Network Troubleshoooting
------------------------

if there are packet drops, check for link flapping in /var/log/messages. if link flaps ask for cable check. if there are no link flaps increase NIC ring buffer 


# Multipathing
============

Procedures
----------

DM-Multipath
------------

multipath -ll -> list multipath status
multipath -f mpatha ->remove multipath device mpatha
multipath -F ->remove all multipath devices

the name pattern, array support, devices to be blacklisted from multipath all has to be configured /etc/multipath/multipath.conf

EMC powerpath
-------------

powermt display ->display multipath device overview

powermt display dev=all ->display info on each device in detail

powermt check -> check for dead paths

powermt config ->rescan for new devices and create multipath device

powermt restore -> restore path information from the db

powermt display options ->display which all array class is being managed

powermt display paths ->display path information to each san array

powermt manage class=Hitachi ->manage hitachi array from powerpath

powermt unmanage class=Hitachi -> unmanage hitachi array from powerpath

powermt delete dev=emcpowera ->delete multipath device emcpowera (make sure the device is removed from LVM before deleting it)

emcpadm export_mappings -f /tmp/map ->export current powerpath mappings to a file

emcpadm import_mappings -f /tmp/map ->import an exported mapping from a file


Troubleshooting
---------------

Filesystem
----------

for filesystem inconsistency issues, unmount the filesystem and run fsck. 

dumpe2fs /dev/testvg/testlv ->shows the properties of the filesystem 
tune2fs  ->used to change the filesystem parameters
blkid -> lists the uuid of the filesystem


setting up nfs server

automount
---------

setup the maps in /etc/auto.master and run *servive autofs restart*

clearing stale mount -> will happen when the NFS server stops responding when the client is still using. to fix do lazy unmount *umount -l /testmount*


patching
========

enable the correct repository
backup important files
check for free space in /boot
run *yum update*

if something less critical fails, use *yum update --skip-broken*
to exclude a package *yum update --exclude-list=testpkg*
if some dependency does not resolve, resolve the dependency manually by installing the package using rpm command, then do normal patching

if the initrd is not create properly after patching or if you want to recreate the initrd

RHEL5 - mkinitrd -f /boot/initrd-<version> <version>
RHEL6 - dracut -f /boot/initramfs-<version> <version>

Kernel RPMs should be only installed and not updated
after patching reboot the server


ulimits
=======

login as user and run *ulimit -a* to check for user ulimits

soft limit- the limit which is applied by default
hardlimit- the limit upto which the user can increase his limit by himself after hitting the soft limit

nproc - no of processes (including threads/lwp) for a user

memlock - amount of memory in KB each address can lock into his address space- this is not locking but whenever there is a demand the memory availability is guranteed

nofile - no of files each process can open

cat /proc/sys/kernel/pid_max ->max no of PIDs that can be assigned the over all no of processes is that value -400. the 1st 400 PIDs are reserved for kernel

cat /etc/security/limits.conf ->file where limits are set

errors
------
too many open files- nofile limit has breached
resource temporarily unavailable- either nproc or max_pid has breached

to check no of processes opened by a user *ps -eLf |grep -c ^testuser* -(L-includes LWPs)

to check no of processes opened at system level run *sar -q 2 10* (check plist size field)



NTP
===

service ntp restart
service ntpclient restart
ntpq -p

scanning asci bus for new luns
------------------------------

echo "1" >/sys/class/fc_host/host<N>/issue_lip ->scans the FC bus
echo "- - -" > /sys/class/scsi_host/host<n>/rescan #where "- - -" represents Host Bus Target

Deleting disks/ luns 
--------------------

remove the disk from LVM (see pvremove steps above). 
remove the multipath disk (steps above)
remove the individual disk *echo 1 >/sys/block/sda/device/delete

HP Commands
============

hpasmcli -s "show dimm" -> to check dimm status
hpasmcli -s "show ht" -> to check if ht is enables or not

hpacucli/hpssacli ctrl all show config ->to check raid disk status
hpacucli/hpssacli ctrl all show detail ->to display detailed status of the controller

hplog -v -> to see IML messages

Google
======

user creation/removal

umask

uid gid

fstab syntax

kdump

dmidecode

Troubleshooting
===============

perfomance
----------

check load average-it should be relevant to the number of CPUs 

if load is high check where the CPU time is getting lapsed. if it is in the user space check the hogging process from *top* and report to process owner. If the lapsing is in i/o wait check for processes in "D" state. if the process in D state is swap process, then check for the process that is thrashing memory. check this in top "RES" field. if it is some other process inform the process owner. Also, check *iostat -x*. If the svc time field is more than 300ms and %util files is 100%, then engage SAN team to check if the fabric is staurated or if there are issues at SAN level.

If non of the above problem exists, check the network for packet drop using *ifconfig* or *netstat -i*. if there is packet loss engage network team.

if no  issues above exist, then probably the issue is with the enduser level.


boot issues
-----------

check if you are able to boot in single user mode. If yes go and fix the issue there. If not boot in rescue mode and fix

if the server does not boot after patching boot the server is old kernel and troubleshoot from there.

if grub doesn't load at all, boot to rescue mode and resinatall grub.


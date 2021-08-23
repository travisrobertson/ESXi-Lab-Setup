# Photon Guest VM
Preparing Photon Guest VM

Download OVA for arm64
https://github.com/vmware/photon/wiki/Downloading-Photon-OS

Deploy photon1 VM using OVA.
change default login root:changeme

Step 1 – Apply the latest updates
tdnf -y update

Step 2 – Reboot the system to ensure all updates have been applied (you may want to run the above command one more time to ensure there aren’t other updates)

Step 3 – Install VMware Tools
tdnf -y install open-vm-tools

Step 4 – Enable and start VMware Tools service
systemctl enable vmtoolsd.service
systemctl start vmtoolsd.service

open-vm-tools: unknown ioctl 1976 errors
/etc/modprobe.d/blacklist.conf
blacklist vsock_loopback
blacklist vmw_vsock_virtio_transport_common
install vsock_loopback /usr/bin/true
install vmw_vsock_virtio_transport_common /usr/bin/true


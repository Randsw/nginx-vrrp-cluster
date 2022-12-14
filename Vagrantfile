# -*- mode: ruby -*-
# vi: set ft=ruby :
$lb_instance_num = 3
$vm_ip_addr_start = 200
#$bridge = "usb0" #name of network interface with internet connection 
$bridge = "wlp2s0" #name of network interface with internet connection 
$vm_cidr = "192.168.0" # virtual machines CIDR
Vagrant.configure("2") do |config|
    config.vm.box = "generic/ubuntu2004"
    config.vm.box_check_update = false
    (1..$lb_instance_num).each do |i|
        config.vm.define "vrrp-#{i}" do |node|
            node.vm.network "public_network", ip: "#{$vm_cidr}.#{$vm_ip_addr_start+i}", bridge: $bridge
            node.vm.hostname = "vrrp-#{i}"
            node.vm.provider "virtualbox" do |vb|
                vb.gui = false
                vb.memory = "1024"
                vb.cpus=1
            end
        end
    end
end
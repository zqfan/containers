# install

~~~
cd ~
wget https://github.com/kubernetes/kubernetes/releases/download/v1.4.0/kubernetes.tar.gz
tar xzvf kubernetes.tar.gz
cd kubernetes
vagrant plugin install vagrant-proxyconf
vagrant plugin install vagrant-libvirt --plugin-version "<0.0.36"
~~~

# problems

## undefined method `dhcp_leases'

~~~
==> master: Waiting for domain to get an IP address...
==> master: Removing domain...
==> master: Running cleanup tasks for 'shell' provisioner...
/home/zqfan/.vagrant.d/gems/gems/fog-libvirt-0.3.0/lib/fog/libvirt/requests/compute/dhcp_leases.rb:8:in `dhcp_leases': undefined method `dhcp_leases' for #<Libvirt::Network:0x000000020458d8> (NoMethodError)
~~~

refs:

* https://github.com/vagrant-libvirt/vagrant-libvirt/issues/669
  * renatomefi: You could try to downgrade your vagrant-libvirt plugin to 0.0.35 and see how it works for you!
  * infernix: Your libvirt version 1.2.2-0ubuntu13.1.17 does not support the virNetworkGetDHCPLeases call that fog-libvirt depends on for its dhcp_leases call. fog/fog-libvirt#8 is related to this.
* https://github.com/fog/fog-libvirt/issues/27
  * infernix: virNetworkGetDHCPLeases isn't supported in libvirt < 1.2.6 so on distros carrying older libvirt, everything compiles but then using this call fails with above error.

solution:

~~~
vagrant plugin uninstall vagrant-libvirt
vagrant plugin install vagrant-libvrit --plugin-version "<0.0.36"
~~~

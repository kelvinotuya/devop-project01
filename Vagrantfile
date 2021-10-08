Vagrant.configure("2") do |config|
 # config.hostmanager.enabled = true 
 # config.hostmanager.manage_host = true


  
### tomcat vm ###
   config.vm.define "app01" do |app01|
    app01.vm.box = "ubuntu/xenial64"
    app01.vm.hostname = "app01"
      # Grab the name of the default interface
    $default_network_interface = `ip route | awk '/^default/ {printf "%s", $5; exit 0}'`
    config.vm.network "public_network", bridge: "#$default_network_interface",
    use_dhcp_assigned_default_route: true
	app01.vm.provider "virtualbox" do |vb|
     vb.memory = "1024"
	 end
   end
  
end

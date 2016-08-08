VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.boot_timeout = 500
  config.vm.box = "centos7"
  config.vm.box_url = "https://googledrive.com/host/0B2JacpSnObRwaExDNUVOYUcyYWM/centos7.box"
  #config.vm.box = "centos"
  #config.vm.box_url = "https://googledrive.com/host/0B2JacpSnObRwOFVnbFJkSDNvaEE"
  config.ssh.insert_key = false 


  config.vm.define :sp do | sp |
    sp.vm.hostname = "sp.sheepcloud.org"
    sp.vm.network :private_network, ip: "192.168.12.20"
    sp.vm.network :forwarded_port, id: "ssh", guest: 22, host: 2212
  end

  config.vm.define :idp1 do | idp1 |
     idp1.vm.hostname = "idp1.sheepcloud.org"
     idp1.vm.network :private_network, ip: "192.168.12.11"
     idp1.vm.network :forwarded_port, id: "ssh", guest: 22, host: 2210
  end

  config.vm.define :idp2 do | idp2 |
     idp2.vm.hostname = "idp2.sheepcloud.org"
     idp2.vm.network :private_network, ip: "192.168.12.12"
     idp2.vm.network :forwarded_port, id: "ssh", guest: 22, host: 2211
  end

  config.vm.provision "ansible" do |ansible|
    #ansible.verbose = "vvv"
    ansible.ask_sudo_pass = false 
    ansible.playbook = "site.yml"
    ansible.limit = "all" 
      ansible.groups = {
      "idp" => ["idp1","idp2"],
      "sp"=> ["sp"]
    } 
  end
end

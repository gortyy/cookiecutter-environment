VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.provider "virtualbox" do |vb|
    vb.cpus = 2
    vb.memory = 8192
  end

  config.vm.define "app" do |dev|
    dev.vm.box = "bento/ubuntu-18.04"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.galaxy_role_file = "ansible-requirements.yml"
    ansible.galaxy_command = "ansible-galaxy install --role-file=%{role_file}"
    ansible.playbook = "playbook.yml"
  end
end

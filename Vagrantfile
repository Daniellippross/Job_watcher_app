ENV["GEM_PATH"] = nil
ENV["GEM_HOME"] = nil
required_plugins = %w( vagrant-hostsupdater vagrant-berkshelf )
required_plugins.each do |plugin|
  exec "vagrant plugin install #{plugin};vagrant #{ARGV.join(" ")}" unless Vagrant.has_plugin? plugin || ARGV[0] == 'plugin'
end

Vagrant.configure("2") do |config|
  config.omnibus.chef_version = '14.12.9'
  config.vm.box = "ubuntu/xenial64"
  config.vm.define "app" do |app|
    app.vm.box = "ubuntu/xenial64"
    app.vm.network "private_network", ip: "192.168.10.100"
    app.hostsupdater.aliases = ["development.local"]
    app.vm.synced_folder "Job_watcher", "/home/ubuntu/Job_watcher"
   #app.vm.provision "shell", path: "Environment/provision.sh"
   app.vm.provision "chef_solo" do |chef|
      chef.cookbooks_path = ["C:/Users/It_Jobs_Watch_Data_Package"]
      chef.add_recipe "Job_watcher_chef::default"
    end
  end
end

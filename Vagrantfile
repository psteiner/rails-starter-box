Vagrant::Config.run do |config|
  config.vm.customize ["modifyvm", :id, "--name", "test-box", "--memory", "512"]
  config.vm.box       = 'precise64'
  config.vm.box_url   = 'http://files.vagrantup.com/precise64.box'
  config.vm.host_name = 'test-box'

  config.vm.forward_port 3000, 3000, :auto => true
  config.vm.share_folder "site", "site", "../site"

  config.vm.provision :puppet,
    :manifests_path => 'puppet/manifests',
    :module_path    => 'puppet/modules'
end

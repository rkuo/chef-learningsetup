Vagrant::Config.run do |config|

  # setup to create multiple vms here, use different vm.define block
  config.vm.define :web do |web_config|
    
    #web
    web_config.vm.box = "opscode-ubuntu-12.04"
    web_config.vm.network :hostonly, "33.33.33.21"

    web_config.vm.provision :chef_client do |chef|
      # setup location of recipes and authentication keys
      chef.chef_server_url        = "https://api.opscode.com/organizations/villa"
      chef.validation_key_path    = "/Users/rkuo/Projects/chef-learningsetup/chef-repo/.chef/villa-validator.pem"
      chef.validation_client_name = "villa-validator"

      chef.provisioning_path      = "/etc/chef"

      chef.node_name              = "demo-12.04-webserver-01"

      # chef.add_recipe("apache2")
      
    end
  end
end

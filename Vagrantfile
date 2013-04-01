Vagrant::Config.run do |config|

  # setup to create multiple vms here, use different vm.define block

  #web
  config.vm.define :web do |web_config|  
    web_config.vm.box = "opscode-ubuntu-12.04"
    web_config.vm.network :hostonly, "33.33.33.21"
    web_config.vm.forward_port 80, 8080

    web_config.vm.provision :chef_client do |chef|
      # setup location of recipes and authentication keys
      chef.provisioning_path      = "/etc/chef"
      chef.chef_server_url        = "https://api.opscode.com/organizations/villa"
      chef.validation_key_path    = "/Users/rkuo/Projects/chef-learningsetup/chef-repo/.chef/villa-validator.pem"
      chef.validation_client_name = "villa-validator"

      chef.node_name              = "demo-12.04-webserver-01"

      # recipes, run list, role
      # chef.add_recipe("apt")
      chef.add_recipe("nginx")
      chef.add_recipe("mongodb")
      # chef.add_recipe("riak")
    end
  end
end

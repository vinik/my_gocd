# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
    config.vm.box = "vinik/ubuntu"

    config.berkshelf.berksfile_path = "chef/cookbooks/Berksfile"

    config.vm.define "server" do |server|
        # config.vm.network "forwarded_port", guest: 8080, host: 80

        server.vm.provision "chef_solo" do |chef|
            chef.cookbooks_path = ['chef/cookbooks']
            chef.add_recipe 'go_cd::server'
        end
    end

    # config.vm.define "agent" do |agent|
    #     # config.vm.network "forwarded_port", guest: 8080, host: 80
    #
    #     agent.vm.provision "chef_solo" do |chef|
    #         chef.cookbooks_path = ['chef/cookbooks']
    #         chef.add_recipe 'go_cd::agent'
    #     end
    # end



end

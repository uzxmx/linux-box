# -*- mode: ruby -*-
# vi: set ft=ruby :

kernel_version = '5.7.6'

Vagrant.configure('2') do |config|
  config.vm.box = 'uzxmx/mybox'

  config.ssh.forward_agent = true

  env = {
    KERNEL_VERSION: kernel_version,
    KERNEL_SRC_ROOT: "/home/vagrant/linux-#{kernel_version}"
  }

  File.open('.env', 'w') do |io|
    env.each do |k, v|
      io << "#{k}=#{v}\n"
    end
  end

  config.vm.provision :shell, privileged: false, env: env,
    path: './scripts/download_kernel'
end

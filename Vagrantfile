Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/jammy64"
  config.vm.define "haproxy" do |haproxy|
  end

  config.vm.provider "virtualbox" do |v|
    v.linked_clone = true
  end

  config.vm.provision "shell",
    :path => "vagrant_specs.sh",
    :upload_path => "/home/vagrant/specs",
    # change role name below
    :args => "--install ansible-haproxy"
end

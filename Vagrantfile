

require 'vagrant-aws'

=begin

class Hash
  def slice(*keep_keys)
    h = {}
    keep_keys.each { |key| h[key] = fetch(key) if has_key?(key) }
    h
  end unless Hash.method_defined?(:slice)
  def except(*less_keys)
    slice(*keys - less_keys)
  end unless Hash.method_defined?(:except)
end

=end

Vagrant.configure('2') do |config|

    # mention the box name if you have changed the name of the box
    config.vm.box = 'dummy'

    config.vm.provider 'aws' do |aws, override|

      # provide the access key id and secret access key for particular IAM or root
      aws.access_key_id = "xxxxxxxxxxxxxxx"
      aws.secret_access_key = "xxxxxxxxxxxxxxxxxxxxxxxxxxxx"
      
      #provide your keypair name which you use to ssh into VM's
      aws.keypair_name = 'cloud-keypair'

      # provide the instance type which you want to boot up
      aws.instance_type = 't2.micro'

      # procide the region of your VM 
      aws.region = 'us-east-2'

      # provide your ami id to launch the particualr VM
      aws.ami = 'ami-01e7ca2ef94a0ae86'

      # mention the particular Security Group 
      #remember for ssh you need to give permission..!!
      # So choose the group accordingly
      aws.security_groups = ['default']

      # provide the username of the VM
      override.ssh.username = 'ubuntu'

      # provide the path to your .pem or ssh key file with extension
      override.ssh.private_key_path = '~/.ssh/keypair.pem'
    end
end
# **Vagrant and AWS Web Services**

#### *This Repo is made so that VM's (on AWS) can be launched via vagrant*
#### *And we can use the command line utility provided by vagrant to do whatever needed*

***

> Here you will need to install plugins for AWS provider
> You can launch VM on any cloud but beforehand you need to install the plugin
***

> So following are the command to install aws-plugin
```
> $ vagrant plugin install vagrant-aws
```
***
> **If you are windows and facing some issues related to teh failure in installation you must install another plugin before this one**
```
> $ vagrant plugin install fog-aws
```
> **You also need to donwload the specific box provided by mitchellh or you can give the path to the box.**
**I have done it by the first way**
```
> $ vagrant box add dummy https://github.com/mitchellh/vagrant-aws/raw/master/dummy.box
```
**So on doing** 
```
> $ vagrant box list
```
**This box should be present there**
```
 ...
 
 dummy           (aws, 0)
 
 ...
```
***

**Now your plugins are installed :)**

- So there is a commented part in the code that starts with =begin and ends with =end
- If you are facing a error such as **Undefined HashMap method except** then uncomment that section of code
- And if not let the code remain commented :)

**After these installations, you need to run following command**
```
> $ vagrant up --provider=aws
```
**Now your VM is up..!!**

**You can ssh into it using following command**
```
> $ vagrant ssh
```
**Terms** : -

- **access_key_id** - The access key for accessing AWS
- **availability_zone** - The availability zone within the region to launch the instance. If nil, it will use the default set by Amazon.
- **aws_dir** - AWS config and credentials location. Defaults to $HOME/.aws/.
- **instance_type** - The type of instance, such as "m3.medium". The default value of this if not specified is "m3.medium". "m1.small" has been deprecated in "us-east-1" and "m3.medium" is the smallest instance type to support both paravirtualization and hvm AMIs
- **keypair_name** - The name of the keypair to use to bootstrap AMIs which support it.
- **region** - The region to start the instance in, such as "us-east-1"
- **secret_access_key** - The secret access key for accessing AWS
- **security_groups** - An array of security groups for the instance. If this instance will be launched in VPC, this must be a list of security group Name. For a nondefault VPC, you must use security group IDs instead (http://docs.aws.amazon.com/cli/latest/reference/ec2/run-instances.html).
- **tags** - A hash of tags to set on the machine.
- **terminate_on_shutdown** - Indicates whether an instance stops or terminates when you initiate shutdown from the instance.


You can read the docs of vagrant and AWS Web services
Few important links to perform the operations

[**Vagrant AWS**](https://github.com/mitchellh/vagrant-aws) <br/>
[**Vagrant Docs**](https://www.vagrantup.com/docs) <br/>
[**Hashmap Error**](https://github.com/mitchellh/vagrant-aws/issues/566)


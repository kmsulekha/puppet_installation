# Instructions

This repo includes steps to setup master and slave for puppet.


## Commands

|                         Master                            |                          Slave                                 |
|-----------------------------------------------------------|----------------------------------------------------------------|
| apt-get update                                            | apt-get update                                                 |
| wget https://apt.puppetlabs.com/puppet-release-bionic.deb | wget https://apt.puppetlabs.com/puppet-release-bionic.deb      |
| dpkg -i puppet-release-bionic.deb                         | dpkg -i puppet-release-bionic.deb                              |
| apt-get install puppetmaster -y                           | apt-get install puppet                                         |
| apt policy puppetmaster                                   | vim /etc/hosts                                                 |
| sudo systemctl status puppet-master.service               | -- <Master Ip> puppet                                          |
| vim /etc/default/puppet-master                            | systemctl start puppet                                         |
| --   JAVA_ARGS="-Xms512m -Xmx512m"                        | systemctl enable pupet                                         |
| systemctl restart puppet-master                           |                                                                |
| sudo ufw allow 8140/tcp                                   |                                                                |
| vim /etc/hosts                                            |                                                                |
| -- <Master Ip> puppet                                     |                                                                |
| puppet cert list                                          |                                                                |
| puppet cert sign --all                                    |                                                                |



## Providers
```hcl
provider "aws" {
  profile = "default"
  region = "ap-south-1"
}
```

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| ami\_id | n/a | `string` | <pre> "ami-0447a12f28fddb066" </pre> | yes |
| instance\_type | n/a | `string` | <pre> "t2.micro" </pre> | yes |
| availability\_zone | n/a | `string` | <pre> "ap-south-1b" </pre> | yes |
| vpc\_security\_group\_ids | n/a | `list` | <pre> ["default"] </pre> | yes |
| key\_name | n/a | `string` | <pre> "redhat-key" </pre> | yes |
| disk\_size | n/a | `number` | <pre> 1 </pre> | yes |
| disk\_name | n/a | `string` | <pre> "/dev/sdd" </pre> | yes |


<!--- END_TF_DOCS --->

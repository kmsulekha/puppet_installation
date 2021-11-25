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

## Create Menifest File
-- mkdir -p /etc/puppet/code/environments/production/menifests/
-- vim /etc/puppet/code/environments/production/menifests/site.pp

## Puppet Menifest File Code
```hcl
file {'/tmp/it_works.txt':
  ensure  => present,
  mode    => '0644',
  content => "it works on ${ipaddress_eth0}!\n",
}
```




<!--- END_TF_DOCS --->

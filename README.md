# SNORT_Automation
SNORT IDS Installation and configuration on Debian and CentOS-7 using Ansible 

SNORT is an open source IDS (Intrusion Detection Sysyem).

I creted a script which installs the essential packages for IDS to function, then install SNORT itself.
The code also contains creating essential folders and files.


## Howto (for Debain)

Update the machine

`
apt-get update -y
`

Install git

`
apt-get install git -y
`

Install Anisble

`
apt-get install ansible -y
`

Pull the repository

`
git clone https://github.com/ameen-mcmxc/SNORT_Automation.git
`

`
cd SNORT_Automation
`

Run the main playbook to install Snort

`
ansible-playbook snort.yml
`




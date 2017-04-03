# ansible-tia-devoxx2017
This is an ansible set-up for the devoxx FR 2017 TIA

## Notice
This playbook is used for centos 7, it is tested on Amazon EC2 (ami-centos-7.2 (ami-303b1f43))
It still need to be update in order to execute ansibleplaybook
`
	sudo yum -y install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm && \
	sudo yum -y update && \	
	sudo yum -y install tmux httpd python-certbot-apache expect openssl && \
	sudo systemctl start httpd && sudo systemctl enable httpd
`

## install via ansible playbook

This playbook install :
 - a Certifcation Authority (self signed)
 - a Certifcation Authority Intermediate (signed by the upper Certifcation Authority)
 - an SSL Certificat (signed by the upper Certifcation Authority)
 
 - it install the ssl certificate in apache for the demo
 
 
 
`ansible-playbook -i inventory-production.txt http-openssl.yaml`

### variables 

 - is_openssl_template: True
 - fqn_website: the web site for the ssl certificat example test.parisjug.net
 
### The script need to be improve
 - better variables
 - better organisation
 - upgrade ansible version (curent version is 2.2.1.0)
 
## Misc
 - https://www.sslshopper.com/article-most-common-openssl-commands.html
 - https://docs.ansible.com
 - https://letsencrypt.org/
 - https://community.letsencrypt.org/
 - https://certbot.eff.org/
 - https://www.ssllabs.com/index.html
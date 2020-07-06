## Set up nodejs project for blank (DigitalOcean) Linux Ubuntu instance

- Update the latest dependencies `sudo apt-get update && sudo apt-get upgrade`
- Install node JS (Latest version as of June 2020 is Node.js v14.x)
  - `curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -`
  - `sudo apt-get install -y nodejs`
- Install nginx `sudo apt-get install apache2`
- Generate ssh key
  - `ssh-keygen -t rsa -C "your_email@example.com"`
  - The location for generated key is inside `~/.ssh`
- Clone project into `~` directory, make sure to include a project setup script `deploy.sh` in the git directory
- Set up the apache configuration which you'll likey to edit /etc/apache2/ (https://www.digitalocean.com/community/tutorials/how-to-set-up-apache-virtual-hosts-on-ubuntu-16-04)
- For sub-domain deployment, refer to: https://www.binarytides.com/create-localhost-sub-domains-apache-ubuntu/
	- First edit the /etc/hosts file to add the subdomains you wish to create
		```
		127.0.0.1       localhost
        127.0.1.1       enlightened
        127.0.0.1       a.localhost
		```
	- Then add a new virtual host in the same file as the main domain



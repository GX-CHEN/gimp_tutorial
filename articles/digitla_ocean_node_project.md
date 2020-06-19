## Set up nodejs project for blank (DigitalOcean) Linux Ubuntu instance

- Update the latest dependencies `sudo apt-get update && sudo apt-get upgrade`
- Install node JS (Latest version as of June 2020 is Node.js v14.x)
  - `curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -`
  - `sudo apt-get install -y nodejs`
- Install nginx `sudo apt-get install nginx`
- Generate ssh key
  - `ssh-keygen -t rsa -C "your_email@example.com"`
  - The location for generated key is inside `~/.ssh`
- Clone project into `~` directory, make sure to include a project setup script `deploy.sh` in the git directory
- Set up the nginx configuration, the location of config file is `/etc/nginx/sites-available/default`
- After verify that the nginx is setup correctly, we'll use the certbot to set the https ssl
  - `sudo add-apt-repository ppa:certbot/certbot`
  - `sudo apt-get update`
  - `sudo apt-get install python-certbot-nginx`
  - `sudo certbot --nginx -d example.com -d www.example.com`
  - Verify the auto-new is correctly: `sudo certbot renew --dry-run`

A combined dependency install script:

```
sudo apt-get update && sudo apt-get upgrade
curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
sudo apt-get install -y nodejs
sudo apt-get install nginx
sudo add-apt-repository ppa:certbot/certbot
sudo apt-get update
sudo apt-get install python-certbot-nginx
```
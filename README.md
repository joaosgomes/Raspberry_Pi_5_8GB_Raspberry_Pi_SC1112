
````
echo "# Raspberry_Pi_5_8GB_Raspberry_Pi_SC1112" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/joaosgomes/Raspberry_Pi_5_8GB_Raspberry_Pi_SC1112.git
git push -u origin main

git remote add origin https://github.com/joaosgomes/Raspberry_Pi_5_8GB_Raspberry_Pi_SC1112.git
git branch -M main
git push -u origin main
````
 

# Raspberry_Pi_5_8GB_Raspberry_Pi_SC1112

## Headless Config

### network-config

```yaml
network:
  version: 2
  renderer: networkd
  ethernets:
    eth0:
      dhcp4: true
      optional: true
  wifis:
    wlan0:
      dhcp4: true
      optional: true
      access-points:
        "WIFI_NETWORK_SSID":
          password: "WIFI_NETWORK"
          hidden: false # Set to true if your Wi-Fi network is hidden
```

### user-data

```yaml
power_state:
  mode: reboot
```

## SSH

Connect to SSH:

```sh
ssh -o UserKnownHostsFile=/dev/null joaosgomes@joaosgomes.local
```

## Update and Upgrade

```sh
sudo apt update
sudo apt upgrade
```

## Install XFCE4 and xrdp

```sh
sudo apt install xfce4 xfce4-goodies -y
sudo apt install xrdp -y
```

## Enable xrdp

```sh
sudo systemctl status xrdp
sudo systemctl start xrdp
sudo ufw status
curl ifconfig.me
sudo systemctl enable xrdp
```

## Configure xfce4-session

```sh
cd $HOME
echo "xfce4-session" | tee .xsession
sudo systemctl restart xrdp
```

## Install Git and Docker

```sh
sudo apt install git -y
git --version
curl -sSL https://get.docker.com | sh || error "Failed to install Docker."
sudo docker start
sudo usermod -aG docker $USER || error "Failed to add user to the Docker usergroup."
```
## Reboot

```sh
sudo reboot
```

## Install shellinabox

```sh
sudo apt install shellinabox

 sudo systemctl status shellinabox

# https://joaosgomes.local:4200/

```

## Install net-tools

```sh
sudo apt install net-tools
```

## Portainer

```sh
docker volume create portainer_data
docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ee:latest

# https://joaosgomes.local:9443/

```

## landscape-sysinfo

Run `landscape-sysinfo` to check system information.

## Jenkins Docker Install

```sh
docker run -p 8080:8080 -p 50000:50000 --restart=on-failure -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts
```
## Jenkins Linux Install

Install default-jre:

```sh
sudo apt install default-jre
```

Install default-jdk:

```sh
sudo apt install default-jdk
```

Check Java version:

```sh
java -version
javac -version
```

```sh

# Reference: https://www.jenkins.io/doc/book/installing/linux/

sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins

systemctl status jenkins


sudo systemctl status jenkins

sudo systemctl enable jenkins


sudo cat /var/lib/jenkins/secrets/initialAdminPassword

# http://joaosgomes.local:8080/

```



https://www.digitalocean.com/community/tutorials/how-to-install-jenkins-on-ubuntu-22-04 (Not Working)


~~wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key |sudo gpg --dearmor -o /usr/share/keyrings/jenkins.gpg~~



~~sudo sh -c 'echo deb [signed-by=/usr/share/keyrings/jenkins.gpg] http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'~~


sudo rm /usr/share/keyrings/jenkins.gpg






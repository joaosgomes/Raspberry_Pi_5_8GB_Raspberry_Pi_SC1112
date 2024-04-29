
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


sudo apt update
sudo apt upgrade

sudo apt install xfce4 xfce4-goodies -y
sudo apt install xrdp -y

sudo systemctl status xrdp
sudo systemctl start xrdp
sudo ufw status
curl ifconfig.me
sudo systemctl enable xrdp

cd $HOME
echo "xfce4-session" | tee .xsession
sudo systemctl restart xrdp


sudo apt install git -y
git --version
curl -sSL https://get.docker.com | sh || error "Failed to install Docker."
sudo docker start
sudo usermod -aG docker $USER || error "Failed to add user to the Docker usergroup."

sudo reboot



sudo apt install shellinabox

sudo apt install net-tools

docker volume create portainer_data
docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ee:latest


landscape-sysinfo











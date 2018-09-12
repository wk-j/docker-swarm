## Commands

```
sudo vim /etc/hosts

192.168.0.22    manager
192.168.0.22    worker1

ping -c 3 manager
ping -c 3 worker1

# install docker Ubuntu 18.04
sudo apt install apt-transport-https software-properties-common ca-certificates -y
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
sudo apt update
apt-cache policy docker-ce
sudo apt install docker-ce
sudo systemctl status docker

sudo service network-manager restart

docker swarm init  --advertise-addr 192.168.0.20 --listen-addr 0.0.0.0
docker swarm join --token SWMTKN-1-5ok0pa7j9azm2r3fsa9x2qwmvn2ef0frd7o4a8mci3a4sqdti9-dogt5pllrh4f0jpd8ykqvt5p2 192.168.0.20:2377

docker node ls

# deploy
docker service create --name docker-cloud --publish 8080:80 wearetherock/docker-cloud:latest
docker service ls


docker-machine ls
```
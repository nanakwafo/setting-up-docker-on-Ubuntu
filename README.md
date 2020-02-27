# setting-up-docker-on-Ubuntu

Install required packages:
```
sudo apt-get update

sudo apt-get -y install \
  apt-transport-https \
  ca-certificates \
  curl \
  gnupg-agent \
  software-properties-common

```
Add the Docker GPG key and repo:
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

sudo apt-key fingerprint 0EBFCD88

sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"

```
Install Docker CE packages:
```
sudo apt-get update

sudo apt-get install -y docker-ce=5:18.09.5~3-0~ubuntu-bionic docker-ce-cli=5:18.09.5~3-0~ubuntu-bionic containerd.io

```
Give cloud_user permission to run docker commands:
```
sudo usermod -a -G docker cloud_user

```
Log out and back in.
Test the installation by running a simple container:
```
docker run hello-world
```

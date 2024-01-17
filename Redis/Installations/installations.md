## Linux

### Ubuntu/Debian

Pre-requisites
```
sudo apt install lsb-release curl gpg
```
Add the repository to the apt index, update it, and then install:
```
curl -fsSL https://packages.redis.io/gpg | sudo gpg --dearmor -o /usr/share/keyrings/redis-archive-keyring.gpg

echo "deb [signed-by=/usr/share/keyrings/redis-archive-keyring.gpg] https://packages.redis.io/deb $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/redis.list

sudo apt-get update
sudo apt-get install redis
```
#### Install from Snapcraft

```
sudo snap install redis
```
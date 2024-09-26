# Nillion-Verifier

Nillion verifier program started again

now you can verify your account and stake again

## Install docker
```
sudo apt update -y && sudo apt upgrade -y
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done

sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
```
sudo apt update -y && sudo apt upgrade -y
```
```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
Check docker version
```
docker --version
```

## Install verifier
```
docker pull nillion/verifier:v1.0.1
```
```
mkdir -p nillion/accuser
```
```
docker run -v ./nillion/verifier:/var/tmp nillion/verifier:v1.0.1 initialise
```
Save your account details

You can check keys/address of the accuser
```
cat nillion/accuser/credentials.json
```
get [faucet](https://faucet.testnet.nillion.com/)

## Run verifier accuser
```
docker run -v ./nillion/verifier:/var/tmp nillion/verifier:v1.0.1 verify --rpc-endpoint "https://testnet-nillion-rpc.lavenderfive.com"
```

## Verify your node in the dashboard

Go to [verifier dashboard](https://verifier.nillion.com/verifier)

Verify your node 



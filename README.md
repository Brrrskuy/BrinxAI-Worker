# <h2 align=center>BrinxAI Worker Nodes AI</h2>
- Buy VPS di : [t.me/skuycloud](t.me/skuycloud)
- Trakteer buat buy Kopi : https://trakteer.id/brrrskuy/tip `<---`

| **Requirement**         |
|-------------------------|
| 8GB/16GB RAM       |
| 4core/8core    CPU   |

# Install Docker
```
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y && curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - && sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable" && sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin -y
```
# Enable Docker
```
sudo systemctl start docker
sudo systemctl enable docker
```
# Open Firewall UFW
```
sudo ufw allow OpenSSH
sudo ufw enable
```
# Allow Port Worker and Relay
```
sudo ufw allow 5011/tcp
sudo ufw allow 1194/udp
```
# You can New Regist same gmail and password
https://brinxai.com/login

# Next add Worker and copy UUID
![Cuplikan layar 2025-05-17 205610](https://github.com/user-attachments/assets/87e86860-39b5-4df7-b30a-ad6ec847b5e7)

# Run Script on Your VPS and Copy Paste your UUID
```
git clone https://github.com/admier1/BrinxAI-Worker-Nodes
cd BrinxAI-Worker-Nodes
chmod +x install_ubuntu.sh
./install_ubuntu.sh
```
# Install Models on Worker Nodes
  **Stable Diffusion Models**
  ```
  docker run -d --name stable-diffusion --network brinxai-network --cpus=6 --memory=8192m -p 127.0.0.1:5060:5060 -e PORT=5060 admier/brinxai_nodes-stabled:latest
  ```
  **Upscaller Models**
  ```
  docker run -d --name upscaler --network brinxai-network --cpus=2 --memory=8192m -p 127.0.0.1:3800:3800 admier/brinxai_nodes-upscaler:latest
  ```
  **Text-ui Models**
  ```
  docker run -d --name text-ui --network brinxai-network --cpus=4 --memory=8192m -p 127.0.0.1:5012:5012 admier/brinxai_nodes-text-ui:latest
  ```
  **Rembg Models**
  ```
  docker run -d --name rembg --network brinxai-network --cpus=2 --memory=4096m -p 127.0.0.1:7000:7000 admier/brinxai_nodes-rembg:latest
  ```
# Run the Relay Image from Docker Hub
`Note : Button relay not interactive , wait for next info to run this`
```
sudo docker run -d --name brinxai_relay --cap-add=NET_ADMIN -p 1194:1194/udp admier/brinxai_nodes-relay:latest# BrinxAI-Worker
```

# BrinxAI-Worker Nodes

# Install Docker
```
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y && curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - && sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable" && sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin -y
```

# Enable Docker
```
sudo systemctl start docker
```
```
sudo systemctl enable docker
```

# Open Firewall
```
sudo ufw allow OpenSSH
```
```
sudo ufw enable
```

# Allow Port 
```
sudo ufw allow 5011/tcp
```
```
sudo ufw allow 1194/udp
```

# Pull Worker Image from Docker Hub
```
docker pull admier/brinxai_nodes-worker:latest
```
# Run Script on Linux (Ubuntu)
```
git clone https://github.com/admier1/BrinxAI-Worker-Nodes
cd BrinxAI-Worker-Nodes
chmod +x install_ubuntu.sh
./install_ubuntu.sh
```

# Add Model to Active Worker rembg,text-ui,upscaller,stable-difusion (Click manualy turn models)
![Cuplikan layar 2025-01-15 010039](https://github.com/user-attachments/assets/44a89a6e-44a4-4a5f-bb6c-f259ddda479c)

# Run the Relay Image from Docker Hub
```
sudo docker run -d --name brinxai_relay --cap-add=NET_ADMIN -p 1194:1194/udp admier/brinxai_nodes-relay:latest# BrinxAI-Worker
```

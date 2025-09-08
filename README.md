
step to follow
__________________________________________
curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com noble main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update
sudo apt install packer -y
packer --version
clear
ls -la
cd devops-world/
mkdir packer-ubuntu
code .
git clone https://github.com/sheakimran/packer.git
cd packer
ls -la
code .
packer validate packer.json
packer plugins install github.com/hashicorp/amazon
packer validate packer.json
packer build -var-file=packer-vars.json packer.jso

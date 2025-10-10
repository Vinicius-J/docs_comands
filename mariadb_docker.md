# — REMOVER POSSÍVEIS VERSÕES ANTERIORES CONFLITANTES —
sudo apt-get remove -y docker docker-engine docker.io docker-compose docker-compose-v2 podman-docker containerd runc

# (Opcional) limpar dados antigos, se quiser recomeçar do zero:
# sudo rm -rf /var/lib/docker /var/lib/containerd

# — ATUALIZAR A LISTA DE PACOTES —
sudo apt-get update

# — INSTALAR DEPENDÊNCIAS NECESSÁRIAS —
sudo apt-get install -y \
  ca-certificates \
  curl \
  gnupg \
  lsb-release \
  software-properties-common

# — ADICIONAR A CHAVE GPG DO DOCKER —
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

# — ADICIONAR O REPOSITÓRIO DO DOCKER —
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" \
  | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# — ATUALIZAR A LISTA DE PACOTES (com o novo repositório) —
sudo apt-get update

# — INSTALAR O DOCKER (ENGINE, CLI e containerd) —
sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

# — (Opcional) adicionar seu usuário ao grupo “docker” para não ter que usar sudo sempre —
sudo usermod -aG docker $USER
# Atenção: depois disso, você provavelmente precisará fazer logout/login ou rodar `newgrp docker` para aplicar.

# — Verificar se o Docker está funcionando —
docker --version
sudo systemctl status docker
# e testar com:
sudo docker run hello-world

# — RODAR O CONTAINER DO MARIADB —  
# (adaptado para incluir volume persistente, variáveis de ambiente, reinício automático)
sudo docker run -d \
  --name bdmariadb1 \
  --restart always \
  -p 3306:3306 \
  -v ~/mariadb_data:/var/lib/mysql \
  -e MYSQL_ROOT_PASSWORD="9j6vqT9aWzdJ" \
  mariadb:latest

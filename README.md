<p align="center">
<img src="https://cwmkt.com.br/wp-content/uploads/2023/08/logo-github-cwmkt.svg" alt="DispZap Whats Marketing" width="240" />
<p align="center">Seja bem-vindo ao Guia de Instalação Portainer 🚀</p>
</p>
  
<p align="center">
<img src="https://whatsapp.com/favicon.ico" alt="WhatsAPP-logo" width="32" />
<span>Grupo WhatsaAPP: </span>
<a href="https://link.cwmkt.com.br/grupo-whats" target="_blank">Grupo</a>
</p>

<hr />
<hr />

**Manual de Instalação Portainer**

**Para instalar o Portainer em uma VPS com Ubuntu 20.04, você pode seguir os seguintes passos**

</p>
Certifique-se de ter permissões de administrador em sua VPS.
</p>
Atualize os repositórios do Ubuntu executando o seguinte comando:
</p>
sudo apt update && apt upgrade -y
</p>

----------------------------------------------------------------------------

**Instale o Docker em sua VPS. Você pode fazer isso com o seguinte comando:**


sudo apt install docker.io -y
</p>
Inicie o serviço do Docker com o seguinte comando:
</p>
sudo systemctl start docker
</p>
Verifique se o serviço do Docker está em execução com o seguinte comando:
</p>
sudo systemctl status docker
</p>
Faça o logout e login novamente para que as alterações sejam aplicadas.
</p>

----------------------------------------------------------------------------

**Ativando SSL OPCIONAL**

sudo apt install nginx -y
</p>
sudo rm /etc/nginx/sites-enabled/default
</p>
sudo nano /etc/nginx/sites-available/portainer
</p>

```
server {
  server_name portainer.seudominio.com.br;
  location / {
    proxy_pass http://127.0.0.1:9000;
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection 'upgrade';
    proxy_set_header Host $host;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-Proto $scheme;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_cache_bypass $http_upgrade;
  }
   }
 ```
   
</p>
 sudo ln -s /etc/nginx/sites-available/portainer /etc/nginx/sites-enabled
</p>
sudo apt-get install snapd -y
</p>
sudo snap install notes
</p>
sudo snap install --classic certbot
</p>
sudo certbot --nginx
</p>
sudo service nginx restart
</p>

----------------------------------------------------------------------------

**Baixe o contêiner do Portainer com o seguinte comando:**

</p>
sudo docker pull portainer/portainer-ce
</p>

Crie um volume para persistir os dados do Portainer, como contêineres, imagens e outros dados. Para fazer isso, execute o seguinte comando:

</p>
sudo docker volume create portainer_data
</p>

Inicie o contêiner do Portainer com o seguinte comando:

sudo docker run -d -p 8000:8000 -p 9000:9000 --name portainer --restart always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce
</p>
Isso iniciará o contêiner do Portainer e ele estará acessível através do endereço IP da sua VPS na porta 9000. Por exemplo, se o endereço IP da sua VPS for IP, você poderá acessar o Portainer abrindo um navegador da web e digitando o seguinte endereço:

</p>
sudo systemctl restart docker
</p>

https://seusite
Você será direcionado para a página de login do Portainer, onde poderá criar uma conta de usuário e começar a gerenciar seus contêineres Docker.


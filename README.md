<p align="center">
	<img src="https://www.portainer.io/hubfs/portainer-logo-black.svg" alt="Quepasa-logo" width="100" />	
	<p align="center">Implante, configure, solucione problemas e proteja contêineres em minutos no Kubernetes, Docker, Swarm e Nomad em qualquer data center, nuvem, borda de rede ou dispositivo IIOT</p>
</p>
<hr />
<p align="left">
	<img src="https://telegram.org/favicon.ico" alt="Telegram-logo" width="32" />
	<span>Grupo e Canal Telegram: </span>
	<a href="https://t.me/quepasa_api" target="_blank">Grupo</a>
	<span> || </span>
	<a href="https://t.me/quepasa_channel" target="_blank">Canal</a>
</p>
<hr />
<p align="left">
	<img src="https://whatsapp.com/favicon.ico" alt="WhatsAPP-logo" width="32" />
	<span>Grupo WhatsaAPP: </span>
	<a href="https://chat.whatsapp.com/Cv5WfmujRzE09yQ6hagYim" target="_blank">Grupo</a>
</p>
----------------------------------------------------------------------------
</p>

**Gostou do Tutorial? Faça sua Contribuição**

<img src="https://github.com/EngajamentoFlow/quepasa/blob/main/Contribui%C3%A7%C3%A3o.png" alt="Quepasa-logo" width="200" />
</p>

**Manual de Instalação Portainer**

----------------------------------------------------------------------------

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


sudo apt install docker.io
</p>
Inicie o serviço do Docker com o seguinte comando:
</p>
sudo systemctl start docker
</p>
Verifique se o serviço do Docker está em execução com o seguinte comando:
</p>
sudo systemctl status docker
Adicione seu usuário ao grupo docker para evitar ter que usar sudo com cada comando Docker. Para fazer isso, execute o seguinte comando:
</p>
sudo usermod -aG docker ${USER}
Faça o logout e login novamente para que as alterações sejam aplicadas.
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

http://123.45.67.89:9000
Você será direcionado para a página de login do Portainer, onde poderá criar uma conta de usuário e começar a gerenciar seus contêineres Docker.

----------------------------------------------------------------------------

</p>

**Gostou do Tutorial? Faça sua Contribuição**

<img src="https://github.com/EngajamentoFlow/quepasa/blob/main/Contribui%C3%A7%C3%A3o.png" alt="Quepasa-logo" width="200" />
</p>
----------------------------------------------------------------------------

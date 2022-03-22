## Projeto de instalação do Magento usando Ansible, Nginx, Vagrant
### Instalação totalmente automatizada!
### Como testar

- Instale o Virtualbox e o Vagrant;
- Baixe os arquivo ou faça um git clone;
- No terminal, digite o comando $ vagrant up
- Após o término, basta acessar pelo navegador o endereço http:// 192.168.33.25

#### Explicando o projeto:
> - O Vagrant irá iniciar uma máquina virtua com Ubuntu focal, com as configurações definidas no arquivo Vagrantfile.
> - Logo após a criação da máquina o Vagrant irá instalar o ansible;
> - A partir desse momento o ansible irá realizar todas as instalações e configurações via playbooks
> - Após instalar os requisitos (php, nginx, mysql, composer) será instalado o magento;
> - As pré configurações do magento estão defininas no arquivo de variáveis all.yml na pasta group_vars

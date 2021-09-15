# wordpress-ansible
# - Configurando o linux

#### Acesse o pasta sudoers:  

>ansible@ubuntu:~/ sudo visudo

#### Encontre *User privilege specification*:

user  ALL=(ALL:ALL) NOPASSWD: ALL

# - SSH

## Instalação:

>ansible@ubuntu:~/ sudo apt-get install openssh-server

#### Abra o arquivo do SSH:

>ansible@ubuntu:~/ sudo gedit etc/ssh/sshd_config

#### Altere o seguinte comando *#PermitRootLogin prohibit-password* para:

>PermitRootLogin yes

#### Reinicie o SSH server:

>ansible@ubuntu:~/ service ssh restart

#### Crie um chave SSH:

>ansible@ubuntu:~/ ssh-keygen

#### Faça copia da chave SSH:

>ansible@ubuntu:~/ cp -p ~/.ssh/id_rsa.pub ~/.ssh/authorized_keys

# - Instalação do Ansible...

#### Crie um repositorio Ansible:

>ansible@ubuntu:~/ sudo apt-add-repository ppa:ansible/ansible

#### Confirme < ENTER >.

#### Faça uma atualização:

>ansible@ubuntu:~/ sudo apt-get update

#### Instale o Ansible:

>ansible@ubuntu:~/ sudo apt-get install ansible

#### Verifique a versão do Ansible:

>ansible@ubuntu:~/ ansible --version

#### Criando o Playbook...

#### Crie uma pasta Wordpress-ansible:

>ansible@ubuntu:~/ mkdir wordpress-ansible

#### Dentro da pasta wordpress-ansible, crie pasta roles, arquivo hosts e playbook.yml:

>ansible@ubuntu:~/ cd wordpress-ansible 
> 
>ansible@ubuntu:~/wordpress-ansible$ touch hosts 
> 
>ansible@ubuntu:~/wordpress-ansible$ touch playbook.yml 

#### Abra o arquivo hosts:

>ansible@ubuntu:~/wordpress-ansible$ sudo nano hosts

#### Acesse o caminho abaixo e copie o codigo, caso tenha mais hosts, adicione o ip do servidor no arquivo:

#### Acesse o caminho abaixo e copie o codigo no arquivo playbook.yml:

>ansible@ubuntu:~/wordpress-ansible/ sudo nano playbook.yml  

#### Roles:

>ansible@ubuntu:~/wordpress-ansible/roles$ ansible-galaxy init server  
>
>ansible@ubuntu:~/wordpress-ansible/roles$ ansible-galaxy init php  
>
>ansible@ubuntu:~/wordpress-ansible/roles$ ansible-galaxy init mysql  
>
>ansible@ubuntu:~/wordpress-ansible/roles$ ansible-galaxy init wordpress  

## - Tasks das roles

#### Codigo server:

>ansible@ubuntu:~/wordpress-ansible/roles/server/tasks$ sudo nano main.yml

#### Codigo PHP:

>ansible@ubuntu:~/wordpress-ansible/roles/php/tasks$ sudo nano main.yml

#### Codigo MySQL:

>ansible@ubuntu:~/wordpress-ansible/roles/mysql/tasks$ sudo nano main.yml

#### Codigo Mysql pasta Default:

>ansible@ubuntu:~/wordpress-ansible/roles/mysql/defaults/main.yml

#### Codigo Wordpress:

>ansible@ubuntu:~/wordpress-ansible/roles/wordpress/tasks$ sudo nano main.yml

#### Codigo Wordpress pasta handlers:

>ansible@ubuntu:~/wordpress-ansible/roles/wordpress/handlers$ sudo nano main.yml

## instalação concluida, digite o IP do host no navegador web para acessar a aplicação WordPress.

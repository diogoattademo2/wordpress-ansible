# wordpress-ansible
## - Configurando o linux

#### Acesse o pasta sudoers:  

>user@ubuntu:~$ sudo visudo

#### Encontre *User privilege specification*:

user  ALL=(ALL:ALL) NOPASSWD: ALL

## - Instalando o SSH:

>user@ubuntu:~$ sudo apt-get install openssh-server

#### Abra o arquivo do SSH:

>user@ubuntu:~$ sudo gedit etc/ssh/sshd_config

#### Altere o seguinte comando *#PermitRootLogin prohibit-password* para:

>PermitRootLogin yes

#### Reinicie o SSH server:

>user@ubuntu:~$ service ssh restart

#### Crie um chave SSH:

>user@ubuntu:~$ ssh-keygen

#### Faça copia da chave SSH:

>user@ubuntu:~$ cp -p ~/.ssh/id_rsa.pub ~/.ssh/authorized_keys

## - Instalando o Ansible...

#### Crie um repositorio Ansible:

>user@ubuntu:~$ sudo apt-add-repository ppa:ansible/ansible

#### Confirme < ENTER >.

#### Faça uma atualização:

>user@ubuntu:~$ sudo apt-get update

#### Instale o Ansible:

>user@ubuntu:~$ sudo apt-get install ansible

#### Verifique a versão do Ansible:

>user@ubuntu:~$ ansible --version

#### Criando o Playbook...

#### Crie uma pasta Wordpress-ansible:

>user@ubuntu:~$ mkdir wordpress-ansible

#### Dentro da pasta wordpress-ansible, crie pasta roles, arquivo hosts e playbook.yml:

>user@ubuntu:~$ cd wordpress-ansible 
> 
>user@ubuntu:~/wordpress-ansible$ touch hosts 
> 
>user@ubuntu:~/wordpress-ansible$ touch playbook.yml 

#### Abra o arquivo hosts:

>user@ubuntu:~/wordpress-ansible$ sudo nano hosts

#### Acesse o caminho abaixo e copie o codigo, caso tenha mais hosts, adicione o ip do servidor no arquivo:

**[Hosts](https://github.com/powblack/ansible---linux/blob/master/hosts)**

#### Acesse o caminho abaixo e copie o codigo no arquivo playbook.yml:

**[Playbook](https://github.com/powblack/ansible---linux/blob/master/playbook.yml)**

#### Criando as roles:

>user@ubuntu:~/wordpress-ansible/roles$ ansible-galaxy init server  
>
>user@ubuntu:~/wordpress-ansible/roles$ ansible-galaxy init php  
>
>user@ubuntu:~/wordpress-ansible/roles$ ansible-galaxy init mysql  
>
>user@ubuntu:~/wordpress-ansible/roles$ ansible-galaxy init wordpress  

## - Tasks das roles

#### Codigo server:

>user@ubuntu:~/wordpress-ansible/roles/server/tasks$ sudo nano main.yml

**[Server/Tasks](https://github.com/powblack/ansible---linux/blob/master/roles/server/tasks/main.yml)**  

#### Codigo PHP:

**[PHP/Tasks](https://github.com/powblack/ansible---linux/blob/master/roles/php/tasks/main.yml)**

>user@ubuntu:~/wordpress-ansible/roles/php/tasks$ sudo nano main.yml

#### Codigo MySQL:

**[MySQL/Tasks](https://github.com/powblack/ansible---linux/blob/master/roles/mysql/tasks/main.yml)**

>user@ubuntu:~/wordpress-ansible/roles/mysql/tasks$ sudo nano main.yml

#### Codigo Mysql pasta Default:

**[MySQL/Defaults](https://github.com/powblack/ansible---linux/blob/master/roles/mysql/defaults/main.yml)**

>user@ubuntu:~/wordpress-ansible/roles/mysql/defaults/main.yml

#### Codigo Wordpress:

**[Wordpress/Tasks](https://github.com/powblack/ansible---linux/blob/master/roles/wordpress/tasks/main.yml)**

>user@ubuntu:~/wordpress-ansible/roles/wordpress/tasks$ sudo nano main.yml

#### Codigo Wordpress pasta handlers:

**[Wordpress/Handlers](https://github.com/powblack/ansible---linux/blob/master/roles/wordpress/handlers/main.yml)**

>user@ubuntu:~/wordpress-ansible/roles/wordpress/handlers$ sudo nano main.yml

## instalação concluida, digite o IP do host no navegador web para acessar a aplicação WordPress.

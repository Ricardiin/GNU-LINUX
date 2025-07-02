    Etapa 1 copiar esses comandos

#atualizando as listas do Apt
sudo apt update

#instalando as dependências do Apache2 Server
#opção da contra barra (\): criar uma quebra de linha no terminal
sudo apt install git vim perl python2 python3 unzip pwgen xz-utils bzip2 curl ghostscript zlib1g \
zlib1g-dev apt-transport-https

#instalando o Apache2 Server, PHP 8.x e suas dependências (SUPORTE EXTRA DE DEPENDÊNCIAS)
#opção da contra barra (\): criar uma quebra de linha no terminal
sudo apt install apache2 apache2-utils apache2-bin apache2-data php php-cli php-common php-mysql \
php-opcache php-readline php-bcmath php-curl php-intl php-mbstring php-xml php-zip php-soap php-json \
php-imagick libapache2-mod-php libapr1 libaprutil1-ldap libaprutil1 libaprutil1-dbd-sqlite3 php-dev \
php-pear libmcrypt-dev php-gd php-imap php-memcache php-pspell php-tidy php-xmlrpc php-ldap php-cas \
php-apcu xmlrpc-api-utils php-bz2

#habilitando os módulos do Apache2 Server (NÃO COMENTADO NO VÍDEO)
#opção da contra barra (\): criar uma quebra de linha no terminal
sudo a2enmod cgi alias authz_host deflate dir expires headers mime rewrite autoindex \
negotiation setenvif

#reiniciando o serviço do Apache2 Server
#opções do comando systemctl: restart (Stop and then start one or more units)
sudo systemctl restart apache2 

__________________________________________________________

    Etapa 2

#verificando o serviço do Apache2 Server
#opções do comando systemctl: status (runtime status information), restart (Stop and then start one or more units),
#stop (Stop (deactivate) one or more units), start (Start (activate) one or more units), reload (Asks all units 
#listed on the command line to reload their configuration)
sudo systemctl status apache2
sudo systemctl restart apache2
sudo systemctl reload apache2
sudo systemctl stop apache2
sudo systemctl start apache2

#analisando os Log's e mensagens de erro do Servidor do Apache2 (NÃO COMENTADO NO VÍDEO)
#opção do comando journalctl: x (catalog), e (pager-end), u (unit)
sudo journalctl -xeu apache2

#verificando os arquivos de configuração do Apache2 Server (NÃO COMENTADO NO VÍDEO)
#opção do comando apache2ctl: configtest (Run a configuration file syntax test)
sudo apache2ctl configtest 

__________________________________

#verificando a versão do Apache2 Server
#opção do comando apache2ctl: -V (version)
sudo apache2ctl -V

#verificando a versão do PHP
#opção do comando php: -v (version)
sudo php -v

___________________________________
informação: /var/www/html/                 <-- Diretório padrão das Hospedagem de Site do Apache2 Server

    etapa 3 adicionando usuarios no www-data

ps:fazer isso em cada usuario vai ter q se logar no senac admin e richard

#adicionando o usuário local (logado) no grupo do Apache2 Server
#opções do comando usermod: -a (append), -G (groups), $USER (environment variable)
sudo usermod -a -G www-data $USER

#fazendo login em um novo grupo do Apache2 Server
newgrp www-data

#verificando os identificadores de usuário e grupos
id

#verificando as informações do grupo WWW-DATA do Apache2 Server
#opção do comando getent: group (the database system group)
sudo getent group www-data

#recomendo fazer logout do usuário para testar as permissões de grupos
#OBSERVAÇÃO: você pode utilizar o comando: exit, logout ou tecla de atalho: Ctrl+D
exit


________________________

#acessando o diretório padrão dos Sites do Apache2 Server (DocumentRoot)
cd /var/www/html

#criando o diretório de teste das páginas HTML e PHP
#opção do comando mkdir: -v (verbose)
sudo mkdir -v teste

#alterando as permissões do diretório de teste
#opção do comando chmod: -R (recursive), -v (verbose), 2775 (Set-GID=2,User=RWX,Group=RWS,Other=R-X)
#opções das permissões: R (read), W (write), X (execute), S (Set-Group ID)
sudo chmod -Rv 2775 teste/

#alterando o dono e grupo do diretório de teste
#opção do comando chown: -R (recursive), -v (verbose), root (User), . (separate), www-date (group)
sudo chown -Rv root.www-data teste/

#listando o diretório criado do site teste
#opção do comando ls: -l (long listing), -h (human-readable)
ls -lh

#acessando o diretório criado do site teste
cd teste

_______

/var/www/html/teste$ sudo vim richard.html

____

comandos:
senac@wsrichard:/var/www/html/teste$ sudo vim richard.php
senac@wsrichard:/var/www/html/teste$ sudo vim phpinfo.php

_________________________

DESAFIO 
DESAFIO-01: CRIAR UM NOVO DIRETÓRIO NA RAIZ DO APACHE2 EM: /var/www/html
Cria uma pasta richard
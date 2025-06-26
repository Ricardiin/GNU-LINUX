ws= Significa Web server
rayka= 10.26.44.230
richard= 10.26.44.231
user:wsrichard
usuario:senac
senha:123@senac
local server SENAC:10.26.44.29

criando windows server 
    SSH VIA gitbash..

entrando via ssh= ssh senac@10.26.44.29 ENTER dar yes e entrar .. confirma

    PUTTY via.
digitar 
senac@10.26.44.29 e entrar dar YES na notificação e fim.
--------------------
    Power sheell
senac@10.26.44.29 vai pedir a senha: 123@senac

apertar w e enter pra saber do sistema/pessoas.

-----------------
cuidado ao digitar os comandos.

--
    Tela rosa com daemons, aperta tab e ok [ENTER] 
..
    sudo vim /etc/hostname
clicar insert
do lado do nome wsrichard
wsrichard.richard.intra
!CUIDADO.. pra sair esc.. (shift) :x [ENTER].

    sudo vim /etc/hosts
1ªcoluna um ip <br>
2ªcoluna usuarios <br>
3ªcoluna nao apareceu (locais).
____________________

127.0.0.1      localhost.richard.intra   localhost <br>
127.0.1.1      wsrichard.richard.intra   wsrichard <br>
10.26.44.231  wsrichard.richard.intra   wsrichard <br>

-------------
sudo lspci -v | grep -i ethernet
checa se o cabo ethernet ta funcionando o driver.
_____________
backup .old = um estado anterior do q foi alterado..

*para ajudar numerando as linhas.
ESC :set number ENTER

---------------------
    depois editar o arquivo.. INSERT 

dhcp4:false (ENTER) <br>
(backspace) link-local:[] <br>
(backspace) addresses: [10.26.44.231/24] <br>
........
##CUIDADO DEIXAR TUDO NA MESMA LINHA.
digite todos os comando, cuidado com as linhas e o TAB .. 
--------------------

# This file is generated from information provided by the datasource.  Changes
# to it will not persist across an instance reboot.  To disable cloud-init's
# network configuration capabilities, write a file
# /etc/cloud/cloud.cfg.d/99-disable-network-config.cfg with the following:
# network: {config: disabled}
network:
    ethernets:
        enp0s3:
            dhcp4: false
            link-local: []
            addresses: [10.26.44.231/24]
            routes:
              - to: default
                via: 10.26.44.1
            nameservers:
              addresses: [8.8.8.8, 8.8.4.4]
              search: [richard.intra]
    version: 2


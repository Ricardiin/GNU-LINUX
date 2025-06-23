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
2ªcoluna usuarios
3ªcoluna nao apareceu (locais).
____________________

127.0.0.1      localhost.richard.intra   localhost
127.0.1.1      wsrichard.richard.intra   wsrichard
10.26.44.231  wsrichard.richard.intra   wsrichard

-------------
sudo lspci -v | grep -i ethernet
checa se o cabo ethernet ta funcionando o driver.
_____________
backup .old = um estado anterior do q foi alterado..

*para ajudar numerando as linhas.
ESC :set number ENTER

---------------------
    depois editar o arquivo.. INSERT 

dhcp4:false (ENTER)
(backspace) link-local:[]
(backspace) addresses: [10.26.44.231/24]
........
!CUIDADO DEIXAR TUDO NA MESMA LINHA.
digite todos os comando, cuidado com as linhas e o TAB .. 
--------------------

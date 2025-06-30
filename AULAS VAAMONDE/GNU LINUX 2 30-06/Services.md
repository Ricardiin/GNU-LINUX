sudo sshd -V
sudo ssh -V
! v (CAPSLOCK)
______________________________

ALL: ALL (espaço)
ALL: ALL
ALL: ALL

__________________

sudo vim /etc/hosts.allow

*meu ip do senac 10.26.44.46 (ipv4 do meu pc senac ATUAL) (ps:ele pode mudar o ipv4).

____________________
etapa 06: 
#alterar a variável ListenAddress na linha: 27 
#ListenAddress 172.16.1. para: SEU_ENDEREÇO_IPV4_DO_UBUNTU
#OBSERVAÇÃO: ALTERAR O ENDEREÇO IPv4 CONFORME A SUA NECESSIDADE
ListenAddress SEU_ENDEREÇO_IPV4_DO_UBUNTU
-- 10.26.44.231

#alterar a variável AllowUsers na linha: 77
#OBSERVAÇÃO: ALTERAR O USUÁRIO DE ACESSO CONFORME A SUA NECESSIDADE
AllowUsers SEU_USUÁRIO
-- senac

#alterar a variável AllowGroups na linha: 83
#OBSERVAÇÃO: ALTERAR O GRUPO DE ACESSO CONFORME A SUA NECESSIDADE
AllowGroups SEU_GRUPO_DO_USUÁRIO
-- senac

________________________________________________________

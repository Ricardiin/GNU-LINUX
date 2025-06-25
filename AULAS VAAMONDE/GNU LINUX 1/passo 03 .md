    01_ Verificando as informações do Locale (Localidade) do Sistema Operacional Ubuntu Server

 - sudo localectl

<br>

    verificando as informações de localidades instaladas no Ubuntu Server opção do comando locale: -a (all-locales)

- sudo locale -a

<br>

    02_ Configurando o Locale (Localidade) do Brasil no Sistema Operacional Ubuntu Server

<br>

#gerando a localidade do Português do Brasil (pt_BR) no Ubuntu Server
- sudo locale-gen pt_BR.UTF-8

#configurando a localidade do Português do Brasil no Ubuntu Server
#opção do comando localectl: set-locale (Set the system locale)
- sudo localectl set-locale LANG=pt_BR.UTF-8

#atualizando as localidades do Português do Brasil e Linguagem no Ubuntu Server
- sudo update-locale LANG=pt_BR.UTF-8 LC_ALL=pt_BR.UTF-8 LANGUAGE="pt_BR:pt:en"

#recomendado rebootar o sistema para testar as localidades
sudo reboot
#verificando as mudanças de localidades do sistema no Ubuntu Server depois do reboot
#opção do comando locale: -a (all-locales)
- sudo localectl
- sudo locale -a

<br>

passo 3 4 5 6 so copiar e colar preguiça de copiar

**passo 4 5 6 eu fechei sem querer**
- pra sair (q)

    Passo 7 caso der erro configurar manual.
    <br>

Ao desligar no comando lembres-se de ligar o LINUX no virtual box.*
 <br> 


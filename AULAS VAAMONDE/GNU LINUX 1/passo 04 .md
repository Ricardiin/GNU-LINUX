05_ Desligando e reinicializando o servidor com shutdown no Ubuntu Server
#opção do comando shutdown: -P (poweroff), -h (halt 60 second default), -r (reboot), -c (cancel)
#now (Shutdown immediately), 19:50 (Shutdown at 19:50 pm), +20 (Shutdown in 20 minutes)
sudo shutdown -P

sudo shutdown -h

sudo shutdown -r

sudo shutdown -h now

sudo shutdown -r now


#agendando (schedule) o desligamento ou o reboot do servidor com shutdown

sudo date

sudo shutdown -r 19:50 Servidor será reinicializando às 19:50hs

sudo shutdown -r +20 Servidor será reinicializando em 20 minutos

sudo shutdown -c


#verificando o arquivo temporário de agendamento (schedule) do shutdown (NÃO COMENTADO NO VÍDEO)
#opção o comando cat: -n (number line)

sudo cat -n /run/systemd/shutdown/scheduled

#confirmando que o servidor fez o reboot na hora certa do shutdown (NÃO COMENTADO NO VÍDEO)

#opção do comando last: -x (Display the system shutdown entries and run level changes)
#opção do comando grep: -i (Ignore case distinctions in patterns and input data)
#opção do redirecionador | (pipe): Conecta a saída padrão com a entrada padrão de outro comando
sudo last -x | grep -i reboot

#confirmando o tempo que o servidor está ligado e funcionando após o reboot (NÃO COMENTADO NO VÍDEO)
#opção do comando uptime: -s (system up since)
sudo uptime -s
Script feito conforme pedido do professor.

Arquivos.
Arquivo	instalacao.sh	faz a instalação dos pacotes após verificar o tipo de sistema Debian ou CentOS
webbkp.sh	faz o backup dos pacotes
restauracao.sh	esse faz a restaucação dos backups
desistall.sh	desinstalação completa da solução
Validação da ferramenta:
Arquivo	Função
delserver.sh exclusão das pastas as quais foram feitas o backup.
validacao.sh	 lista as pastas e arquivos restaurados do backup.
Pré requisitos para instalação e funcionamento dos scripts:
Sistema operacional Debian + Apache2 e acesso ao sistema com permissão root. ou Sistema operacional CentOS + HTTPD e acesso ao sistema com permissão root.

1 - Instruções de download e preparação da instalação:
Primeiramente clone o repositório com o comando abaixo:
git clone https://github.com/msbjx5/LinuxClasses.git

Entre na pasta com os scripts
cd LinuxClasses/Nac2

Dê permissão de execução para os scripts da pasta com o comando abaixo:
chmod +x *.sh

2 - Agendamento no cron:
O instalador irá criar automaticamente um agendamento no cron para que o backup seja executado diariamente as 23:00 horas.

Caso não tenha necessidade de alterar o horário do agendamento pule diretamente para o passo 3.

Caso seja necessário alterar esse agendamento edite as linhas 34 e 46 do arquivo install.sh conforme sua necessidade.

2.1 - Instruções cron:
  .---------------- minutos (0 - 59)
  |  .------------- horas (0 - 23)
  |  |  .---------- dia do mês (1 - 31)
  |  |  |  .------- mês (1 - 12) ou jan,fev,mar,abr ...
  |  |  |  |  .---- dia da semana (0 - 6) (Domingo=0 ou 7) ou dom,seg,ter,qua,qui,sex,sab
  |  |  |  |  |
  *  *  *  *  *    usuário    comando-a-ser-executado
3 - Instalação automatizada do script de backup e do agendamento do crontab
Execute o script de instalação e agendamento com permissão de root
sudo ./install.sh

Pronto !
O script de backup já está instalado e agendado para rodar conforme a data e hora selecionada.

4 - Restauração dos backups
Entre na pasta /bkp/script e execute o arquivo restore.sh com permissao de root digitando o comando abaixo:

cd /bkp/script
sudo ./restore.sh

Siga as instruções na tela

5 - Desinstalação do script de backup
Entre na pasta /bkp/script e execute o arquivo uninstall.sh com permissão de root digitando o comando abaixo:
cd /bkp/script
sudo ./uninstall.sh

Todos os arquivos gerados pelo instalador bem como os backups e logs gerados serão apagados, esse procedimento é irreversível.

Agendamento no CRON automatizado pelo script instalador com geração de log.
Script para restore dos backups realizados com geração de log.
Script para desinstalação completa da solução.



## FreeBSD -> Resumo geral
### Aquele manual básico para firmar estudos

&nbsp;

___

### Introdução

Manual simples e resumido sobre o FreeBSD feita com base na documentação do FreeBSD, dispónivel neste endereço: https://docs.freebsd.org/en/books/handbook/, forá demais pesquisas feitas com o intuito de melhorar este documento.

&nbsp;

___

### Curiosidades interessantes 

* Totalmente free -> Licença BSD -> Sua licença é totalmente aberta, isso é, pode usar para qualquer coisa e pode ser trancado caso aquele que fez o fork queira.
* A primeira versão do FreeBSD foi a 1.0 em 1993, depois de problemas de código com a Novell, em 1994, grande parte do código interno foi alterado para de própria autoria do projeto, levando a versão 2.0 que possuia a versão Lite por não estar completo até data de lançamento.
* A equipe do BSD além de fechar a distribuição do BSD com uma fabricante de Discos CD em 1993, recebeu a oportunidade de possuir um computador com internet para a disponibilização do projeto.
* Possibilita o porte para o sistema ARM, exemplo o raspberry.
* O FreeBSD vem com o usuário ```root``` sem senha, já configurado no sistema, mesmo em modo live.

&nbsp;

___

### Hardware

* Compátivel com processadores AMD64, X86 e ARM;
* Necessidade de mémória vária do uso do equipamento com a distro, porém é recomendo o minimo de 96MB de memória (pessoalmente, 1GB de memória é o suficiente para testes);
* Espaço de armazenamento mínimo é 2GB interno;

&nbsp;

___

### Tipos de instaladores

* Installer Images -> Imagens de instaldores do FreeBSD.
* Virtual Machine Images -> Imagens prontas para máquinas virtuais.
* SD Card Images -> Imagens para cartão SD, possívelmente estruturas ARM em maioria.

&nbsp;

___

### Dicas para criar uma mídia de boot 
##### P.S: Totalmente pessoal esse ponto

Particularmente utilizo o Etcher Balena e o Rufus, ambos me atendendo super bem, para o caso de já estar utilizando alguma distro Linux, é possível usar o comando ```dd``` para gerar o disco bootavel externo ou mesmo o Etcher, se está utilizando o Windows, recomendo o uso do Rufus, segue abaixo os Links para o download dos arquivos e do sistema operacional:

* Rufus: https://rufus.ie/pt_BR/
* Etcher: https://www.balena.io/etcher/
* FreeBSD: https://www.freebsd.org/where/

Exemplo fornecido pelo próprio site do FreeBSD Documentation do uso do DD:

```
dd if=Image-FreeBSD-*.img of=/dev/da0 bs=1M conv=sync
```

##### P.S: Recomendo que esteja ciente dos trechos acima antes de realizar a criação (Para não perder tempo) da mídia, forá que se for instalar em alguma máquina, lembre-se de realizar o BK na mesma caso necessário.

&nbsp;

___

### Sistemas de arquivos compátiveis

* MBR (Master boot record) -> 4 partições primárias máximas, porém pode se converter em partições lógicas, somente necessitando de uma partição primária para o sistema;
* GPT (GUID Partition Table / Tabela de partição GUID) -> Possui até 128 partições, eliminando a necessidade de partições lógicas como a MBR

&nbsp;

___

### BIOS

Bom lembrar que existem dois tipos de BIOS utilizadas atualmente, a legancy e a UEFI, sendo a primeira a mais antiga e genérica e a segunda uma versão bolatada entre da Microsoft e a Intel que se espalhou para demais fabricantes e hardwares.

&nbsp;

___

### Entrando no BSD

___

### Boot BSD

Iniciando a instalação do FreeBSD.

![bootbsd](img/bootbsd.png)
<center><small>Tela de boot de BSD, tanto para a instalação quando pós a instalação.</small></center>

&nbsp;

Quando carregada essa tela, ele tem um contador embaixo da tela, para parar esse contador é só pressionar qualquer tecla que não acione alguma função listada.

&nbsp;

Menu de boot:
* ```Multi user``` -> Iniciar sistema com capacidade de multiplos usuários;
    * Aperte ```1, B ou Enter```  para entrar neste modo;
    * Vale comentar que quando essa opção é escolhida, será feito o Boot do S.O já existente ou entra na tela de instalação;
        * Se quebrar o instalador, você entra em modo live, para quebrar o básico ```Ctrl+C```;
* ```Single``` ->  Modo de entrada de prompt para a recuperação do sistema, pelo menos segundo a página do BSD;
    * Aperte ```1 ou b``` para iniciar esse modo;
* ```Escape``` -> Abre um prompt limitado com somente alguns comandos, utilizado para reparo dentro do sistema;
    * Aperte ```3 ou Esc``` para entrar no modo;
* ```Reboot``` -> Reiniciar o sistema; 
* ```Cons``` -> Altera a constante do vídeo -> Tenho que entender melhor esse ainda;

&nbsp;

![#bootoptions](img/bootoptions.png)

&nbsp;

Menu de opções:
* ```Kernel``` -> Seleciona o kernel (nucleo) do sistema que será utilizado no boot do S.O (Sistema operacional);
* ```Boot Options``` -> Opções de boot, para acionar as ações neste menu é só clicar nos valores que a opção faz referência ou na tecla onde a letra está BOLD:
    * 1 -> Para retornar ao menu principal é só teclar o ```1 ou backspace```;
    * 2 -> Recarregue as opções padrões do sistema, aperte ```2 ou d```; 
    * 3 -> ACPI: Se o sistema travar, altere essa opção, é para a gestão de energia do sistema sobre o hardware, aperte ```3 ou A```;
    * 4 -> Safe mode: Se o sistema persistir em travar, mesmo com o ACPI off, coloque este em ```ON``` (Não há muitos detalhes no handbook);
    * 5 -> Single user: Limita a quantidade de usuários a um uúnico para o boot  
    * 6 -> Verbose só libera um maior detalhamento dos command-lines na ação do sistema, aperte o ```6 ou v```;

&nbsp;

___

&nbsp;

### Install BSD

&nbsp;

![freebsdinstaller](img/freebsdinstaller.png)
<center><small>Menu de instalação caso não tenha um BSD já firmado na máquina ou queria instalar um.</small></center>

&nbsp;

Quando usado o instalador do FreeBSD, ele te dá 3 opções, sendo essas:

* ```Install``` ->  Inicia o processo de instalação;
* ```Shell``` -> Abre um Shell para manipular o computador ou fazer operações pré-instalação;
* ```Live CD``` -> Aqui é o famoso modo live, onde você pode usar o sistema de forma experimental, já que o mesmo só está em memória;

&nbsp;

Uma dica do site do handbook BSD é apertar ```s``` nessa tela para abrir um prompt e dar o comando ```more /var/run/dmesg.boot``` para verificar o boot e o hardware detectado.

&nbsp;

___

&nbsp;

### Ctrl+C in install

&nbsp;

![ctrlcscriptbsd](img/ctrlcscriptbsd.png)
<center><small>Olha o Ctrl+C em ação.</small></center>

&nbsp;

Use o usuário ```root``` para entrar no modo live, vale comentar tambem que "ás vezes" ele pede a senha, nesse caso é só dar outro ```Ctrl+C``` e tentar entrar denovo como ```root```, possivelmente irá funcionar, já que forá feitos testes.

&nbsp;

___

&nbsp;

### Agora é o install mesmo

&nbsp;

O menu de instalação da distro freeBSD é chamado de bsdinstall, a primeira parte da instalação é a detecção do tipo de teclado utilizado, Ex:

![freebsdkeymap](img/freebsdkeymap.png)
<center><small>Seleção de teclado.</small></center>

&nbsp;

Aqui você seleciona o teclado para o sistema, neste caso, após a seleção, ele te leva ao ```test keymap``` para confirmar que o teclado está correto.

&nbsp;

##### P.S: Selecione o ```Brazilian (withoud accent keys)``` pois funcionou maioria do meu teclado... bem, depois que ler mais um pouco, mais prafrente eu faço funcionar o ```Alt GR + Q``` para gerar o ```\```.

&nbsp;

Bem, depois de escolher e testar o teclado, caso tenha selecionado o ```default```, será o ``` americado ISO-8859-1```, será a tela de configuração do **hostname**, ai você pode colocar o nome que quiser para identificação do host na sua rede, Ex:

![hostnamebsd](img/hostnamebsd.png)
<center><small>Olha o hostname selecionado... eu sei, nada criativo, más bem, são testes mesmo, então tanto faz.</small></center>

&nbsp;

Agora a coisa fica mais interessante, pois nessa tela temos as opções de instações de pacotes opcionais para o sistema.

![pacotesbsd](img/pacotesbsd.png)
<center><small>Escolha sabiamente</small></center>

&nbsp;

Os pacotes listaos são:
* ```base``` -> Ferramentas básicas de sistema como ```CAT, LS, DIR``` e demais;
* ```Kernel``` -> Kernel e módulos com símbolos de depuração ativados;
* ```Lib32-dpg``` -> Bibliotecas para funcionamento de aplicativos 32bits em sistema 64 com símbolos de depuração ativados;
* ```Lib32``` -> O mesmo que o acima, porém sem a parte de símbolos;
* ```Ports``` -> Coleção de Ports BSD para automatizar download, compilação e instalação de pacotes terceiros, só lembrando que o Ports não verifica espaço em disco durante a instalação, isso é, o mesmo ocupa 500Mb a mais durante a instalação, lembre-se disso caso selecionar essa opção e do seu armazenamento.
* ```src``` -> Código-fonte do BSD para o Kernel e usuário, utilizado por alguns Ports e para o próprio desenvolvimento do BSD, lembrando, ele é utilizado para desenvolvimento e requer 1GB em armazenamento, forá mais 5GB para a recompilação de todo o S.O BSD; 
* ```test``` -> pacotes de teste do BSD;

&nbsp;

Bem, após a seleção dos pacotes, você precisa fazer o download deles para instalar caso tenha optado por manter atualizado ou se você pegou uma versão CD de boot, de qualquer forma será apresentada essa tela.

![redebsd](img/redebsd.png)
<center><small>Olha o aviso de instalação de pacotes via rede.</small></center>

&nbsp;

Ao que se segue agora, é a preferência de rede do BSD para a instalação de pacotes via rede, segue abaixo a configuração da placa de rede para o download dos pacotes.

&nbsp;

##### P.S: Tudo aqui não consta no handbook, sendo assim fui eu que fiz por própria autoria e com base nos meus conhecimentos... espero que de certo

&nbsp;

![placaderedebsd](img/placaderedebsd.png)
<center><small>Selecionar placa de rede.</small></center>
&nbsp;

![ipv4bsd](img/ipv4bsd.png)
<center><small>Decido ou não aceitar o uso do IPV4, esse eu marquei que sim.</small></center>
&nbsp;

![ipv4dhcpbsd](img/ipv4dhcpbsd.png)
<center><small>Aqui eu falo que se quero ele estático ou DHCP... Fui no DHCP para economizar tempo.</small></center>
&nbsp;

![ipv6bsd](img/ipv6bsd.png)
<center><small>Decido ou não aceitar o uso do IPV6, esse eu marquei que não.</small></center>
&nbsp;

![dnsbsd](img/dnsbsd.png)
<center><small>Configuro o DNS que o host vai usar.</small></center>
&nbsp;

![mirrorbsd](img/mirrorbsd.png)
<center><small>Aqui é de onde ele vai baixar os pacotes.</small></center>
&nbsp;

Ufa.... com isso é o fim da configuração do download dos pacotes, há, lembrando, isso aqui é mais para quem quer deixar os pacotes atualizados ou baixou uma versão mais "lite" do FreeBSD por assim dizer.

&nbsp;

Ai, agora é hora de rolo, hora de otimizar ou só taca no automatico e vai.

![formadeinstalarbsd](img/formadeinstalarbsd.png)
<center><small>Aqui é de onde ele vai baixar os pacotes.</small></center>
&nbsp;

Aqui é a configuração de forma de instalação do BSD no armazenamento interno, segue abaixo os tipos de instalação:

* ```Auto``` -> Aqui é a formatação automático via ```UFS``` do sistema de arquivos;
* ```Manual``` -> Aqui é a criação manual das partições para a instalação do S.O;
* ```Shell``` -> Esse abre um Shell para a criação de partições utilizando as ferramentas de sistema, Ex: ```Gpart, Fdisk, BsdLabel``` e outros;
* ```Auto``` -> (ZFS)O particionamento cria um sistema root-on-ZFS com suporte de criptografia GELI opcional para ambientes de inicialização... ***(Esse aqui eu não entendo bem... tenho que dar uma olhada mais fundo)***; 

&nbsp;

___
***Aqui sinceramento eu pulei os demais métodos e fui direto para o modelo Auto de instalação, neste eu selecionei o sistema de arquivos MRB... bem, eu volto mais tarde para tentar realizar a instalação nestes modelos.***
___

&nbsp;

![instalandopacotesbsd](img/instalandopacotesbsd.png)
<center><small>Aqui é o download dos pacotes externos que foram selecionados no opcionais.</small></center>

&nbsp;

![instalandoosistemabsd](img/instalandoosistemabsd.png)
<center><small>Aqui é a instalação dos pacotes do sistema em si.</small></center>

&nbsp;

Bem, bem, depois de tudo, agora é hora de dar uma senha ao ```root``` ao sistema.

&nbsp;

![timezonebsd](img/timezonebsd.png)
<center><small>Aqui você seleciona o time-zone do sistema, no caso, aqui foi de américas, Brasil e agora a seleção do estado.</small></center>

&nbsp;

Depois de selecionar o time-zone, agora você tem que selecionar os serviços que serão iniciados durante o boot.

![servicesbsd](img/servicesbsd.png)
<center><small>Esses são os serviços default da instalação do BSD... aqui tem que escolher oque será iniciado junto ao sistema.</small></center>

&nbsp;

___

### Shutdown

Para o desligamento do sistema BSD, é feito os seguintes passos:

* Comandos de desligar ou reiniciar o sistema requisitarão o shell ```/etc/rc.shutdown```;
* Após acionar o shell, todos os processos receberam um sinal de ```TERM```, aqueles que não responderem em tempo hábil, receberam um ```KILL```;

Para o desligamento do sistema em arquiteturas que suportam o controle de ACPI, é necessário os comandos:

```
shutdown -p now
init 0
halt -p
```

Para reiniciar o sistema use:

```
shutdown -h now
reboot
halt -q
```

Lembrando somente os membros do grupo ```operator``` ou o próprio ```root``` tem capacidad de reiniciar ou desligar.

___

### Compilar um PORT

Para compilar uma porta, você simplesmente muda para o diretório do programa que deseja instalar, digite make installe deixe o sistema fazer o resto. 

___

### Agradecimentos

Há, aqui vai coisa ainda para ser feita, más agradeço a própria documentação do BSD e todos os sites buscados durante o desenvolvimento deste mini-manual. 

___
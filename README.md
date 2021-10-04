## FreeBSD -> Resumo geral
### Aquele manual básico para firmar estudos

&nbsp;

___
&nbsp;


### Introdução

Manual simples e resumido sobre o FreeBSD feita com base na documentação do FreeBSD, dispónivel neste endereço: https://docs.freebsd.org/en/books/handbook/, forá demais pesquisas feitas com o intuito de melhorar este documento.

&nbsp;

___

&nbsp;

### P.S

Qualquer contribuição ao manual é bem vinda, se conter erros e demais coisas, fique a vontade para mexer, isso ajuda a comunidade como um todo.

&nbsp;

___

&nbsp;

### Curiosidades interessantes 

* Totalmente free -> Licença BSD -> Sua licença é totalmente aberta, isso é, pode usar para qualquer coisa e pode ser trancado caso aquele que fez o fork queira.
* A primeira versão do FreeBSD foi a 1.0 em 1993, depois de problemas de código com a Novell, em 1994, grande parte do código interno foi alterado para de própria autoria do projeto, levando a versão 2.0 que possuia a versão Lite por não estar completo até data de lançamento.
* A equipe do BSD além de fechar a distribuição do BSD com uma fabricante de Discos CD em 1993, recebeu a oportunidade de possuir um computador com internet para a disponibilização do projeto.
* Possibilita o porte para o sistema ARM, exemplo o raspberry.
* O FreeBSD vem com o usuário ```root``` sem senha, já configurado no sistema, mesmo em modo live.

&nbsp;

___

&nbsp;

### Hardware

* Compátivel com processadores AMD64, X86 e ARM;
* Necessidade de mémória vária do uso do equipamento com a distro, porém é recomendo o minimo de 96MB de memória (pessoalmente, 1GB de memória é o suficiente para testes);
* Espaço de armazenamento mínimo é 2GB interno;

&nbsp;

___

&nbsp;

### Tipos de instaladores

* Installer Images -> Imagens de instaldores do FreeBSD.
* Virtual Machine Images -> Imagens prontas para máquinas virtuais.
* SD Card Images -> Imagens para cartão SD, possívelmente estruturas ARM em maioria.

&nbsp;

___

&nbsp;

### Dicas para criar uma mídia de boot 
###### P.S: Totalmente pessoal esse ponto

&nbsp;

Particularmente utilizo o Etcher Balena e o Rufus, ambos me atendendo super bem, para o caso de já estar utilizando alguma distro Linux, é possível usar o comando ```dd``` para gerar o disco bootavel externo ou mesmo o Etcher, se está utilizando o Windows, recomendo o uso do Rufus, segue abaixo os Links para o download dos arquivos e do sistema operacional:

* Rufus: https://rufus.ie/pt_BR/
* Etcher: https://www.balena.io/etcher/
* FreeBSD: https://www.freebsd.org/where/

Exemplo fornecido pelo próprio site do FreeBSD Documentation do uso do DD:

```
dd if=Image-FreeBSD-*.img of=/dev/da0 bs=1M conv=sync
```

###### P.S: Recomendo que esteja ciente dos trechos acima antes de realizar a criação (Para não perder tempo) da mídia, forá que se for instalar em alguma máquina, lembre-se de realizar o BK na mesma caso necessário.

&nbsp;

___

&nbsp;

### Sistemas de arquivos compátiveis

* MBR (Master boot record) -> 4 partições primárias máximas, porém pode se converter em partições lógicas, somente necessitando de uma partição primária para o sistema;
* GPT (GUID Partition Table / Tabela de partição GUID) -> Possui até 128 partições, eliminando a necessidade de partições lógicas como a MBR

&nbsp;

___

&nbsp;

### BIOS

Bom lembrar que existem dois tipos de BIOS utilizadas atualmente, a legancy e a UEFI, sendo a primeira a mais antiga e genérica e a segunda uma versão bolatada entre da Microsoft e a Intel que se espalhou para demais fabricantes e hardwares.

&nbsp;

___

&nbsp;

### Entrando no BSD

&nbsp;
___

&nbsp;


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

### Esc and Ctrl+C in install

&nbsp;

![ctrlcscriptbsd](img/ctrlcscriptbsd.png)
<center><small>Olha um Esc ou Ctrl+C em ação.</small></center>

&nbsp;

Use o usuário ```root``` para entrar no modo live, vale comentar tambem que "ás vezes" ele pede a senha, nesse caso é só dar outro ```Esc ou Ctrl+C``` e tentar entrar denovo como ```root```, possivelmente irá funcionar, já que forá feitos testes.



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

###### P.S: Selecione o ```Brazilian (withoud accent keys)``` pois funcionou maioria do meu teclado... bem, depois que ler mais um pouco, mais prafrente eu faço funcionar o ```Alt GR + Q``` para gerar o ```\```.

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

Há, existe uma parte do handbook sobre configuração da rede do BSD, porém, durante esse manual, BSD foi instalado em um virtualbox e está usando uma placa de rede NAT, então deixei a config mais simples... 

&nbsp;

##### P.S: volto a melhorar essa parte depois com mais testes.

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

Abaixo segue a instalação dos pacotes opcionais e do sistema.


###### P.S: Antes de continuar, deixo avisado para eu não ser julgado, somente é por convivencia com discos HD..., Não tenho contato, nem mesmo conheco alguém do ramo, más não importa para quem tu reza ou se nem reza, tenha um SSD no seu hardware para ganhar tempo de vida.

&nbsp;

![instalandopacotesbsd](img/instalandopacotesbsd.png)
<center><small>Aqui é o download dos pacotes externos que foram selecionados no opcionais.</small></center>

&nbsp;

Primeiramente... Depois de você ter criado a partição, agora elas seram utilizadas primeiramente para a criação do sistema de arquivos, em seguida o download dos pacotes opcionais, sendo que, se a instalação for do tipo DVD, todos os opcionais já vão estar dentro do disco, se não, exemplos os ```bootonly media, CD, mini memstick e demais```, ele precisa fazer o download dos pacotes, por isso a seleção do Mirror antecipadamente foi útil.... OK, em resumo sobre isso, ele confere a lista selecionada, baixa os pacotes opcionais, confere se os mesmos não estam corrompidos e seguidamente os passa ao instalador do sistema.

&nbsp;

![instalandoosistemabsd](img/instalandoosistemabsd.png)
<center><small>Aqui é a instalação dos pacotes do sistema em si.</small></center>

&nbsp;

Como dito, os pacotes opcionais são obtidos e deixados para serem instalados por esse processo de extração.

###### P.S: Como comentando no handbook, o tempo de instalação vária muito, quantidade de pacotes, velocidade de internet se você precisar dela para baixar pacotes, o hardware em si, como quantidade de memória, CPU e principalmente o armazenamento

&nbsp;

Bem, bem, depois do processo de extração, será requisitada a criação de senha para o literal usuário mais importante do sistema, o ```root```, neste caso, peço só que lembre da senha... sério, se não depois passa um apertado para pegar a senha devolta ou descobrir a mesma.

&nbsp;

![timezonebsd](img/timezonebsd.png)
<center><small>Aqui você seleciona o time-zone do sistema, no caso, aqui foi de américas, Brasil e agora a seleção do estado.</small></center>

&nbsp;

Depois de selecionar o time-zone, vem uma tela para configurar os horários locais... ai vai de você no caso, só acertar o relógio ou selecionar o ```skip```.

###### P.S: Recomendo configurar corretamente o horário para não ter problemas a acesso de pacotes externos.

&nbsp;

![servicesbsd](img/servicesbsd.png)
<center><small>Esses são os serviços default da instalação do BSD... aqui tem que escolher oque será iniciado junto ao sistema.</small></center>

&nbsp;

Depois de tudo isso, vem agora você tem que selecionar os serviços que serão iniciados durante o boot, todos esses serviços são opcionais, não necessários para o funcionamento do sistema, esse é outro ponto para deixar no automático ou personalizar, ai vai da necessidade de cada um.

&nbsp;

Más bem, segue abaixo um pouco de detalhamento dos serviços:

* ```local``` -> Ative o serviço de DNS local, vale comentar que esse é somente para o host e não valido a toda a rede, caso seja esse o seu objetivo, é recomendado instalar o resolvedor DNS, no caso, esse: ```dns/unbound```.
* ```sshd``` -> Habilita o SSH (daemon Secure Shell), que possibilita um acesso remoto criptografado ao host.
* ```moused``` -> Serviço de mouse para o console do sistema;
* ```ntpdate``` -> Habilite um serviço de NTP para sincronizar o relógio do host durante o boot.
* ```ntpd``` -> Habilita o NTP para buscar de servidores do mesmo para a sincronização do relógio do host;
* ```powerd``` -> Serviço para controle de energia do hardware caso o mesmo permita ou tenha esse controle, serve para ajustar frequência do CPU e demais outras peças;
* ```dumpdev``` -> Habilita os despejos de memória, isso é, limpar a memória de coisas que deram problemas e demais;

&nbsp;

![segurancabsd](img/segurancabsd.png)
<center><small>Esses são os serviços default da instalação do BSD... aqui tem que escolher oque será iniciado junto ao sistema.</small></center>

&nbsp;

Ok, depois de selecionar os serviços, ta na hora de escolher o sistema de segurança do BSD, que comecem os jogos:

* ```hide_uids``` -> Oculta UID de processos em execução para usuários sem permissão;
* ```hide_gids``` -> Oculta processos em execução pertencendos a outros grupos;
* ```hide_jail``` -> Oculta processos em execução nas ```jail's``` para usuários sem permissão;
* ```read_msgbuf``` -> Retira a permissão de leitura do buffer de mensagem do kernel para usuários sem privilégios, basicamente desativa o dmesg para alguns usuários e tira a permissão de leitura dos arquivos que contém essas infos;
* ```proc_debug``` -> Desabilitar possibilidade de depuração dos processo para usuários sem privilégios, basicamente quase todos os processo do sistema e demais linguagens ficam desabilitados o depurador para esse usuário;
* ```random_pid``` -> Randomize o PID de processos recém-criados.
* ```clear_tmp``` -> Limpa o diretorio ```/tmp``` quando o sistema da boot;
* ```disable_syslogd``` -> Desative a abertura do soquete da rede syslogd, claro, existe mais detalhes, porém tem que confirmar na configuração personalizada do BSD sobre o serviço;
* ```disable_sendmail``` -> Desative o agente de transporte de correio sendmail;
* ```secure_console``` -> Quando esta opção é ativada, o prompt solicita a senha de ```root``` para entrar no modo de usuário único.
* ```disable_ddtrace``` -> O DTrace pode ser executado de forma destrutiva para o kernel em execução, para mais detalhes, tem que conferir a funcionabilidade do programa e seus parâmetros.

&nbsp;

Ótimo, depois de todos esses passos, chegamos ao final, que é adicionar um usuário ao BSD sem ser o ```root```, para isso, selecione o ```yes``` na tela de adicionar mais um usuário ao sistema, se selecionar o ```no```, pronto, o sistema irá terminar o processo de instalação, aplicar as alterações e fechou, um BSD totalmente instalado.

Agora, esse é um usuário já criado no BSD, Ex:

![usuariobsd](img/usuariobsd.png)
<center><small>Esse usuário é bem default, sem qualquer customização, forá a senha.</small></center>

&nbsp;

As informações do usuário são:

* ```Username``` -> Nome do usuário, boas práticas para isso são:
    * Sem espaçamento;
    * Sem caracteres especiáis;
    * O sistema é case-sensitive, então o mesmo diferença de maiúsculo de minúsculo;
    * Todo nome de usuário deve ser único;
* ```Full name``` -> Nome completo do usuário, aqui é um campo de descrição, então pode digitar sem medo dos descritos acima;
* ```Uid``` -> ID do usuário e esse é normamente deixado por conta do sistema, a mesmo que você saiba quais ID's ainda estão disponíveis;
* ```Login group``` -> O grupo que o usuário irá pertencer e aqui também é normal deixar em branco, poiso grupo se torna o nome do usuário.
* ```Invite user into other groups?``` -> Grupos adicionais, isso é, grupos a qual o usuário pode pertencer, como grupos que tem permissões especiais e demais;
    * Se o usuário precisar de ```root```, digite: ```wheel``` neste campo;
* ```Login class``` -> Normalmente deixado em branco para o padrão ***(Sinceramente não sei nem oq é, tenho que ver isso depois)***;
* ```Shell```-> Seleciona qual shell o usuário utilizará por padrão;
* ```Home directory``` -> O diretório do ```\home``` do usuário, normalmente, o default já preenche corretamente;
* ```Home directory permissions``` -> Permissões no diretório ```\home``` do usuário.
* ```Use password-based authentication?``` -> Aqui pergunta se o usuário quer usar o password para entrar no usuário;
* ```Use an empty password?``` -> Aqui decide se o usuário vai usar uma senha ou se será um campo em branco, é melhor colocar uma, afinal, você não vai usar um BSD para acessar email do google né;
* ```Use a random password?``` -> Favor usar o ```no``` aqui, se gerar uma senha aleatória e você esquecer... bem, espero que saiba onde fica armazenado as senhas do sistema;
* ```Enter password``` -> Aqui você digita uma senha para o usuário;
* ```Enter password again``` -> Agora você repete aquela mesma senha aqui para efetivar a senha do usuário;
* ```Lock out the account after creation?``` -> Por default é um ````no```, pois ai o usuário fica trancado e não pode acessar;


&nbsp;

Agora, depois de tudo isso, é só dar um ```OK``` para finalizar a criação do usuário... Ufa, cabou , bem, nem tanto, depois que você terminar de criar o usuário aparecerá uma pergunta para adicionar um novo outro usuário ou não, nesse caso, ai vai de sua vontade ou necessidade.

&nbsp;

Por fim, agora que foi feito tudo o de neessário, aparecerá essa tela:

![teladetodasopcoesbsd](img/teladetodasopcoesbsd.png)
<center><small>Tela para efetivar tudo e sair, ou alterar alguma coisa antes de aplicar.</small></center>

&nbsp;

Como dito na descrição da imagem, aqui é possível alterar as configurações antes de aplicar e finalizar totalmente a instalação do sistema.

Com isso está terminado a parte da instalação do sistema BSD, para finalizar, aperte a opção do ```EXIT``` e pronto... más e os demais? ... Bem, eles já foram vistos de forma seguida, más para deixar de forma mais didática, eles são:

* ```Add User``` -> Adicionar usuários.
* ```Root Password``` -> Definição da senha do ```root```.
* ```Hostname``` -> Definir o nome do host.
* ```Network``` -> Configurações da's interface's de Rede .
* ```Services``` -> Ativação de serviços .
* ```System Hardening``` -> Opções de segurança de proteção .
* ```Time Zone```-> Definição do fuso horário .
* ```Handbook``` -> Baixe e instale o Manual do FreeBSD.

&nbsp;

___

&nbsp;

### Problemas durante a instalação

Segundo o pessoal do handbook e como comentado anteriormente, o BSD vem com o ACPI ligado, isso é, gerenciamento de energia inteligente ao hardware, porém tem BIOS ou Firmware's de placas mãe's que ainda são incompátiveis ou apresentão problemas, dessa forma é recomendado fazer:

* Desabilitar nas opçõe savançadas durante a instalação;
* Digitar em modo shell o comando: ```set hint.acpi.0.disabled="1"``` para desabilitar a opção;
* Ou por fim, alterar o arquivo ```/boot/loader.conf``` adicionando a linha ```hint.acpi.0.disabled="1"``` ao mesmo e recarregando o arquivo no sistema de instalação;

&nbsp;

___

&nbsp;

### Primeiro login

```
FreeBSD/amd64 (teste_freebsd) (ttyv0)

login:
```

Depois de toda a tela de verbose após iniciar o sistema que é exatamente igual a tela de bootinstall, o sistema para na tela de login entrando as informações de:

* Versão: amd64;
* Hostname: teste_freebsd;
* Console virtual: ttyv0;

O login é a entrada de usuários que foram registrados durante a instalação, com exemplos desses podemos logar no ````root``` e no ```teste``` criados durante a instalação da versão em uso.

Após o login, uma mensagem será printada no terminal console, sendo essa o ```MOTD```, que entrada várias informações, Ex:

![modtbsd](img/modtbsd.png)
<center><small>MOTD BSD após o login no usuário root.</small></center>

Para editar esse ```MODT```, é necessário ter as permissões necessárias para editar o arquivo que fica no ```/etc/motd```.

&nbsp;

___

&nbsp;

### Consoles virtuais

&nbsp;

Isso é algo comum, normalmente só utilizamos um único terminal por ver, isso é, um único console por ver, cada console é nomeado de ```ttyv*```, indo de 0 a 8, podendo ser alterado com o uso dos comandos ```Alt+F*``` de 1 a 8.

O local onde fica as configurações de consoles virtuais é no ```/etc/ttys```.

Dentro do arquivo de configuração dos ttys, é bom orientar que:

* Não comente a linha ```ttyv0```, afinal é o default;
* O ```ttyv8``` é normalmente utilizado pelos programas que geram interfaces gráficas, no caso o Xorg.


Veja a imagem abaixo para você ter uma idéia da configuração dos consoles virtuais.

&nbsp;

![ttysbsd](img/ttysbsd.png)
<center><small>Configuração dos TTYSV do BSD.</small></center>

&nbsp;

___

&nbsp;

### Boot single user

&nbsp;

Lembra que foi comentado sobre o boot de usuário unico era para reparar o sistema operacional, sabe, lá no inicio.... bem, é isso mesmo, más olha a sacada, dentro desse modo, o unico usuário disponivel é o ```root``` e sem senha... sentiu o medo né, tipo e um acesso remoto... sem senha com o usuário com maior permissão dentro do sistema... vai dar ruim né!? Nops, olha o pq.

Esse modo abre o terminal com o usuário ```root``` sem senha, porém bloqueia acesso externo a rede, necessitando de interação física ao equipamento para o exercicio da tarefa, sendo assim, você pode manipular o sistema totalmente, porém tem que ter acesso ao mesmo, forá que esse modo além de ser usado para reparação, é usado também para redefinir a senha do ```root``` caso a mesmo tenha sido perdida.

Para ficar ciente, quando você faz um boot de single user, os ttyv são a base para o acesso, seguindo a mesma regra, onde o default é o ```ttyv0```, o fato de você acessar o mesmo sem precisar da senha é porque ele está com o ```secure``` afirmado no fim da linha, isso é, se estiver ```insecure```, mesmo em modo single user, será necessário colocar a senha do usuário ```root``` para ter acesso e isso leva o perigo que, se você esta entrando nesse modo para recuperar a senha de root perdido... bem, vai dar não, entao sempre tenha cuidado e zelo pelas senhas utilizadas nos sistemas e aplicações.

&nbsp;

___

&nbsp;

### Configuração de vídeo


&nbsp;

___

&nbsp;

### Contas e usuários

Primeiramente, existem que tipos de contas dentro do sistema BSD? Segue abaixo uma lista dos tipos:

* ```daemon```;
* ```operator```;
* ```bind```;
* ```news```;
* ```www```;
* ```nobody```;

Forá demais outras, os litados são um exemplo, cada tipo de conta tem um limite de agir dentro do sistema, sendo assim, cada um tem um nível de prioridade, vamos supor que o ```nobody``` é o tipo predominante dentro do sistema e esse grupo for comprometido de alguma forma, bem, isso vai gerar uma grande perda, já que todos os arquivo deste mesmo tipo estão igualmente comprometidos.

Vale tambem comentar que a ```nobody``` é a conta genérica do sistema e que não possiu privilégios.

&nbsp;

___

&nbsp;

### Estrutura de Diretório

&nbsp;

Segue abaixo uma tabela com o esquema de diretórios do sistema FreeBSD, lembrando que o diretório principal é a raiz do sistema, o ```/```.

| Diretório | Descrição | 
|---|---|
|/| Raiz do sistema|
|/bin||
|/boot||
|/boot/defaults||
|/dev||
|/etc||
|/etc/defaults||
|/etc/mail||
|/etc/periodic||
|/etc/ppp||
|/mnt||
|/proc||
|/rescue||
|/root||
|/sbin||
|/tmp||
|/usr||
|/usr/bin||
|/usr/include||
|/usr/lib||
|/usr/libdata||
|/usr/libexec||
|/usr/local||
|/usr/obj||
|/usr/ports||
|/usr/sbin||
|/usr/share||
|/usr/src||
|/var||
|/var/log||
|/var/mail||
|/var/spool||
|/var/tmp||
|/var/yp||

&nbsp;

![raizbsd](img/raizbsd.png)
<center><small>Toda a raiz simples de um BSD sem customizações.</small></center>

&nbsp;

___

&nbsp;

### Shutdown

&nbsp;

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

### Controle de usuários

___

### Agradecimentos

Há, aqui vai coisa ainda para ser feita, más agradeço a própria documentação do BSD e todos os sites buscados durante o desenvolvimento deste mini-manual. 

___
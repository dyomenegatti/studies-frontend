# Arquitetura de computadores: Por trás de como seu programa funciona

## Anotações

* Todo computador possuir fios que enviam e recebem energia, quando energizado ele entende como ligado ou 1, quando não energizado ele entende como desligado ou 0. Todos esses _1s_ e _0s_ são chamados de **bit**, que vem do inglês _BInary Digit_ ou _Digito Binário_. - menor unidade possível para o armazenamento de informações. 
* Como um bit é uma unidade muito pequena, costuma-se trabalhar com grupos de 8 bits, essa quantidade agrupada é chama de _byte_. Por convenção, quando medimos o armazenamento de um computador usamos o byte. 
* Para representar essas undiades, utilizamos o b (minúsculo) para o bit e o B (maiúsculo) para byte.
* Geralmente encontrado essas unidades em conjunto com prefixos SI como _k_ (kilo ou mil), _M_ (mega ou milhão), _G_ (giga ou bilhão) e assim por diante. Por exemplo:
  * Um arquivo de 200MB é um arquivo com 200 milhões de bytes.


* Nós entendemos (e escrevemos) um cógio fonte que se transforma (através do tradutor) em código de máquina, assim é possível que o computador entenda o código fonte. 
* Compiladores x Interpretadores
  * _Compiladores_: execução rápida, verifica erros antes de executar, tempo extra para execução, executa em uma máquina valorizando a performance.
    * C, Go, Rust...
  * _Interpretadores_: execução lenta, só verifica erros ao executar, começa a executar na mes ahora, executa em diferentes máquinas valorizando o processo de desevolvimento.
    * JS, Python, PHP, Ruby...
  * Uma mesma linguagem pode ter os dois (compilador e interpretador)

* _Just In Time Compilation = JIT COMPILATION = Compilação na hora certa_
  * _HD - Hard Disk_ - Disco Rígido: grande capacidade, barato, lento e frágil.
  * _SSD - Solid State Driver_ - Unidade de Estado Sólido: menor, mais rápido, resistente, caro e limitação de escrita.
  * Ambas são memórias secundárias, onde o computador não trabalha diretamente com eles.
* _Memória RAM - Random Access Memory_ - Memória de Acesso Aleatório
* No SSD ou Disco Rígido é onde são armazenados informações sobre o sistema operacional do computador e permite utilizá-lo no dia a dia. Mesmo assim, no momento que o computador liga, como ele vai saber quais informações estão conectadas? Esse dado inicial é cricual e é localizado na _memória ROM - Read-Only-Memory_ ou Memória Apenas de Leitura - memória não volátil com baixo armazenamento, bem diferente da RAM ou HD/SSD.


* _CPU - Central Process Unit_ ou Unidade Central de Processamento (processador) 
  * Recebe as instruções na RAM e tenta executa-las.
  * Dividida em:
    * _UC - Unidade de Controle_: recebe e coordena as instruções da RAM;
    * _ULA - Unidade Lógica Aritmética_: executa e manipula os dados, realiza operações aritméticas; 
    * _regist_: é a memória do processador, guarda a instrução real, a posição da memória que está lendo, valores intermediários;
  * Instruções de execução de um código no processador:
    * _Buscar (fetch)_: processador olha pra memória RAM e busca a instrução que ele tem que executar, guarda no registrador - como o processador sabe qual instrução pegar? Por causa do contador que registra a posição atual da memória. 
    * _Decodificar_: manda para a unidade de controle e configura o processador para poder executar a ação;
    * _Executar_: pega o resultado da ação e envia para o acumulador; 
    * Para sincronizar essas instruções é utilizado o _clock_ que faz os tic tac para monitorar a velocidade que as instruções ocorrem, isso é considerado como GHz do processador -> 3GHz = 3 bilhões de tiques por segundo.
      * O clock define a velocidade com que as instruções são executadas. Quanto maior a velocidade do clock, mais rápido um programa será executado.

* Dispositivos de entrada e saída
  *  Entrada: teclado, mouse, webcam, microfone
  *  Saída: Tela, fone, impressora

* _Memória cache_ é uma técnica muito importante para otimizar o funcionamento do processador e é cada vez mais explorada atualmente. Mesmo assim, essa não é uma ideia limitada aos componentes do processador mas é usada em quase todas as comunicações de dados atualmente. Alguns lugares comuns são:
* _Cache em navegadores_:
  * Ao acessar uma página pelo navegador, é necessário se comunicar com servidores pela internet e esperar todo o conteúdo da página ser transferido para o seu computador. Como as páginas não costumam ser alteradas com frequência, os navegadores costumam guardar esses dados dentro do próprio computador. Dessa forma, a próxima vez que for acessar a página, será mais rápida.
* _Cache em banco de dados_:
  * Alguns sistemas usam estruturas chamadas de banco de dados. Elas são formas de guardar e estruturar uma grande quantidade de informação no HD/SSD. Porém, algumas pesquisas nessa estrutura podem não ser tão rápidas e seria interessante guardar valores muito pedidos para acelerar as respostas. 
  * Por isso, muitos bancos de dados utilizam uma estrutura de dados rápida (muitas vezes em memória RAM) para guardar essas respostas, como o memcached e o redis. 
* _Cache em servidores_:
  * Muitas vezes, alguns serviços de um servidor podem ser bem mais requisitados que outros. Por exemplo, uma página inicial de um site de computadores que mostra todos os  produtos em desconto naquele dia. Desssa forma, para acelerar a resposta e diminuir a carga nas máquinas, esses equipamentos podem guardar versões prontas dessas páginas durante um período de tempo. Assim, sempre que uma pessoa pedir a página para o servidor, ele não precisará buscar no banco de dados nem fazer um processamento complexo paraa devolver a resposta. 
  * Esse processo é normalmente feito em conjunto com uma Content Delivery Network (CDN) ou Rede de Distribuição de conteúdo. Elas basicamente distribuem cópias das suas mídias para diversos servidores para que o dado esteja o mais próximo possível de você.

* _Hierarquia de memória_
  * Registradores (1 ciclo de clock ~500b) > cache L1 (700GB/s - 64kb) > cache L2(200GB/s - 500kb) > cache L3(150GB/s - 4mb) > RAM(10GB/s - 8GB) > SSD(2GB/s - 500GB) > HD(200MB/s - 4TB) > Cloud(2MB/s - PB ou EB)
  * Quanto mais sobe - mais velocidade. Quanto mais desce - mais capacidade de carga. 
* Princípio da localidade 
   * Localidade temporal- acessar de novo em breve
   * Localidade espacial- acessar vizinho em breve
* Porque precisamos desses vários tipos de memórias?
  * Como o princípio da localidade diz que nós usamos a mesma porção de dados durante um período de tempo, é importante ter memórias rápidas para poucos dados e lentar para muitos dados. 
  * Memórias rápidas são muito caras, então não é viável usá-las para armazenar uma grande quantidade de dados.

* _Processador de 32 ou 64 bits_
  * Tamanho de informação que pode ser processada na CPU em um ciclo de clock 
  * Processador de 64 bits tem mais performance (processa mais de uma só vez, otimizações mais complexas) e memória 

* UTF-8 representa vários caracteres do sistema unicode, mas essa não é a única codificação para isso. Existem outros dois sistemas UTF-16 e UTF-32.
  * _UTF-8_: Representa os caracteres em pedaços de 8 bits e sua grande vantagem é manter os textos codificados apenas em ASCII (a grande maioria da web no passado) intactos. Ele tem um tamanho variável e cada caractere pode ocupar 8,16 ,24 ou 32 bits. É a mais comum na web atualmente. 
  * _UTF-16_: representa os caracteres em pedaços de 16 bits. Isso significa que a codificação não é mais compatível com ASCII e ocupa o dobro de memória em textos que possuem apenas caracteres da língua inglesa. Ele tem um tamanho variável e cada caractere pode ocupar 16 ou 32 bits. Sua grande vantagem é ocupar menos espaço quando o texto possui muitos caracteres asiáticos. Codificação usaa em sistemas windows
  * _UTF-32_: representa os caracteres em pedaços de 32 bits. Ela não é compatível com ASCII e ocupa 4 vezes mais espaço em textos que só utilizavam ASCII. Mesmo assim, diferentemente do UTF-8 e UTF-16, essa codificação tem um tamanho fixo e essa é sua grande vantagem. Como cada caractere ocupa a mesma quantidade de bits, é fácil em qual posição cada caractere está em um texto.
  
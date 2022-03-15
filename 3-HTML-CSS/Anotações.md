# Criar suas primeiras páginas web

## Anotações

1. **ARTIGO: HTML, CSS E JAVASCRIPT, QUAIS AS DIFERENÇAS?**

  * Tim Berners-Lee criou o HTML em 1991;
  * A linguagem de marcação foi desenvolvida para possibilitar o compartilhamento de documentos de forma mais prática;
  * O CSS foi desenvolvida como consequência do crescimento do HTML, possibilitando que as páginas criadas ficassem mais estilosas e de forma separada da estrutura do HTML, tudo isso ocorreu em 1995;
  * A partir de uns anos, a Netscape deu inicio a um projeto de implementar uma linguagem nos servidores web da empresa. Ao descobrir isso a Microsoft não perdeu tempo e começou a desenvolver uma linguagem JScript para a mesma utilidade. Ao perceber a cópia do projeto, a Netscape decidiu desenvolver uma tecnologia para o lado do cliente, no mesmo momento a Microsoft descobriu e iniciou a mesma ideia de projeto. Até que existiam duas tecnologias "client-side" e para padronizar o JavaScript a Netscape enviou para a empresa ECMA, permitindo a incorporação à maioria dos navegadores, daí surgiu a ECMAscript.

  * **HTML** - _Hyper Text Markup ou Linguagem de Marcação de Hipertexto_
    * Utilizado para criar toda a estrutura da página web, o cabeçalho, título, imagens entre outros - a partir das tags (etiquetas) sinalizando cada elemento e onde ele se encontra.
  * **CSS** - _Cascading Style Sheet ou Folha de Estilos em Cascata_
    * É uma linguagem de estilo responsável por separar a parte estrutura da página, da parte estética.
    * É possível usar mais de um arquivo CSS ao mesmo tempo, daí o nome "cascata", isso permite várias interações diferentes. 
    * O seletor é o elemento que será utilizado (podendo ser uma tag, classe, identificador...), a propriedade será o que iremos alterar e o valor será de fato a alteração.
    ´´´
      seletor { 
        proprietario: valor;
      }
    ´´´
  * **JAVASCRIPT**
    * A única linguagem de programação das três tecnologias.
    * Responsável por adicionar funcionalidades dinâmicas na página, além de permitir o processamento e transformação de dados enviados e recebidos.
  
  * O papel de cada uma:
    * **HTML**: linguagem de marcação utilizada para estrutura os elementos da página;
    * **CSS**: linguagem de estilos utilizada para definir cores, fontes, tamanhos entre outros;
    * **JAVASCRIPT**: linguagem de programação utilizada para deixar a página web dinâmica;

2. **CURSO: HTML5 e CSS3 parte 1: A PRIMEIRA PÁGINA DA WEB**
  
  * **CSS**
    * Cores Hexadecimais
      * RGB - Red Green Blue 
        * Representação: # R R G G B B
        * 0 - ausência de cor
        * F - máximo de cor
          * **Exemplo**: Cor preta #000000 / Cor branca: #FFFFFF / Cor vermelha: #FF0000
    * Dicionário RGB:
      * 0 ao 255
        * Representação: rgb(R, G, B)
        * 0 - ausência de cor
        * 255 - máximo de cor
          * **Exemplo**: Cor branca: rgb(255, 255, 255) / Cor azul: rgb(0,0,255)
    * Estilizando com CSS
      * **Inline**: dentro da tag que você quer utilizar
        ```
          <p style="font-size: 20px;">Exemplo de parágrafo.</p>
        ```
      * **Interno**: dentro da head do html
        ```
          <style>
            p {
              text-align: center;
            }
          </style>
        ```
      * **Externo**: arquivo separado nomeado como style.css (ou o nome desejado) 
        ```
          //Primeiro no head do html chama o arquivo do css
          <link rel="stylesheet" href="style.css">

          //Depois no arquivo style.css você cria as estilizações
          body {
            background-color: #CCCCCC;
          }
        ```
    * Identificar tag no HTML
      * **Classe**: Marcar itens que podem ser repetidos
        * Representa com o . 
          ```
            //No HTML
            <p class="missao"></p>

            //No CSS
            .missao { 
              color: red;
            }
          ```
      * **ID**: Marcar itens únicos
        * Representa com o #
          ```
            //No HTML
            <p id="missao"></p>

            //No CSS
            #missao { 
              color: red;
            }
          ```
    * Dimensões
      * **Largura**: width 
        * Dado em % ou px
      * **Altura**: height 
        * Dado em px
      * **Espaçamento Interno**: padding 
        * Dado em px
        * Possui as propriedades: left, right, top ou bottom
      * **Espaçamento Externo**: margin 
        * Dado em px
        * Possui as propriedades: left, right, top ou bottom
    * Listas
      * **ul**: Sem ordem
      * **ol**: Ordenadas 
    * Inline e Block
      * **Inline**: Permite alterar os espaçamentos: margin-left, margin-right, padding-left e padding-right
      * **Block**: Bloqueia todas as modificações possíveis.
      * **Inline e Block**: Permite alterar espaçamentos, altura e largura: margin, padding, height e width.
  
3. **CURSO: HTML5 e CSS3 parte 2: POSICIONAMENTO, LISTAS E NAVEGAÇÃO**

  * **HTML**
    * Tags semânticas
      * Deixa o código mais legível, tanto para os devs, quanto para o navegador - fazem com o que o navegador entenda melhor o conteúdo, e com isso carregue melhor a página. 
        * **Header**: Representa o cabeçalho do documento.
        * **Section**: Representa uma seção dentro do documento e geralmente contém um título, pode ser utilizado, por exemplo, para descrever as seções/tópicos de um documento. 
        * **Article**: Representa o conteúdo que não precisa de outro para fazer sentido no documento HTML, por exemplo, um artigo em um blog.
        * **Nav**: Representar um agrupamento de links de navegação, que, por sua vez, são criados com os elementos _ul_, _li_ e _a_.
        * **Aside**: Representa um conteúdo de apoio/adicional ao conteúdo principal. 
        * **Main**: Representa o conteúdo principal e, consequentemente, de maior relevância dentro da página. 
        * **Figure**: É uma marcação de uso específico para a inserção de uma figura. Para incluir a descrição dessa figura, pode ser utilizado o elemento _figcaption_.
        * **Footer**: Representa um rodapé de um documento, como a área presente no final de uma página web. 
  
  * **CSS**
    * Position
      * **Static**: São posicionados estáticos por padrão. Os elementos posicionados estáticos não são afetados pelas propriedades superior, inferior, esquerda e direita. Ele não será posicionado de nenhuma maneira especial, na verdade ele está sempre posicionado de acordo com o fluxo normal da página. 
        ```
          div {
            position: static;
          }
        ```
      * **Relative**: Está posicionado em relação à sua posição normal. Definindo as propriedades superior, direita, inferior e esquerda de um elemento relativamente posicionado fará com que ele seja ajustado para longe de sua posição normal. Outro conteúdo não será ajustado para caber em qualquer lacuna deixada pelo elemento. 
      ```
        div {
          position: relative;
        }
      ```
      * **Fixed**: É posicionado em relação à janela de visualização, o que significa que ele sempre permanece no mesmo lugar, mesmo se a página for rolada. As propriedades superior, direita, inferior e esquerda são usadas para posicionar o elemento. Um elemento fixo não deixa uma lacuna na página onde normalmente estaria localizado.
      ```
        div {
          position: fixed;
        }
      ```
      * **Absolute**: É posicionado em relação ao ancestral posicionado mais próximo (em vez de posicionado em relação à janela de visualização, como o fixo). Contudo, se um elemento posicionado de forma absoluta não tiver ancestrais posicionados, ele usará o corpo do documento e se moverá junto com a rolagem da página. São removidos do fluxo normal e podem sobrepor elementos.  
      * Serve para mudar a posição do ponto inicial que ele se encontra.
      ```
        div {
          position: absolue;
        }
      ```
      * **Sticky**: É posicionado com base na posição de rolagem do usuário. Um elemento adrente alterna entre relative e fixed, dependendo da posição de rolagem. É posicionado até que uma determinada posição de deslocamento seja encontrada na janela de exibição - então, ele se fixa no lugar dele. 
      ```
        div {
          position: sticky;
        }
      ```
    * Pseudo-classes
      * **Link não visitado**:
        ```
          a:link {
            color: #FF0000;
          }
        ```
      * **Link visitado**:
        ```
          a:visited {
            color: #00FF00;
          }
        ```
      * **Mouse em cima do elemento**:
        ```
          a:hover {
            color: #FF00FF;
          }
        ```
      * **Elemento selecionado**:
        ```
          a:active {
            color: #0000FF;
          }
        ```
4. **CURSO: HTML5 e CSS3 parte 3: TRABALHANDO COM FORMULÁRIOS E TABELAS**

  * **CSS**
    * Hierarquia no CSS
      * Inline
      * ID
      * Class
      * Tag
  

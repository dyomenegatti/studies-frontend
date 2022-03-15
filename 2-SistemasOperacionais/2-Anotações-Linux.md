# Linux I: Conhecendo e utilizando o terminal

## Anotações

1. **TRABALHANDO COM ARQUIVOS E DIRETÓRIOS**

| Comandos                        | Descrição                                     |
| -------------                   |:-------------:                                |
| pwd                             | retorna o diretório                           |
| ls                              | retorna todos os arquivos e diretórios        |
| echo "Bem Vindo"                | retorna a mensagem entre " "                  |
| echo "Bem Vindo" > bemvindo.txt | redireciona a mensagem para o arquivo         |
| cat bemvindo.txt                | le o arquivo no terminal                      |
| clear                           | limpa o terminal                              |
| ls -l                           | exibe as infos dos arquivos/diretórios        |
| ls -la                          | exibe todos os arquivos, inclusive os ocultos |
| man                             | retorna os dados de um comando                |
| whoami                          | retorna o nome do usuário logado              |
| cat -n                          | exibe o conteúdo do arquivo e a linha         |

2.  **MAIS SOBRE REDIRECIONAMENTO E CARACTERES CORINGA NO BASH**

| Comandos                        | Descrição                                                    |
| -------------                   |:-------------:                                               |
| cd Desktop                      | muda para o diretório especificado                           |
| echo "Always" >> musicas.txt    | concatena mensagem dentro de um arquivo                      |
| cd..                            | volta para o diretório anterior                              |
| ..                              | diretório anterior                                           |
| mkdir workspace                 | cria novo diretório                                          |
| cd                              | volta para o diretório base                                  |
| rmdir projetos.java             | apagar diretório                                             |
| rm arquivo.txt                  | apaga arquivo                                                |
| cat *.txt                       | ler todos os arquivos da mesma extensão do diretório         |
| rm -r workspace                 | remove todos os arquivos de um diretório o próprio diretório |

3. **MANIPULANDO, COMPACTANDO E DESCOMPACTANDO ARQUIVOS**
   
| Comandos                                        | Descrição                                  |
| -------------                                   |:-------------:                             |
| cp mensagem.txt bemvindo.txt                    | copia arquivo para outro arquivo           |
| mv mensagem.txt bemvindo.txt                    | renomear arquivo                           |
| mv bemvindo.txt projetos-java/bemvindo.txt      | move arquivo                               |
| mv bemvindo.txt projetos-java/bemvindo-novo.txt | move e renomeia                            |
| cp -r projetos-java projetos-c#                 | copia o diretório                          |
| zip -r work.zip workspace                       | compactar diretório                        |
| unzip -l work.zip                               | confere o arquivo compactado               |
| unzip work.zip                                  | descompactar arquivo                       |
| zip -rq work.zip workspace                      | compactando o arquivo e retirando logs     |
| unzip -q work.zip                               | descompactando o arquivo e retirando logs  |
| zip bemvindo.zip *.txt                          | compacta todos os arquivos de extensão txt |

4. **MAIS SOBRE COMPACTAÇÃO E DESCOMPACTAÇÃO E COMANDOS DO TERMINAL**

| Comandos                                        | Descrição                                                  |
| -------------                                   |:-------------:                                             |
| tar -cz workspace > work.tar.gz                 | compactar utilizando tar                                   |
| tar -xz < work.tar.gz                           | descompactar utilizando tar                                |
| tar -czf work.tar.gz workspace                  | compactar 2                                                |
| tar -xzf work.tar.gz                            | descompactar 2                                             |
| tar -vxzf work.tar.gz workspace                 | compactar e ver logs                                       |
| touch bemvindo.txt                              | apenas alterar a última data de atualização do arquivo     |
| head google.txt                                 | ler o começo do arquivo                                    |
| head -n 3 google.txt                            | ler a quantidade específica de linhas do início do arquivo |
| tail 3 google.txt                               | ler o rodapé do arquivo                                    |
| tail -n 3 google.txt                            | ler a quantidade específica de linhas do início do arquivo |
| less google.txt                                 | abrir o arquivo para navegação pelo terminal               |

5. **EDIÇÃO DE ARQUIVOS COM O VI: INCLUSÃO, EXCLUSÃO, REPETIÇÃO**

| Comandos                                        | Descrição                                      |
| -------------                                   |:-------------:                                 |
| vi google.txt                                   | editar o arquivo no terminal                   | 
| i                                               | altera o modo de navegação para inserção       | 
| esc                                             | sai do modo de edição                          | 
| :w                                              | salva o arquivo                                | 
| :q                                              | sai do modo de navegação                       | 
| a                                               | insere na posição seguinte                     | 
| x                                               | deleta o caractere atual                       | 
| 11x                                             | altera a quantidade especificada de caracteres | 
| dd                                              | remove uma linha por completo                  | 
| :q!                                             | sai sem salvar                                 | 
| A                                               | adiciona no final da linha                     | 
| :wq                                             | salva e sai                                    | 
| G                                               | direciona para a última linha                  | 
| 1G                                              | direciona para a linha especificada            | 
| $                                               | direciona para o final da linha atual          | 
| 0                                               | direciona para o início da linha atual         | 
| /palavra                                        | busca uma palavra                              | 
| n                                               | direciona para próxima ocorrência da busca     | 
| N                                               | direciona para a ocorrência anterior           | 
| yy                                              | copia linha completa                           |
| p                                               | cola linha completa                            | 
| 3yy                                             | copia a quantidade de linhas especificadas     |  
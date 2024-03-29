# Comandos essenciais para uso no Terminal Linux


## 0 - Identificar versão:
- Informações Completa
```shell
cat /etc/*-release
```
- ou
```shell
lsb_release -a
```


## 1 -  Manipulação de Diretorios e Arquivos (mv, cp, rm, mkdir, rmdir) 

### 1.1 - Comando mv, Mover Arquivos ou Diretorios  
```shell
- mv -<Argumento> <diretorio ou arquivo.extenção> <local>.
```

#### Exemplo abaixo move um arquivo nomeado como arquivo para o diretorio documentos: 
```shell
- mv -f arquivo.txt /home/luizcamini/documentos.
```
### 1.2 - Comando cp, Copiar Arquivos ou Diretorios
```shell
- cp -<Argumento> <diretorio ou arquivo.extenção> <local>
```
#### Exemplo copiando arquivos nomeados como arquivo_a e arquivo_b para o diretorio documentos: 
```shell
- cp arquivo_a.txt arquivo_b.txt /home/luizcmaini/documentos
```
### 1.3 - comando rm e rmdir, Remover Arquivos e/ou pastas  
```shell
- rm -<Argumento> <arquivo.extenção>  
```
#### Exemplo abaixo remove um arquivo simples
```shell
- rm arquivo.txt
```
#### Exemplo abaixo remove um diretorio chamado documentos utilizando o argumento r Recursivo  
```shell
- rm -r /home/luizcamini/documentos  
```
#### Exemplo abaixo remove diretorio documentos, com o comando rmdir (PS.: este comando só remove diretorios caso o mesmo esteja vazio)  
```shell
- rmdir documentos  
```

#### Exemplo Remove multiplos arquivos  
```shell
- rm arquivo_a.doc arquivo_b.txt arquivo_c.pdf
```
### 1.4 - comando mkdir, Criar Diretorios  

#### Exemplo Abaixo Cria um diretorio (Pasta) noemada como documentos  
```shell
- mkdir documentos
```

## 2 - Manipulação de programas

### 2.1 - APT-GET
#### Abaixo argumentos que podem ser usados com o apt-get  
- u, −−show-upgraded : mostra a lista de pacotes sendo atualizada.
- install pacotes : atualiza os pacotes especificados.
- remove pacotes : remove os pacotes especificados.
- update : atualiza a lista das versões dos pacotes disponíveis.
- upgrade : atualiza os pacotes instalados no sistema.
- -h, −−help : mostra as opções do comando.
- -v, −−version : mostra informações sobre o programa.  

#### Recomenda-se sempre que antes e depois de instalar novos programas utilizar os comandos abaixo para atualizar as bibliotecas :

```shell
- sudo apt-get update 
```

```shell
- sudo apt-get upgrade
```

### 2.2 - Removendo programas  

#### Comando abaixo desinstala somente os arquivos binários e as dependências que já não são utilizadas)

```shell
- sudo apt-get remove <nome do programa>
```

#### Comando abaixo remove tudo, incluindo configurações de usuário
```shell
- sudo apt-get pruge <nome do programa>
```

### 2.3 - Finalizar programas e relacionados a este (janelas do mesmo programa aberto serao fechadas, requer privilegios de super usuario)
```shell
- sudo killall <nome do programa>
```
#### Exemplo abaixo encerra o aplicativo (Programa) anydesk e todas as suas janelas
```shell
- sudo killall anydesk
```

### 2.4 - Finalizar programa indicando com o mouse  

```shell
- sudo xkill <use o mouse e selecione o programa que deseja ser fechado>
```

### 2.5 - Instalar programas  (requer privilegios de super usuario)
```shell
- sudo apt-get install <nome do programa> 
```

#### Exemplo abaixo instala o programa gimp usado para edição de imagens  
```shell
- sudo apt-get install gimp
```
## 3 - Manual de Programas 
```shell
- man <nome do programa>
```

#### Exemplo abaixo é apresentado o manual do editor de texto do linux gedit 
```shell
- man gedit
```


## 4 - Listar arquivos e diretorios

#### Exemplo abaixo Listar tudo de forma simples  
```shell
- ls
```

#### Exemplo abaixo Listar arquivos e diretorios mostrando detalhes de permissões etc
```shell
- ls -la
```

## 5 - Navegação entre pastas

#### Exemplo abaixo volta uma pasta
```shell
- cd ..
```

#### Exemplo abaixo acessa a pasta documentos
```shell
- cd documentos
```


#### Exemplo abaixo Mostra qual diretorio esta nomento
```shell
- pwd
```

#### Exemplo abaixo abre arquivo (deve ser utilizado dentro do diretorio que encontra-se o arquivo)
```shell
- cat <Nome do arquivo>
```

- PS Utilizar o TAB apos digitar a primeira, segunda ou terceira letra o sistema ira utilizar o intelicense para auto preencher o nome do arquivo ou diretorio (pasta)


## 6 - Demonstra espaço em disco

```shell
- df
```


## 7 - Permissões de Pastas e Arquivos

#### Exemplo abaixo 
```shell
- chmod go-rwx nomedapasta
```


## 8 - SSH

#### Comando abaixo instala os recursos do SSH no server linux:
```shell
sudo apt-get install openssh-server
```

#### Comando abaixo demonstra o status do ssh:
```shell
service ssh status
```

## 9 - Outros

#### Comando abaixo permite instalar APK's a partir de uma URL (Download disponivel na internet)
```shell
wget <url>
```

#### Comando Abaixo descompacta arquivos zipados
```shell
unzip <nome do arquivo.zip>
```

#### comando para compactacao de aquivos
```shell
- tar
```


#### compactar e reduzir arquivo 
```shell
- gzip <nome do arquivo>
```

#### compactar e reduzir arquivo 
```shell
- gzip <nome do arquivo>
```


#### para descompactar.

```shell
- gunzip < nome do arquivo para ser descompactado>
```

#### visualizar conteudo do arquivo tar
```shell
- tar -tvf <nome do arquivo>
```

#### visualizar conteudo do arquivo tar
```shell
- tar -tvf <nome do arquivo>
```

#### Ver tudo dentro do arquivo tar com nome item
```shell
- tar -tvf <nome do arquivo> PIPE grep u.item
```

#### comando para ver informações do tipo do arquivo 
```shell
file  <nome do arquivo>
```

#### comando para criar um despejo de hex ou binario de um determinado arquivo 
```shell
xxd <argumento> <nome do arquivo>
```

#### comando para identificar estado do (BASE) e desativar
```shell
conda config --show | grep auto_activate_base
```

- Desativar (BASE)
```shell
conda config --set auto_activate_base False
```

## 9 - RDP Client Linux FREERDP
- Instalar:
```shell
sudo apt-get update
sudo apt-get install freerdp2-x11
sudo apt-get upgrade
```

- Help:
```shell
xfreerdp /?
```

- Exemplo usando Rede local:
```shell
 xfreerdp /w:1336 /h:900 /u:administrador /v:192.168.0.10 /p:senha
```

- Exemplo usando porta rede wan
```shell
 xfreerdp /w:1336 /h:900 /u:administrador /v:192.168.0.10 /p:senha /port:4005
```

- Principais parametros:
/port: (porta) numero da porta de conexão, se não informar o padrão é 3389;
/u: (usuario) usuario que sera usado para conexao;
/p: (senha) senha do usuario;
/v: (IP da Conexao) ip que sera conectado;
/w: (pixels linha) Geometria da tela em linha (largura) exemplo: 1024 / 1280 / 1336 / 1920 ...
/h: (pixel coluna) Geometria da tela em coluna (Altura) exemplo: 768 / 960 / 1024 / 1080 ...
+clipboard redirecionar a area de transferencia (CTRL + C e CTRL + V para arquivos).

## 10 - Comandos de gerenciamento de Processos:

- Verifica o uso de processos do sistema e permite identificar o que esta mais consumindo recursos (os primeiros da Lista) para parar CTRL + C
```shell
top
```

- Comando ps lista os processos em execução no sistema, mas apenas resumido, sem detalhes.
```shell
ps
```

- Comando pstree permite visualizar os processos em forma de arvore melhorando a visualização e relações entre eles.
```shell
pstree
```

- Lista todos os processos com prioridades de execução com uma variação com escala entre 19 (menos significativa) a -20(mais significativa)
```shell
renice
```

## 11 - Usando VPN IPSEC Linux Ubuntu/Debian

- Instalar pacote VPNC
```shell
sudo apt-get install vpnc vpnc-scripts network-manager-vpnc network-manager-vpnc-gnome
```
#### Parte 1:
- Acessar Network > VPN > clicar botão (+)
- Selecionar (cisco compatible VPN)
- Name = <nome sua(empresa) VPN>
- Gateway = <IP fornecido por sua empresa>
- User name = <nome usuario>
- User Pasword = <senha usuario>
- Group name = <Nome Grupo>
- Group pasword = <Chave fornecida pela empresa Pré-shared Key>
#### Parte 2:
- Clicar na guia avançado;
- Vendor = Cisco(Default)
- Encryption method = Secure(default)
- NAT transversal = NAT-T when avaliable(defalt)
- IKE DH Group 5 (Forticlient)
- Perfect Forward Secrecy = DH Group 5 (Forticlient)


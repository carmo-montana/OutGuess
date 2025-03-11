### O `OutGuess` é uma ferramenta de esteganografia que permite esconder informações dentro de arquivos de imagem sem alterar significativamente a aparência visual da imagem. Ele é frequentemente usado para ocultar mensagens secretas em imagens, tornando-as praticamente indetectáveis a olho nu.

### Aqui está um guia passo a passo sobre como usar o OutGuess, com detalhes sobre cada comando:

1. Instalação do OutGuess
Antes de começar, você precisa instalar o OutGuess. No Linux, você pode compilar a partir do código-fonte:

```bash copy
# Clone o repositório do OutGuess
git clone https://github.com/resurrecting-open-source-projects/outguess.git

# Navegue até o diretório
cd outguess 

# Compile o código-fonte
./configure
make
sudo make install
```
## Escondendo uma Mensagem em uma Imagem
Para esconder uma mensagem em uma imagem, use o seguinte comando:

```bash Copy
outguess -d mensagem.txt imagem_original.jpg imagem_com_mensagem.jpg
```
`-d mensagem.txt`: Especifica o arquivo de texto que contém a mensagem que você deseja esconder.

`imagem_original.jpg`: A imagem original onde a mensagem será escondida.

`imagem_com_mensagem.jpg`: A nova imagem gerada que contém a mensagem escondida.

* O que acontece?

- O OutGuess lê a mensagem do arquivo `mensagem.txt` e a esconde na imagem `imagem_original.jpg`.

- A nova imagem `imagem_com_mensagem.jpg` é criada, contendo a mensagem escondida.

## Extraindo uma Mensagem de uma Imagem
Para extrair uma mensagem escondida em uma imagem, use o seguinte comando:

```bash
outguess -r imagem_com_mensagem.jpg mensagem_extraida.txt
-r: Indica que você deseja extrair a mensagem escondida.
```
`imagem_com_mensagem.jpg`: A imagem que contém a mensagem escondida.

`mensagem_extraida.txt`: O arquivo onde a mensagem extraída será salva.

* O que acontece?

- O OutGuess analisa a imagem `imagem_com_mensagem.jpg` e extrai a mensagem escondida, salvando-a no arquivo `mensagem_extraida.txt`.

## Verificando a Capacidade de Ocultação
Você pode verificar quantos dados podem ser escondidos em uma imagem antes de realmente esconder a mensagem:

```bash
outguess -k "chave_secreta" -c imagem_original.jpg
```
- `-k "chave_secreta"`: Especifica uma chave secreta para criptografar a mensagem (opcional).

- `-c`: Verifica a capacidade de ocultação da imagem.

* O que acontece?

O OutGuess analisa a imagem e informa quantos bytes podem ser escondidos nela.

## Escondendo uma Mensagem com uma Chave Secreta
Para adicionar uma camada extra de segurança, você pode usar uma chave secreta para criptografar a mensagem:

```bash
outguess -k "chave_secreta" -d mensagem.txt imagem_original.jpg imagem_com_mensagem.jpg
```
- `-k "chave_secreta"`: Define uma chave secreta para criptografar a mensagem.

- `-d mensagem.txt`: Especifica o arquivo de texto com a mensagem.

- `imagem_original.jpg`: A imagem original.

- `imagem_com_mensagem.jpg`: A nova imagem com a mensagem escondida e criptografada.

* O que acontece?

A mensagem é criptografada com a chave secreta antes de ser escondida na imagem.

## Extraindo uma Mensagem com uma Chave Secreta
Para extrair uma mensagem que foi escondida com uma chave secreta:

```bash
outguess -k "chave_secreta" -r imagem_com_mensagem.jpg mensagem_extraida.txt
```
- `-k "chave_secreta"`: A chave secreta usada para criptografar a mensagem.

- `-r`: Indica que você deseja extrair a mensagem.

- `imagem_com_mensagem.jpg`: A imagem com a mensagem escondida.

- `mensagem_extraida.txt`: O arquivo onde a mensagem extraída será salva.

* O que acontece?

O OutGuess usa a chave secreta para descriptografar e extrair a mensagem da imagem.

## Verificando a Integridade da Mensagem
Você pode verificar se a mensagem foi corretamente escondida e se pode ser extraída:

```bash
outguess -k "chave_secreta" -E imagem_com_mensagem.jpg
```
- `-E`: Verifica a integridade da mensagem escondida.

* O que acontece?

O OutGuess verifica se a mensagem pode ser extraída corretamente usando a chave secreta.

## Usando um Arquivo de Configuração
O OutGuess também permite usar um arquivo de configuração para definir parâmetros avançados:

```bash
outguess -c config_file.txt -d mensagem.txt imagem_original.jpg imagem_com_mensagem.jpg
```
- `-c config_file.txt`: Especifica um arquivo de configuração com parâmetros avançados.

* O que acontece?

O OutGuess usa as configurações definidas no arquivo config_file.txt para esconder a mensagem.

## Ajuda e Opções Adicionais
Para ver todas as opções disponíveis no OutGuess, você pode usar o comando de ajuda:

```bash
outguess -h
```

* O que acontece?

O OutGuess exibe uma lista de todas as opções e comandos disponíveis.

Resumo dos Comandos Principais
- `-d`: Esconde uma mensagem em uma imagem.

- `-r`: Extrai uma mensagem de uma imagem.

- `-k`: Usa uma chave secreta para criptografar/descriptografar a mensagem.

- `-c`: Verifica a capacidade de ocultação ou usa um arquivo de configuração.

- `-E`: Verifica a integridade da mensagem escondida.

- `-h`: Exibe a ajuda com todas as opções.

## Exemplo Completo
Esconder uma mensagem:

```bash
outguess -k "minha_chave_secreta" -d mensagem.txt imagem.jpg imagem_com_mensagem.jpg
```
Extrair a mensagem:

```bash
outguess -k "minha_chave_secreta" -r imagem_com_mensagem.jpg mensagem_extraida.txt
```
Verificar a capacidade de ocultação:

```bash
outguess -c imagem.jpg
```
Considerações Finais
`Segurança`: O uso de uma chave secreta adiciona uma camada extra de segurança, mas lembre-se de que a segurança total depende de como você gerencia e compartilha essa chave.

- Formato da Imagem: O OutGuess funciona melhor com formatos de imagem como JPEG, que permitem alterações sem perda significativa de qualidade visual.

- Agora você está pronto para começar a usar o OutGuess para esconder e extrair mensagens em imagens!

#

### `Autor`: Pedro olivieria
# **Git**

#### O Git em si é um sistema de versionamento de código distribuído, criado em 2005 pelo Linus Torvalds, usado no desenvolvimento de software e para registrar o histórico de edições de arquivos

### SHA1

A sigla SHA significa Secure Hash Algorithm, que é um conjunto de funções hash criptográficas, onde a encriptação gera um conjunto de caractere identificador de 40 dígitos, ou seja, é uma forma curta de representar um arquivo.

### **Objetos Internos do Git**

- **Blob;**
- **Tree;**
- **Commit.**

#### **Blob**

É um objeto binário grande utilizado para armazenar o conteúdo de um arquivo.

*echo -e 'blob 9\0conteudo'|openssl sha1*

Para gerar o mesmo sha1 que o git.

*echo "conteudo"|git hash-object --studin*

#### **Tree**

A Tree se trata de uma árvore que armazena Blob, em seus blocos base, de maneira que a Tree(árvore) armazena e aponta os Blobs.

**Observação:** A Tree armazena o nome do documento, já o Blob não, tornando então a Tree(árvore) responsável por montar toda estrutura das posições os arquivos, suas localizações, podendo as Trees(árvores) apontar tanto para Blobs quanto para outras Trees também.

#### **Commit**

O Commit é um conjunto de Tree(árvore) e Blob(objeto binário), onde seu processo torna permanente um conjunto de alterações nos Blobs e Trees.

**Observação:** O SHA1 do Commit é o hash de todo o conjuto integrado(Tree e Blob).



### Chave SSH e Tokens de Acesso Pessoal

#### Chave SSH

A chave SSH é uma forma de estabelecer uma conexão segura e encriptada entre duas maquinas, gerando assim duas chaves, uma *chave pública* e uma *chave privada*.

**Comando para gerar uma par de chaves**

1. ​      ssh-keygen -t (key do github) -c (seu e-mail)
2. ​       cd /c/Users/(nome do seu usuário do computador)/.ssh/          (esse comando serve para acessar a pasta .ssh)
3. ​       cat id_(key do github que você utilizou).pub                      (comando para ver a sua chave pública).
4. Comando **pwd** mostra os caminhos de diretórios tomados.
5. ​        eval $(ssh-agente -s)                   (para gerar o número do agente).
6. ​         ssh-add id_(chave privada)                   (nessa etapa você vai passar a chave privada ao agente, pois ele esta encarregado a descriptografar.)



**Observação:** Para clonar repositórios no github utilize o comando **git clone** e insira o HTTPS ou SSH.

#### **Tokens de Acesso Pessoal**

Os tokens de acesso pessoal são um conjunto de caracteres que são gerados para serem utilizados como "senha", esse token ao ser gerado pode ter um prazo de expiração ou não, mas sempre lembrar que assim que gerado, guardar esse token em alguma pasta, pois o Github só o mostrará uma única vez. 














# Extra - Comandos Git

Adaptado de: https://woliveiras.com.br/posts/comandos-mais-utilizados-no-git/

## Comandos do curso

Nessa página coloquei os comandos mais usados do git, para acompanhar o curso vamos precisar apenas dois: **git clone** e **git pull**:


###  Baixando o material 

Para baixarmos o material, vamos usar o comando para clonar um repositório existente:

``` console
git clone [repositorio]
````

Esse comando automaticamente cria uma pasta aonde estivermos executando com o nome do repositório.

Como o material está no github, o comando fica:

``` console
git clone https://github.com/joaopmedeiros/curso_python.git
```

###  Atualizando nosso material

Para atualizar o material utilizaremos o comando git pull para "baixar e atualizar" os arquivos.
Muito importante: só vai funcionar se você estiver executando o comando **dentro** da pasta.
**Observe abaixo o caminho C:\user....**

Sempre execute esse comando antes de iniciar as aulas, ler um material ou fazer os exercícios:

``` console
C:\Users\joao.cecilio\Documents\curso_python>git pull    
```


------------------------------------------------------------

## Demais comandos bem básicos e bastante utilizados:

### Iniciar um repositório do zero
Na pasta que será o novo repositório Git, execute o comando:

``` console
git init
```

### Adicionando alterações
Quando alteramos algo, devemos rodar o comando git add para adicionar ao index e depois fechar um commit.

Adicionando um arquivo
``` console
git add nome_do_arquivo
```

Adicionando tudo de uma vez (cuidado)
``` console
git add .
```

Salvando as alterações
Quando adicionamos com o git add ainda não estamos persistindo os dados no histórico do Git, mas adicionando a uma área temporária onde podemos ficar levando e trazendo alterações até garantirmos que algo realmente deve ser salvo, então rodamos o git commit.

Para fazer um commit, precisamos adicionar uma mensagem ao pacote, então rodamos com o parâmetro -m "mensagem".

Depois de ter adicionado as alterações com git add, rodamos:

``` console
git commit -m "mensagem"
``` 

### Verificando o que foi alterado
Para sabermos se tem algo que foi modificado em nossa branch, rodamos o comando git status.

``` console
git status
```

Enviando as alterações para o servidor
Para enviarmos as alterações para o servidor, rodamos o comando git push.

``` console
git push
```
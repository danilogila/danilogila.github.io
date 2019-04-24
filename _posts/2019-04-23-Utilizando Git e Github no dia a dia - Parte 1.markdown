---
title: "Utilizando Git e Github no dia a dia - Parte 1"
layout: post
date: 2019-04-23 20:00
image: https://danilogila.github.io/assets/images/linux_terminal_wallpaper.png
headerImage: false
tag:
- Git
- Github
- Open Source
category: blog
author: danilogila
description: Uma introdução aos comandos do Git e o uso do Github
---

![Markdowm Image]( /assets/images/git-tuts.png){: class="bigger-image" }
<figcaption class="caption">Foto por Digital Ocean</figcaption>

# Introdução:

Fala, pessoal! Tudo certo? Na postagem de hoje iremos aprender os comandos básicos do Git e como enviar nossos arquivos para o Github. Esse post será a primeira parte de uma série de postagens nas quais irei abordar os principais comandos e fluxos do uso do Git que irão desde de adicionar um arquivo, fazer commits, trabalhar com branches e até resolver os famosos conflitos.

### Conteúdo

* Instalando o Git
* Configurando o Git em sua máquina
* Criando um repositório local
* Criando nosso primeiro Commit
* Alterando nossa mensagem de commit
* Visualizando as mudanças no arquivo
* Modificando seu ultimo commit
* Ignorando... arquivos?
* Criando um repositório no Github
* Configurando nosso repositório remoto
* Enviando nossas alterações para o Github


### Antes de tudo…


Se você estiver usando algum Sistema Operacional baseado em Unix, você conseguirá utilizar o Git no terminal do sistema sem problemas. Caso esteja utilizando o Windows, procure o terminal do Git que virá na instalação do mesmo. 

Então sem mais delongas, vamos estudar Git :)

---

### Instalando Git em sua máquina

Para instalar o Git em sua máquina, entre no site oficial do Git e escolha a opção correspondente ao seu Sistema Operacional. Caso você esteja utilizando o Linux, basta digitar o comando abaixo no seu terminal:

<code class="git">sudo apt-get install git</code>

### Configurando o Git em sua máquina

Após a instalação, iremos fazer uma configuração inicial com suas credenciais de acesso. Isso é importante porque assim poderemos gravar todas as ações que fizermos no decorrer dos exercícios.

Digite os comandos a seguir no terminal:

<code class="git">git config --global user.name “meuusuario”</code><br>
<code class="git">git config --global user.email. “meuemail@email.com”</code>

### Criando um repositório local

Crie uma pasta chamada “git-tutorial” no local que desejar. Depois de criada, entre na pasta e digite o comando <code class="git">git init</code>. Olhando dentro da pasta iremos perceber que não teve nenhuma alteração visível mas existe uma pasta oculta foi criada com o nome <code class="shell">.git</code>, que contém várias configurações do nosso repositório.

Digite <code class="shell">la</code> no terminal para exibir arquivos e pastas que estão ocultos.

![Markdowm Image](/assets/images/git-init.gif)

### Criando nosso primeiro Commit

O próximo passo é criar algum arquivo para adicionar em nosso repositório local. Utilize o seu editor de texto favorito e crie um arquivo chamado <code class="git">filmes-favoritos.txt</code> e escreva alguns filmes que você mais curte. Depois de criar o arquivo, digite <code class="git">git status</code> para saber como o Git está enxergando nosso novo arquivo.

Atualmente nosso arquivo está como <code class="git">Untracked</code>. Isso quer dizer que o Git não está acompanhando as mudanças que estão sendo feitas no nosso arquivo. Para mudarmos isso, digite <code class="git">git add filmes-favoritos.txt</code> para colocar nosso arquivo em uma área de espera, ou seja, a Staging Area.

![Markdowm Image](/assets/images/git-status.gif)

Dica: Caso você queira adicionar vários arquivos ao mesmo tempo, digite <code class="git">git add .</code> (ponto) ou git add seguido dos nomes dos arquivos que deseja adicionar.

Para salvar as mudanças no nosso repositório local digite <code class="git">git commit -m “Meu primeiro commit”</code>. O “-m” nos permite colocar uma mensagem para que nos indique o que aquele commit está fazendo. 

![Markdowm Image](/assets/images/git-status.gif)

### Alterando nossa mensagem de commit

Suponha que você não tenha gostado da mensagem do seu último commit ou simplesmente tenha escrito algo errado e queira mudar. Para mudarmos nossa mensagem digite <code class="git">git commit --amend</code>.

O seu editor de texto padrão irá exibir no terminal o seu ultimo commit e agora podemos alterar a mensagem. Apague a mensagem <code class="git">“Meu primeiro commit”</code> e escreva <code class="git">"Adiciona meus filmes favoritos"</code>. Salve o arquivo e agora digite <code class="git">git log</code> para exibir todos os commits feitos

![Markdowm Image](/assets/images/amend.gif)

Podemos ver que a nossa mensagem foi alterada com sucesso :)

### Visualizando as mudanças no arquivo

Antes de fazer os commits dos nossos arquivos, é sempre válido verificar o que estamos alterando. Abra o arquivo filmes-favoritos.txt e adicione mais alguns filmes e salve o arquivo. Logo em seguida faça um <code class="git">git add filmes-favoritos.txt</code>. 

Digitando <code class="git">git status</code> novamente, vemos que o Git reconheceu que houve alguma alteração no nosso arquivo. Agora digite <code class="git">git diff filmes-favoritos.txt</code> e veremos o que há de diferente no nosso arquivo desde o último commit.

![Markdowm Image](/assets/images/gitdiff.gif)

### Ignorando... arquivos?

É muito comum durante o desenvolvimento de um projeto adicionarmos alguns arquivos que não tenha muita relevância enviar para o nosso repositório remoto como: arquivos de backup, arquivos gerados automaticamente por uma ferramenta, arquivos de ambiente e etc. 

Para impedir que esses arquivos sejam enviados para o nosso Github, por exemplo, iremos criar um arquivo chamado <code class="shell">.gitignore</code>. O <code class="shell">.gitignore</code> é um arquivo oculto que fica na pasta raiz do nosso projeto que tem como objetivo ser uma espécie lista. Essa lista deve conter o nome dos arquivos e/ou pastas que não queremos enviar para no nosso repositório remoto, ou seja, quando fizermos o <code class="git">push</code> para o Github os arquivos não serão enviados. 

Dica: Não esqueça de dar um Git add e commitar o <code class="shell">.gitignore</code> ;)


![Markdowm Image](/assets/images/ignore.gif)

### Criando um repositório no Github

Agora iremos criar nosso primeiro repositório no Github. Entre em https://github.com/ e faça seu cadastro no site. Terminando seu cadastro, na tela inicial clique no botão “Novo” ou “New” para criar um repositório.

No campo “Nome do Repositório” digite o nome que desejar. No exemplo, irei utilizar o nome git-workshop mas sinta-se a vontade para escolher o nome que desejar. 

![Markdowm Image](/assets/images/github-repo-create.png)

Por fim, clique em “Criar repositório” e se tudo der certo, teremos criado o nosso primeiro repositório no Github.

### Enviando nossas alterações para o Github

De volta ao terminal, iremos fazer uma configuração rápida no nosso repositório local. Digite <code class="git">git remote origin add</code> mais o endereço do nosso recém criado repositório no Github. Feito isso, estamos prontos para enviar nossas alterações locais para o Github :)

<code class="git">Git remote add origin https://github.com/danilogila/git-workshop.git</code>

Estão prontos? Agora digite <code class="git">git push origin master</code> para enviar nossas alterações para o Github. Caso seja solicitado, digite sua senha e o nome do usuário cadastrado no Github.


![Markdowm Image](/assets/images/push-remote.gif)

Funcionou! Não acredita? Volte para o seu Github e vá no seu repositório. Lá estará os arquivos que foram criados e as mensagens de commits que escolhemos durante a postagem.

---

### Considerações finais

Assim como saber falar inglês, dominar o Git e seu ecossistema se tornou extremamente necessário na vida dos desenvolvedores nos dias de hoje. Se você parar por 5 minutos e olhar algumas vagas de emprego, verá que sempre teremos o Git ou "experiência com versionamento de códigos" como requisito.

Se você chegou até aqui, refaça os passos que fizemos nesse tutorial adicionando novos arquivos no Github. Lembrem-se que a melhor forma de aprender algo é praticando ;)

Sintam-se livres para mencionar algum possível erro, dar dicas e o que mais acharem necessário.

Obrigado a todos o/
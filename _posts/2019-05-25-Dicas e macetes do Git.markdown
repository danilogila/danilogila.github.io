---
title: "Dicas e macetes do Git"
layout: post
date: 2019-05-25 18:00
image: https://danilogila.github.io/assets/images/git-beyond6.jpg
headerImage: false
tag:
- Linux
- Terminal
- Git
category: blog
author: danilogila
description: Dicas que podem facilitar seu dia
---

![Markdowm Image](https://danilogila.github.io/assets/images/git-beyond6.jpg){: class="bigger-image" }

# Introdução:

Fala aí, pessoal! Na postagem de hoje venho trazer alguns comandos do Git que podem nos poupar algum tempo durante o dia a dia do uso do Git. Alguns desses comandos já foram apresentados em algumas postagens anteriores, mas irei deixar de forma mais condensada pra que seja rápido e fácil de pesquisar :)

Essa postagem vai ser atualizada sempre que eu achar algum comando que possa nos ajudar, então salve o link da postagem em seus favoritos e volte aqui de vez em quando pra aprender algo novo.

---

### Init

O <code class="git">git init</code> é um comando velho e conhecido por nós, e de forma resumida, ele cria um repositório git no diretório em que digitamos o comando. Com esse comando você ainda consegue especificar o diretório alvo em que o repositório será criado. Ou seja, se você está na pasta X e queira iniciar um repositório na pasta Y, basta especificar o caminho da pasta no final do comando:

<code class="git">git init ~Desktop/Projetos/y</code>


### Add e commit no mesmo comando

Normalmente usamos o <code class="git">add</code> nos arquivos alterados e depois disso criamos o commit com esses mesmos arquivos. Podemos encurtar um pouco esse processo fazendo o add e o commit em um comando somente:

<code class="git">git commit -a -m 'Hello, World!'</code>

### Consertando a última mensagem de commit

Imagine que você esteja escrevendo uma mensagem de commit e só depois de ter feito o mesmo, percebe que teve um pequeno erro de escrita na mensagem. O que fazer agora? Felizmente podemos alterar a mensagem do último commit com o seguinte comando:

<code class="git">git commit --amend</code>

Após isso, o seu editor padrão será aberto pelo sistema com a ultima mensagem de commit feita. Altere texto e coloque sua nova mensagem de commit :)


### Listando todas as branches

<code class="git">git branch -a // Lista as branches tanto remoto quanto local </code>
<br/>
<code class="git">git branch    // Lista as branches local </code>


### Alterar o nome de uma branch

Vamos supor que você que queira criar uma branch chamada desenvolvimento mas de alguma maneira você digitou um nome errado. Para consertar esse erro, digite o seguintes comando:

<code class="git">git branch -m desenvimento desenvolvimento </code>
<br/>
Caso você já tenha enviado para o seu repositório remoto, basta seguir os seguintes passos:

<code class="git">git push origin --delete desenvimento </code><br/>
<code class="git">git push origin desenvolvimento </code>


### Adicionou um arquivo por engano?

Aposto que alguma vez você adicionou um arquivo sem querer na sua área do commit. As vezes acabamos adicionando um simples arquivo de texto, até mesmo uma foto pessoal ou qualquer coisa do tipo. 

Caso você não tenha feito o commit do arquivo, utilize o seguinte comando: 

<code class="git">git reset /Documentos/User/praia.jpg </code>

Caso já tenha feito o commit, não se desespere! Basta adicionar os seguintes passos no terminal.

<code class="git">git reset --soft HEAD~1</code><br/>
<code class="git">git reset /Documentos/User/praia.jpg </code><br/>
<code class="git">rm /Documentos/User/praia.jpg </code><br/>
<code class="git">git commit></code>


### Volte para uma branch anterior

Para voltar de forma rápida para a última branch em que você esteve, digite o comando <code class="git">git checkout -  </code>para voltar. Em outras palavras, esse comando serve somente como um alias para o comando <code class="git">git checkout nomeDaBranchAnterior</code>.


### Listando N commits

Para listar os N últimos commits no seu repositório utilize o <code class="git">git log -<n></code>, onde n representa a quantidade de commits a ser exibido

---

### Considerações finais

Gostou das dicas? Compartilhe essa postagem com os amigos. Caso você tenha alguma dica e queira compartilhar, adicione nos comentários para que outras pessoas saibam das suas tecnicas ninjas tambem. 

Abraços e até a próxima postagem o/
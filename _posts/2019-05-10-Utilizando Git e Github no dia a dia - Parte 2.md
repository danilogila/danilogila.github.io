---
title: "Utilizando Git e Github no dia a dia -  Parte 2"
layout: post
date: 2019-05-10 10:00
image: https://danilogila.github.io/assets/images/git_merge.png
headerImage: false
tag:
- Git
- Github
- branch
- Open Source
category: blog
author: danilogila
description: Conhecendo as famosas branches do Git
---

![Markdowm Image]( /assets/images/git_merge.png){: class="bigger-image" }
<figcaption class="caption">Foto por Caelum</figcaption>

# Introdução:

E aí, pessoal! Tudo certo? Dando continuidade ao nosso guia sobre Git, iremos conversar um pouco sobre Branches na postagem de hoje. Branches é um tópico super importante que sem o uso delas, nosso fluxo de trabalho seria muito mais difícil. Sem mais delongas, vamos ao que interessa.

### Conteúdo

* Porque utilizar branches?
* Criando uma branch
* Enviando nossa branch para o repositório remoto
* Deletando uma branch no repositório local
* Deletando uma branch no repositório remoto


### Antes de tudo…

Se você estiver usando algum Sistema Operacional baseado em Unix, você conseguirá utilizar o Git no terminal do sistema sem problemas. Caso esteja utilizando o Windows, procure o terminal do Git que virá na instalação do mesmo. 

Então sem mais delongas, vamos dar continuidade ao estudo do Git :)

---

### Porque utilizar branches?

Quando estamos desenvolvendo um projeto ou adicionando uma nova funcionalidade, há uma chance de construirmos algo que possa quebrar algo na nossa aplicação. Isso seria ruim se imaginarmos que os usuários do nosso projeto teria uma experiência ruim, e claro que não queremos isso. Podemos pensar na Branch como um protótipo de algo que queremos construir, que seja algo consistente e que possamos testar antes de adicionar no nosso fluxo principal da aplicação para que outros possam utilizar.

Não podemos nos esquecer de que o Git é uma ferramenta com o propósito de trabalhar com colaboração. Já pensou se todos que contribuíssem para um projeto utilizassem o mesmo fluxo ou branch? Com toda certeza, isso causaria uma enorme dor de cabeça. Um bom exemplo do benefício em utilizar branch é que podemos selecionar contribuições feitas por terceiros e caso seja algo bom e relevante para o nosso projeto, aí sim iremos adicionar na master do nosso projeto.

### Criando uma branch

Dando continuidade ao nosso projeto da postagem anterior, digite o seguinte comando no terminal para listarmos as Branches atuais em nosso projeto:

<code class="git">Git branch</code><br>

![Markdowm Image](/assets/images/gitbranch.gif)

Atualmente temos uma única branch chamada master. Se olharmos bem, estamos trabalhando com branches esse tempo todo! Viemos adicionando, deletando arquivos e fazendo nossos commits dentro de um único fluxo, e esse fluxo/branch é chamado master.

Para termos certeza de que estamos na branch/fluxo master, digite <code class="git">git status</code> no terminal e olhe a saída do comando: 

![Markdowm Image](/assets/images/gitstatusbranch.gif)

“On branch master” indica que realmente estamos na branch certa :)

Agora, vamos criar nossa primeira branch. Para criarmos uma branch, iremos usar o comando: 

<code class="git">git checkout -b novaBranch</code><br>

Com Isso, criamos uma branch, colocamos o nome dela de novaBranch e por fim saimos da master para a nossa nova branch. 

![Markdowm Image](/assets/images/criandobranch.gif)

### Adicionando arquivos na branch

Agora vamos criar um novo arquivo em nossa branch novaBranch. Crie um arquivo novo chamado minhas-musicas.txt e digite <code class="git">git status</code> no terminal.

O Git está nos falando o seguinte: “Olha! Temos um novo arquivo que está como untracked na nossa branch novaBranch. Digite Git add para adicionarmos esse arquivo na nossa branch atual.”. Em outras palavras, o nosso novo arquivo ainda não vai ter suas mudanças acompanhando em nossa branch atual.

Os próximos passos são: adicionar, fazer um commit, e fazermos um push da nossa nova branch para o repositório no Github. Digite os seguintes comandos:

<code class="git">Git add minhas-musicas.txt</code><br>
<code class="git">Git commit -m “Adiciona minhas-musicas.txt em novaBranch”</code><br>
<code class="git">Git push origin novaBranch</code><br>

![Markdowm Image](/assets/images/pushnovabranch.gif)

Diferente de como fizemos no artigo anterior, em nosso comando <code class="git">“git push …”</code> não estamos mais colocando master e sim novaBranch como branch alvo das nossas atualizações. Em outras palavras, estamos criando uma branch local com o nome novaBranch, adicionamos um arquivo e fizemos um commit do mesmo. E o que <code class="git">Git push origin novaBranch</code> faz exatamente? Ele refaz todo o processo dito anteriormente mas em nosso repositório remoto :)

Em nosso Github:

![Markdowm Image](/assets/images/remotebranch.gif)

Nosso projeto contém 2 branches no total: master e novaBranch. Em nosso master, temos os arquivos criados anteriormente e em nossa “novaBranch” temos os arquivos que estavam na master no momento em que criamos nossa branch mais o arquivo minhas-musicas.txt que adicionamos posteriormente.

Como exercício, volte para a branch master com o comando <code class="git">git checkout master</code>. Crie uma nova branch com o nome que desejar e crie alguns arquivos nesta nova branch. Por fim, faça os commits e mande para o repositório remoto sua nova branch e todas as atualizações feitas.


### Deletando uma branch

No início criamos uma branch chamada novaBranch, e agora vamos deletá la do nosso projeto de forma bem simples e rápida.

1 - Delete a branch localmente: Volte para a branch master com git checkout master e logo após digite <code class="git">git branch -D novaBranch</code>. 

![Markdowm Image](/assets/images/deletebranch.gif)

2 - Delete a branch no Github: Lembre-se que apagamos a branch com o comando anterior nosso repositório local. novaBranch ainda existe no nosso repositório remoto, então digite <code class="git">git push -d origin myBranch</code> para de remover do nosso repositório remoto.

### Considerações finais

Bem pessoal, no artigo de hoje vimos um pouco sobre as branches no Git e como trabalhar com elas. No próximo artigo vamos aprender como atualizar nossa branch master com as alterações feitas em outras branches.

Se você chegou até aqui, refaça os passos que fizemos nesse tutorial adicionando novos arquivos no Github. Lembrem-se que a melhor forma de aprender algo é praticando ;)

Sintam-se livres para mencionar algum possível erro, dar dicas e o que mais acharem necessário.

Obrigado a todos o/
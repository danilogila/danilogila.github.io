---
title: "Manual de sobrevivência do Shell Script para iniciantes"
layout: post
date: 2019-03-21 18:00
image: https://danilogila.github.io/assets/images/linux_terminal_wallpaper.png
headerImage: false
tag:
- Linux
- Terminal
- Shell Script
- MacOS
category: blog
author: danilogila
description: Uma breve introdução ao Shell Script
---

![Markdowm Image](https://danilogila.github.io/assets/images/linux_terminal_wallpaper.png){: class="bigger-image" }
<figcaption class="caption">Foto por Digital Ocean</figcaption>

# Introdução:

Ainda me lembro quando vi um terminal do Linux pela primeira vez. Fiquei espantado com o tanto de informações que tinham naquela estranha tela preta e isso me criou um certo pavor. Com o passar do tempo, fui estudando e conhecendo um pouco mais os comandos do Shell e percebi o quanto dominar aquele terminal seria produtivo para o meu dia-a-dia no estágio e na minha carreira profissional como um todo.

O objetivo dessa postagem é compartilhar um pouco da minha evolução com o Shell Script e mostrar que não precisamos ter medo de utilizá-lo. Veremos que no final ele será um grande aliado da nossa produtividade no ambiente de trabalho :)

### Antes de tudo…

Antes de começarmos, abra um terminal de sua preferência. Depois disso, iremos dar início ao nosso estudo do Shell. Veremos que será possível navegar entre diretórios, criar arquivos e muito mais.

---

### Listar arquivos e diretórios

Para listar/exibir arquivos e pastas de um diretório basta usar o comando <code class="shell">ls</code>. Se olharmos bem, veremos que os arquivos são listados com uma cor diferente das pastas. Dependendo do terminal que você esteja utilizando, será exibida de forma parecida para facilitar a visualização do conteúdo. Se o seu terminal não exibir dessa maneira, utilize <code class="shell">ls --color</code>.

![Markdowm Image](/assets/images/ls-command.gif)

### Mudando de diretório

Quando queremos mudar de diretório usamos o comando cd nome-do-diretório. Além disso, podemos mudar de diretório utilizando <code class="shell">cd ..</code>. Os <code class="shell">..</code> nos indica que estamos voltando um nível na hierarquia de diretórios . Ou seja, ao utilizar <code class="shell">cd ..</code> na pasta Download, voltaremos para a pasta tutorial-shell.

![Markdowm Image](/assets/images/cd-command.gif)

### Criando e removendo diretórios

Os comandos para criação e remoção de pastas são bem parecidos. Quando queremos criar um diretório utilizamos o <code class="shell">mkdir nome-do-diretório</code>. Para removermos o diretório utilizamos <code class="shell">rmdir nome-do-diretório</code>. Vale mencionar que se o diretório que você queira remover possui algum conteúdo dentro dele, devemos utilizar a flag <code class="shell">-r</code> antes do nome do diretório. Isso garante que ele irá remover todas as subpastas e arquivos, mas use esse comando com bastante sabedoria pois uma vez executado, ele irá remover todos os arquivos sem uma pergunta de confirmação ou algo do tipo.

![Markdowm Image](/assets/images/mk-rm-dir.gif)

### Criando e apagando arquivos

Utilizamos o comando <code class="shell">touch nome-do-arquivo</code> para criarmos um arquivo e podemos criar eles colocando uma extensão, dependendo do tipo de arquivo. Exemplo: <code class="shell">touch index.html</code> cria um arquivo HTML. Isso pode ser feito para diversos tipos diferentes de arquivos. Para remover, utilizamos o comando <code class="shell">rm nome-do-arquivo</code>.

![Markdowm Image](/assets/images/create-remove-files.png)

### Editar arquivos

Nano é um editor de texto que é utilizado em nosso terminal. O grande barato desse editor é que ele foca na simplicidade de realizar edições de texto nos arquivos desejados. Para editar um arquivo, basta digitar <code class="shell">nano nome-do-arquivo</code> e o editor irá abrir dentro do seu terminal.

Uma vez aberto, o nano nos oferece vários comandos de edição. Basta utilizar as funções desejadas e editar o seu arquivo da maneira mais conveniente.

Além do nano, temos outros editores como o Vi, Vim e etc mas isso fica pra um outro artigo ;)

![Markdowm Image](/assets/images/nano.png)

### Exibindo conteúdo de arquivos

Dentre os vários comandos de exibição, separei os 4 que eu mais utilizo no dia-a-dia. São eles:

<code class="shell">More</code> : Exibe uma página por vez do seu documento. Exemplo: more filmes.txt.

<code class="shell">Less</code>: O comando less é similar ao more. A diferença entre eles é que você consegue buscar um texto específico dentro do arquivo, consegue navegar entre as páginas e isso não é possível com o more. Exemplo: less agenda.txt

<code class="shell">Head</code>: exibe as 10 primeiras linhas do arquivo desejado. Exemplo: head jogos.txt.

<code class="shell">Tail</code>: mostra a parte final do arquivo. Exemplo: tail index.html.

<code class="shell">Cat</code>: Exibe todo o conteúdo de uma vez. A desvantagem desse comando é que se utilizarmos em um arquivo com bastante conteúdo, fica um pouco difícil de encontrarmos algum trecho específico. Exemplo: cat routes.go.

### Movendo e renomeando arquivos

De forma bastante curiosa, quando queremos mover e renomear algum arquivo, utilizamos o mesmo comando. Quando queremos mover um arquivo para um outro diretório, utilizamos o comando <code class="shell">mv nome-do-arquivo caminho/do/destino</code>. Exemplo: mv dialog.js Documents/backup/

Para renomear um arquivo iremos usar o mesmo comando de mover, só que ao invés de um diretório alvo, iremos colocar o novo nome do arquivo. 

![Markdowm Image](/assets/images/mv.gif)

### Mostrando diretório atual

O comando para mostrar o diretório atual é o <code class="shell">pwd</code>. Pwd é uma sigla para Print Work Directory, e ele exibe o caminho atual para o diretório que estamos operando no terminal.

![Markdowm Image](/assets/images/pwd.gif)

### Limpando o terminal

<code class="shell">Clear</code> remove do terminal todas as saídas de comandos utilizados. Bem útil para quando estamos fazendo muita coisa e queremos dar uma organizada na tela.

![Markdowm Image](/assets/images/clear.gif)

---

### Considerações finais

Vale mencionar que essa é somente a ponta do iceberg quando falamos de Shell Script. Veremos em artigos futuros que alguns comandos podem receber algumas variações na forma de exibir ou executar seus comandos.

Espero que com esse artigo você, leitor/leitora, tenha tido um bom entendimento do funcionamento básico do Shell Script e que tenha perdido um pouco do medo dessa telinha preta.

Sintam-se livres para mencionar algum possível erro, dar dicas e o que mais acharem necessário.

Obrigado a todos o/
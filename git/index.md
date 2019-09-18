---
layout: default
---
## git

`git` é referencia no desenvolvimento de software, estas no passado se não conheces o **git**, criado pelo pai grande
[Linus Torvalds](https://pt.wikipedia.org/wiki/Linus_Torvalds#Carreira), criador do [linux](https://www.linuxfoundation.org/)
é um sistema distribuído de controlo de versão, ao fazer
```shell
git clone https://github.com/baraberto/baraberto.github.io.git
```
ficas com a historia de todas as alterações feitas no repositório que consultas ao executar
```shell
git log
```
tens uma ideia, crias um no novo ramo(_branch_)
```shell
# o `-b` cria um novo ramo
git checkout -b 2-lets-talk-about-git
# Switched to a new branch '2-lets-talk-about-git'
```
vamos ver que ramos(_branches_) existem
```shell
git branch
# * 2-lets-talk-about-git
#  master
```
cria um ficheiro, faz alterações, em um existente
```shell
git status
# On branch 2-lets-talk-about-git
# Changes not staged for commit:
#   (use "git add <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working directory)
#
#         modified:   git/index.md
#
# Untracked files:
#   (use "git add <file>..." to include in what will be committed)
#
#         git/git-rules.md
#
# no changes added to commit (use "git add" and/or "git commit -a")

```
diz-te quais os ficheiros o git acompanha e foram alterados `modified:` e os que ainda não `Untracked files:`,
tens de dizer ao git quais as alterações,  que queres submeter com o `git add <caminho para o ficheiro>`

> não se deve usar o `git add .` pois vai adicionar tudo tirando as exclusões `.gitignore`

> **PRO** se pretendes adicionar os ficheiros que o git ja conhece foram alterados o `git add -u` faz maravilhas.

```shell
# vamos adicionar o index
git add git/index.md
# ver as o que esta em banho de maria
git status
# On branch 2-lets-talk-about-git
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#         modified:   git/index.md
#
# Untracked files:
#   (use "git add <file>..." to include in what will be committed)
#
#         git/git-rules.md
```
e tudo ok? vamos cometer essas alterações com
```shell
git commit
```
vai-te aparecer o teu editor para dizeres o que foi feito, escreve uma mensagem simples
```
<titulo>

<alteracoes que foram feitas>
```
como ficar no nosso computador e perigoso, vamos enviar esse para o servidor
```shell
git push origin 2-lets-talk-about-git
```
e voltas ao `master` com
```shell
git checkout master
```
para actualizar o git local com o servidor
```shell
git pull
```
queres ver as alteracoes entre o `master` e `2-lets-talk-about-git`
```shell
git diff 2-lets-talk-about-git
```
estas confiante nas tuas alterações (isto não se faz, mas para já)
```shell
git merge 2-lets-talk-about-git
```
e as alteracoes passam a estar no master

[atrás](./)

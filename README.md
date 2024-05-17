# Aprendendo a usar GIT

## Sobre o Git

<!-- TODO: create a simple introduction to what's Git -->

1. **Buscando ajuda**

A qualquer momento, você pode buscar ajuda sobre os comandos do git, basta digitar no terminal algum dos comandos abaixo

```bash
git help <verb>
git <verb> --help
man git-<verb>
```

## Fundamentos do Git

1. **Iniciando um projeto**

Para iniciar um projeto Git, basta digitar no terminal o seguinte comando:

```bash
git init
```
Esse comando irá inicar um diretório ```.git``` no diretório raiz do seu projeto, nele estará contido todo o banco de dados do versionamento do seu projeto gerenciado pelo git.

2. **Clonando um projeto**

Caso seu caso não seja de inicar um projeto do zero, mas começar a trabalhar em um projeto existente, primeiro será necessário clonar esse projeto de um repositório. O seguinte comando executa uma clonagem do projeto:

```bash
git clone https://github.com/git/git
```

Esse comando iniciará um diretório ```.git``` e fará a cópia completa de todo o versionamento do código no servidor. Dessa forma, caso o servidor seja corrompido, qualquer das duas versões, cliente ou servidor, poderá ser usada para restaurar o projeto.

3. **Fluxo de trabalho do Git**

Seus arquivos podem estar em um dos seguintes casos:

- Não rastreado (**Untracked**)
- Rastreado
    - Não modificados (**Unmodified**)
    - Modificados (**Modified**)
    - Preparados (**Staged**)

A imagem a seguir mostra o fluxo de estados que os arquivos do seu projeto podem percorrer.

![](https://git-scm.com/book/en/v2/images/lifecycle.png)

4. **Verificando o status dos seus arquivos**

Para verificar o status dos seus arquivos, basta usar o comando:

```bash
git status
```

Esse é um exemplo do retorno do comando:

```bash
git add CONTRIBUTING.md
git status


Your branch is up-to-date with 'origin/master'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

    new file:   README

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

    modified:   CONTRIBUTING.md
```

Nesse caso existem dois arquivos para serem serem registrados, `README` e `CONTRIBUTING.md`. Para preparar as modificações, use o comando `git add (arquivos)`. Após isso, executando um `git status` novamente:

```bash
git add CONTRIBUTING.md
git status


On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

    new file:   README
    modified:   CONTRIBUTING.md
```

Agora as modificações do arquivo `CONTRIBUTING.md` estão prontas para entrarem no próximo `git commit`.

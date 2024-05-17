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

5. **Ignorando arquivos**

É comum que seu projeto tenha arquivos que você não deseje versionar, como arquvios de variáveis de ambiente, arquivos de armazenamento, entre outros. Nesses casos, você pode criar um arquivo nomeado `.gitignore` contendo uma lista de padrões de nomes de arquivos a serem ignorados pelo git.

Um Exemplo de arquivo `.gitignore`:

```bash
cat .gitignore
*.[oa]
*~
```

Nesse casso, todos os arquivos que terminem com `.o`, `.a` ou `~`.

As regras para os padrões que podem ser usados no arquivo .gitignore são as seguintes:

- Linhas em branco ou começando com `#` são ignoradas.
- Os padrões que normalmente são usados para nomes de arquivos funcionam.
- Você pode iniciar padrões com uma barra `/` para evitar recursividade.
- Você pode terminar padrões com uma barra `/` para especificar um diretório.
- Você pode negar um padrão ao fazê-lo iniciar com um ponto de exclamação `!`.

6. **Fazendo commit das suas alterações**

Depois de preparar suas alterações basta digitar o comando:

```bash
git commit -m 'Meu primeiro commit!'
```

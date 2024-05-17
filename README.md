# Aprendendo a usar GIT

## Sobre o Git

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
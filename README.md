# oficina-git-github
A oficina abordará o uso do Git e Github na prática.


# Configurando o Git
[Ir para Referência](https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-Configura%C3%A7%C3%A3o-Inicial-do-Git)

O Git vem com uma ferramenta chamada git config que permite ver e atribuir variáveis de configuração que controlam todos os aspectos de como o Git aparece e opera. Estas variáveis podem ser armazenadas em três lugares diferentes:

1. __/etc/gitconfig__: válido para todos os usuários no sistema e todos os seus repositórios. Se você passar a opção --system para git config, ele lê e escreve neste arquivo.

2. __~/.gitconfig ou ~/.config/git/config__: Somente para o seu usuário. Você pode fazer o Git ler e escrever neste arquivo passando a opção --global.

3. __config no diretório Git__ (ou seja, .git/config) de qualquer repositório que você esteja usando: específico para este repositório.

Cada nível sobrescreve os valores no nível anterior, ou seja, valores em .git/config prevalecem sobre /etc/gitconfig.

A primeira coisa que você deve fazer ao instalar Git é configurar seu nome de usuário e endereço de e-mail. Isto é importante porque cada commit usa esta informação, e ela é carimbada de forma imutável nos commits que você começa a criar:

$ git config --global user.name "Fulano de Tal"
$ git config --global user.email fulanodetal@exemplo.br

##Testando as configurações
Se você quiser testar as suas configurações, você pode usar o comando __git config --list__ para listar todas as configurações que o Git conseguir encontrar naquele momento:

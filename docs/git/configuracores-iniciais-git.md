# Configurações Iniciais do Git

⚠️ O GIT já deve estar instalado nos computadores. Para aprender como instalar o git acesse [Instalando o Git.](https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-Instalando-o-Git)

🔗 Mais informações sobre as configurações no [link.](https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-Configura%C3%A7%C3%A3o-Inicial-do-Git)

É necessário configurar o Git pelo menos uma vez por computador. Abaixo é apresentada a configuração de identificação do usuário. Esta configuração é necessária para identificar o responsável pelos commits. O Git vem com uma ferramenta chamada *git config* que permite ver e atribuir variáveis de configuração que controlam todos os aspectos de como o Git aparece e opera. 

Essa configuração pode ser realizada em três locais diferentes, dependendo da opção inserida:

1. __--system__: atribui a configuração para todos os usuário do sistema;
2. __--global__: atribui a configuração apenas para o usuário do sistema;
3. Quando não inserida uma opção as configurações são apenas para o repositório local. 

        $ git config <opcao> user.name "Fulano de Tal"
        $ git config <opcao> user.email fulanodetal@exemplo.br

O comando *git config --list* lista todas as configurações.

Para editar as configurações no editor padrão:  

		$ git config --global -e

## Configurações básicas

É necessário configurar, pelo menos, o nome e o email do usuário para conseguir fazer o primeiro commit. Se estas informações não estiverem configuradas o Git vai exibir uma mensagem solicitando a configuração. Abaixo algumas configurações.

- name: git config --global user.name "meu nome aqui"
- email: git config --global user.name meu-email-aqui
- editor padrão(Referência: https://docs.github.com/pt/get-started/getting-started-with-git/associating-text-editors-with-git):   
	- Notepad++: git config --global core.editor "'C:/Program Files (x86)/Notepad++/notepad++.exe' -multiInst -notabbar -nosession -noPlugin"
	- Visual Studio COde: git config --global core.editor "code --wait"
	- Vim: git config --global core.editor vim
- delimitador de linha: 
	Windows: git config --global core.autocrlf true
	linux: git config --global core.autocrlf input
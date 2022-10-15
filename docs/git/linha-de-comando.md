# Linha de comando

🔗 Mais informações sobre linha de comando [link](https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-A-Linha-de-Comando)

O Git pode ser usado de duas formas:
   1. GUI - Graphical User Interface - Programas com interfaces gráficas;
   2. CLI - Command Line Interface - Linha de comando.

  Nesta oficina será utilizado a linha de comando:
  - A linha de comando é o único lugar onde se pode rodar todos os comandos do Git;
  - Usando a linha de comando pode facilmente rodar versões GUI.


  ## Comandos básicos no terminal git bash.

  🔗 Mais informações sobre comandos no [link.](https://guialinux.uniriotec.br/)

- cd (change directory) - usado para mudar o diretório de trabalho:
   
   Para ir ao diretório do usuário do sistema:
  
      $ cd ~/
  
   
   Para ir em um diretório filho: 
  
      $ cd nome-do-diretório
    
   Para voltar ao diretório pai: 

      $ cd ..


- ls (list) - lista o conteúdo de um diretório:

   Lista o conteúdo do diretório atual:
  
      $ ls

   Lista o conteúdo do diretório especificado:
  
      $ ls nome-do-diretorio
  

- mkdir (make directory) - cria diretórios:
   
   Criar um diretório dentro do diretório atual
  
      $ mkdir nome-do-diretorio
  
   Criar um diretório dentro de outro diretório. A tag -p ou −−parents cria hierarquia de diretórios:
  
      $ mkdir -p nome-do-diretorio/subdiretorio
  
- rm (remove) - comando que remove arquivos. Para apagar um arquivo:  

  Para apagar um diretório e todo o seu conteúdo. A flag -r apaga os arquivos e subdiretórios. A tag -f apaga sem pedir confirmação:
      
      $ rm -rf nome-do-diretório
  

- clear (limpa) - Para limpar o conteúdo da tela do terminal:

      $ clear
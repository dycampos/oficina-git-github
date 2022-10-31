# Fluxo de trabalho básico do Git

🔗 Mais informações sobre o básico do Git no [link](https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-O-B%C3%A1sico-do-Git) e no [link.](https://git-scm.com/book/pt-br/v2/Fundamentos-de-Git-Gravando-Altera%C3%A7%C3%B5es-em-Seu-Reposit%C3%B3rio)

  O Git possui três seções principais:
  - __Diretório de trabalho (working directory)__ - simples cópia de uma versão do projeto salva no disco para usar ou modificar;
  - __Área de preparo (staging area)__ - armazena informações do que vai entrar no próximo commit;
  - __Diretório Git (Repository)__ - armazena os metadados e o banco de dados de objetos de seu projeto. 
  
  <figure>
    <img src="../../img/fluxo-trabalho-git.png" alt="Seções principais de um projeto Git" width=500px       height=250px>
    <figcaption>Figura - Seções principais de um projeto Git</figcaption>
  </figure> 

Cada arquivo do diretório de trabalho pode estar em um dos seguintes estados: 
- __rastreados (_tracked_)__ - arquivos incluídos no último _snapshot_, arquivos que o Git conhece:
- __comitado ou não modificado (commited or unmodified)__ - dados armazenados de forma segura no banco de dados local;
- __modificado (modified)__ - dados alterados e não armazenados;
- __preparado (staged)__ - arquivo preparado para fazer parte do próximo commit.  

- __não rastreados (_untracked_)__ - arquivos não incluídos no último _snapshot_ e que não estão na área de stage.
  
O fluxo de trabalho básico do Git:
  1. os arquivos são *MODIFICADOS* no diretório de trabalho;
  2. os arquivos são *PREPARADOS*, adicionando-os à área de preparo;
  3. os arquivos são salvos de forma permanente no diretório Git.
   
<figure>
<img src="../../img/lifecycle.png" alt="Ciclo de Vida dos arquivos Git" width=500px height=250px>
<figcaption>Figura - Fluxo de trabalho Git</figcaption>
</figure>

A principal ferramenta para determinar em qual estados os arquivos estão é o ```git status```. Para uma visualização mais compacta pode-se utilizar a flag -s (short).

    $ git status -s ou $ git status --short


Para um respositório vazio a seguinte mensagem será retornada:

    $ git status
    On branch master
    No commits yet
    nothing to commit (create/copy files and use "git add" to track)


Se já existem commits realizados no repositório, e não há alterações realizadas, a seguinte mensagem será exibida:

    $ git status
    On branch master
    nothing to commit, working tree clean

No exemplo acima todos os arquivos estão no UNMODIFIED, porque não houve alteração desde o último commit. 

Se houve alguma alteração, o arquivo estará como MODIFIED. O git apresenta as opções: restaurar o arquivo e devolvê-lo ao estado de UNMODIFIED ou adicionar o arquivo na área de stage e mudar o estado dele para STAGED.

    $ git status
    On branch master
    Changes not staged for commit:
      (use "git add <file>..." to update what will be committed)
      (use "git restore <file>..." to discard changes in working directory)
            modified:   readme.md

    no changes added to commit (use "git add" and/or "git commit -a")

Para arquivos adicionados na STAGE, aparecerá a seguinte mensagem:

    $ git status
    On branch master
    Changes to be committed:
      (use "git restore --staged <file>..." to unstage)
            modified:   readme.md

Novos arquivos são considerados como não rastreados pelo Git:

    $ git status
    On branch master
    Untracked files:
      (use "git add <file>..." to include in what will be committed)
            teste.md

    nothing added to commit but untracked files present (use "git add" to track)


📜 Algumas vezes alguns arquivos não serão adicionados ao repositório mas estão no diretório de trabalho. Para estes arquivos não ficarem aparecendo como não rastreados existe o .gitignore. As pastas ou arquivos adicionados neste arquivo serão ignorados pelo git.

Após as alterações, inserções ou exclusões estamos preparados para criar um marco no projeto, um ponto de referênia, que podemos voltar caso necessário. Os arquivos da STAGE são armazedos no servidor local pelo comando _commit_. O comando abaixo abre o editor de texto para editar a mensagem de commit. No editor aparecem o que será incluido no commit.

    $ git commit


É possível ver as diferenças dos arquivos no editor:

    $ git commit -v

Para digitar a mensagem do commit direto na linha de comando é só utilizar a flag -m:

    $ git commit -m "Digite a mensagem aqui"

O comando abaixo coloca todos os arquivos rastreados e modificados para a área de STAGE e faz o commit:

    $ git commit -a -m "Digite a mensagem aqui"

Para remover um arquivo do Git é necessário utilizar o comando ```git rm nome-arquivo``` para removê-lo da stage e então fazer o commit. O Git então remove o arquivo do diretório de trabalho. Se apenas deletar o arquivo do diretório de trabalho ele aparecerá a mensagem ```changes not staged for commit.```. Se arquivo a ser removido foi alterado será necessário utilizar a flag -f para removê-lo. Essa é uma medida de segurança para evitar a exclusão acidental de um arquivo que não gravado no repositório.

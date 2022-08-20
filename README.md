# Git 

## Git Bash

console do git

## Verificar versão

- no console digite : git --version [enter]

## VS Code

- [Download VS Code](https://code.visualstudio.com/)
- na instalação é importante ativar Add to PATH
- [Notas VS Code](https://www.notion.so/Visual-Studio-Code-0d7cc9dcae254a77be4ce7cb0a993fa6)

## Gerenciadores de Repositórios

- [https://github.com](https://github.com/)
- [https://bitbucket.org/](https://bitbucket.org/)

## Mudança do nome principal de branch (alteração no GitHub)

- antes chamava master e **agora** chama **main**

## 1- Criar Repositório Remoto no GitHub

- na sua conta do GitHub em My Repositories clique em New
- preencha nome, descrição, escolha permissão e se quiser o que deve ser inicializado e clique em Create Repository

## 2- Configurar identidade global email e nome

- pode ser feito no terminal Bash no VSCode

```jsx
git config --global user.email "patriciauemura53@gmail.com"
git config --global user.name "Patricia Uemura"
// Omit --global to set the identity only in this repository.
```

## 3 - Criar novo repositório na linha de comando

1. crie a pasta que irá trabalhar e coloque um arquivo para iniciar
2. git init     //inicia repositório criando pasta oculta .git
3. git add [arquivo.txt]     // adiciona arquivo ao projeto e permite que seja monitorado e versionado
4. git commit -m "comentário"     // salva alterações do projeto e adiciona um comentário para identificação das alterações
5. git branch -M main      // criar branch principal com nome "main"
6. git remote add origin https://github.com/patriciauemura/curso_git.git      //configurar local no repositório remoto que deverá subir, com o nome de atalho "origin"
7. git push -u origin main      // envia ao repositório remoto GitHub indicado pelo atalho “origin” e para a branch “main”

>💡 push para a branch main só é feito em projetos pessoais, mas em empresas ou projetos com mais de uma pessoa deve haver uma pessoa responsável por isso.



## 4 - Outros comandos básicos

- git status      //verifica o status
- git restore [arquivo.txt]     // descarta alterações no diretório que está trabalhando
- git add .     // adiciona todos os arquivos da pasta que falta ser adicionado ao projeto
- git commit a.txt -m “enviando arquivo a”    // enviando um arquivo específico
- git commit -a -m “enviando todos arquivos”     // envia todos arquivos a serem commitados
- git pull     // trazer alterações do remoto para o local para sincronização
- git clone [endereço] .     // clonar repositório para a pasta atual, baixar um repositório de um servidor remoto, quando entramos em um projeto
- git rm [arquivo.txt]     // remover da monitoração do git, as atualização não serão mais consideradas pelo git, **é necessário commitar e dar push para o repositório remoto**
- git log     // histórico de alterações, informação dos commits realizados no projeto até o momento, armazena os commits de um branch
- git mv [arquivo.txt] [pasta]/[arquivo.txt]    // mover arquivo para outra pasta
- git mv [arquivo.txt] [renomeia.txt]     // renomeando arquivo
- git checkout [arquivo.txt]     // retorna ao estado original, desfaz alteração, deixa como está no repositório remoto, **executar na fase de stagging**
- git reset --hard origin/main     // desfaz alterações commitadas e pendentes e retorna a ficar igual ao branch, volta arquivos a versões passadas
- git reset --hard [hash]     // desfaz alteração da hash
- git revert HEAD~1     // desfaz o último commit, antes de fazer push
- .gitignore     //criar arquivo para incluir regras de exclusão, basta incluir lista com os arquivos [arquivo.txt] ou pastas [pasta/*] a serem ignorados



## Branchs

- versões do projeto, ao final os branchs são unidos para ter o código-fonte final
- git branch     // visualiza os branchs disponíveis
- git branch [nome]     // cria novo branch
- git -d [branch]    // ou --delete, deletar branch, não é comum deletar mas deixar como histórico
- git checkout -b [branch]     // mudar e branch branch, 🚩 alterações não commitadas na branch original, mudam-se junto para a outra branch
- git checkout [branch]     // apenas muda a branch
- git checkout -b “[branch]”     // cria branch a partir de outra branch que não é a main
- git push --set-upstream origin [branch]     // to push the current branch and set the remote as upstream
- git merge [branch]     // unir 2 branches, indique qual branch quer trazer para a branch que está atualmente, importante também trazer o main para o branch que estamos trabalhando para que esteja atualizado,

>💡 em empresas ou projetos que mais de uma pessoa trabalha, só é feito da nossa branch para master por alguém autorizado com essa função


- git stash     // as modificações atuais ficam arquivadas e o branch é resetado para a versão de acordo com o repo
- git stash list    // verifica stashs criadas
- git stash apply #     // recupera stash
- git stash show -p #     // mostra quais alterações foram feitas na stash
- git stash clear     // limpa todas stashs da branch
- git stash drop #     // apaga stash específica, faz com que o índice das próximas seja mudado para -1
- git tag -a [nome] -m “mensagem”     // como checkpoint de um branch, utilizada para demarcar estágios do desenvolvimento de um recurso
- git show [nome]     // verificar tag
- git checkout [nome]     // trocar de tag
- git push origin [nome]     // envia tag ao repositório remoto
- git push origin --tags     // envia várias tags

 

## Compartilhar e atualizar repositórios

- git fetch     // atualiza todos os branchs e tags remotos (de outros devs) que não estão reconhecidos por nós
- git pull     // recebe atualização do repositório remoto
- git push     // enviar alterações de arquivos commitados para o repo remoto
- git remote     // adicionar um repo para trackear ou remover
- git remote add origin [link]     // adiciona um repo remoto ao git
- git remote -v     // verifica quais as origens para receber/fetch e enviar/push
- git remote rm origin     // remove a origem
- git submodule add [repo] [diretorio]     // submódulo é a maneira que temos de possuir dois ou mais projetos em um só repositório, podendo adicionar dependência ao nosso projeto atual porém mantendo suas estruturas separadas
- git submodule     // verifica os submódulos
- git push --recurse-submodules=on-demand    // enviando para o submódulo, atualiza apenas o submódulo



## Análise e inspeção de repositórios

- git show     // exibe detalhes da branch
- git show [tag]     // exibe detalhes da tag
- git diff     // diferenças entre o branch atual e o remoto
- git diff [branch]     // diferenças entre o branch atual e o indicado
- git diff [arquivo1] [arquivo2]     // diferenças entre arquivos
- git shortlog     // log resumido do projeto, agrupados por nome do autor

## Administração de repositórios

- git clean     // verifica e limpa arquivos untracked, não utilizou git add ainda
- git gc     // garbage collector, exclui arquivos não necessários
- git fsck     // file system check, verifica integridade de arquivos e sua conectividade, verifica possíveis corrupções em arquivos
- git reflog     // mapear todos os passos no repositório, até mudança de branch, dados salvos até expirar, tempo de expiração padrão é de 30 dias
- git archive --format zip --output master_files.zip master    // transforma o repo em arquivo compactado, a master é zipada no arquivo master_files.zip



## Melhorando os commits do projeto

- commits sem sentido atrapalham o projeto
- private branches: criamos branches que não serão compartilhados no repositório (podemos fazer commits sem sentido), ao fim fazemos um rebase:
    - git rebase [branchAtual] [privateBranch] -i
    - excluimos os commits trocando **pick** por squash (para editar pressione i como no Vim)
    - renomeamos commits trocando pick por reword
    - (esc - sair da edição, :x! enter - salvar arquivo, # linhas ignoradas)
- Boas mensagens do commit
    - assunto máx 50 caracteres com letra inicial maiúscula, corpo máx 72 caracteres
    - para separar assunto de corpo basta deixar uma linha entre eles utilizando enter
    - explicar o por quê e como do commit, e não como o código foi escrito



## Explorando e entendendo o GitHub

- aba Pull Request - códigos enviados para resolver issues ou adicionar novas funcionalidades, não é inserido direto na master
- aba Actions CI/CD - criar automatizações de deploy (implantação, colocar no ar aplicação concluida) com integração em outros serviços, ou seja, criar rotina de atualizar a master automaticamente e outros processos
- aba Projects - parecido com Trello
- aba Wiki - documentação mais extensa para o projeto, descrever funcionalidades, bugs conhecidos e não solucionados…, repositório de conhecimento sobre o projeto
- aba Insights - informações detalhadas doo projeto: contribuidores, commits, forks…
- aba Settings - configurações
- gists - pequenos blocos de código para armazenar


## Markdown do básico ao avançado

- \*\*texto negrito** \_\_texto negrito__
- \_texto italico_
- listas com * ou 1.
- ![Texto Alt](link da imagem)
- \[Texto do Link](link)
- \``` javascript código ```
- \[x] task list
- \[ ] task list
- [Guia Markdown](https://www.markdownguide.org/basic-syntax/)


## Links úteis

[Ícones](https://ionic.io/ionicons/usage)

[Fontes Google (tipografia)](https://fonts.google.com/)

[Dev Icons](https://devicon.dev/)

[Curso Git e Github do básico ao avançado - Matheus Battisti](https://cognizant.udemy.com/course/git-e-github-do-basico-ao-avancado-c-gist-e-github-pages/learn/lecture/21922906#overview)
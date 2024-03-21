- **`git init`**
  - Sintaxe padrão: `git init`
  - Exemplo adicional: Para iniciar um repositório Git em um diretório chamado "meu_projeto", você usaria: `git init meu_projeto`

- **`git status`**
  - Sintaxe padrão: `git status`
  - Exemplo adicional: Não há variação, pois `git status` é um comando informativo.

- **`git clone [url]`**
  - Sintaxe padrão: `git clone https://github.com/usuario/repositorio.git`
  - Exemplo adicional: Para clonar um repositório em um diretório específico, use: `git clone https://github.com/usuario/repositorio.git nome_diretorio`
  
  - **`git clone --branch [nome_da_branch] [url_do_repositório]`**
  - Sintaxe padrão: `git clone --branch nome_da_branch url_do_repositório.git`
  - Exemplo adicional: Para clonar uma branch específica chamada "feature_x" de um repositório remoto, você usaria: `git clone --branch feature_x https://github.com/usuario/repositorio.git`
  - Exemplo adicional: Para clonar uma branch específica e limitar o histórico a apenas o último commit (útil para repositórios grandes), use: `git clone --branch nome_da_branch --single-branch --depth 1 url_do_repositório.git`

- **`git add [arquivo]`**
  - Sintaxe padrão: `git add README.md`
  - Exemplo adicional: Para adicionar todos os arquivos modificados ao staging, use: `git add .`

- **`git commit -m "[mensagem]"`**
  - Sintaxe padrão: `git commit -m "Adiciona funcionalidade X"`
  - Exemplo adicional: Para realizar um commit incluindo todos os arquivos que já estão no staging, use: `git commit -am "Atualiza arquivos X e Y"`

- **`git commit --amend`**
  - Sintaxe padrão: `git commit --amend`
  - Exemplo adicional: Para alterar a mensagem do último commit, você usaria: `git commit --amend -m "Nova mensagem de commit"`
  - Exemplo adicional: Para incluir alterações que foram esquecidas no último commit, primeiro adicione os arquivos com `git add`, e então use: `git commit --amend`

  
  - **`git restore`**
  - Sintaxe padrão: `git restore <pathspec>`
  - Exemplo adicional: Para restaurar um arquivo chamado `index.html` para o estado do último commit, você usaria: `git restore index.html`
  - Exemplo adicional: Para restaurar um arquivo para o estado de um commit específico, use: `git restore --source 5d7a14 index.html`

- **`git log`**
  - Sintaxe padrão: `git log`
  - Exemplo adicional: Para ver o histórico dos commits, use: `git log`

- **`git reset`**
  - Sintaxe padrão: `git reset [opção] [commit]`
  - Exemplo adicional: Para desfazer o último commit mantendo as alterações no diretório de trabalho, você usaria: `git reset --soft HEAD~1`
  - Exemplo adicional: Para desfazer o último commit e todas as alterações, use: `git reset --hard HEAD~1`

O comando git reset é usado para redefinir o HEAD atual para um estado especificado. As opções --soft, --mixed e --hard determinam o comportamento do comando em relação ao índice e ao diretório de trabalho:

--soft: O índice e o diretório de trabalho não são alterados. Isso é útil para redefinir o HEAD para um commit anterior e preparar para um novo commit.
--mixed: O índice é redefinido para corresponder ao HEAD especificado, mas o diretório de trabalho não é alterado. Este é o comportamento padrão se nenhuma opção for fornecida.
--hard: Tanto o índice quanto o diretório de trabalho são redefinidos para corresponder ao HEAD especificado
Atenção: esta opção descarta todas as alterações no diretório de trabalho desde o commit especificado

- **`git remote`**
  - Sintaxe padrão: `git remote add <nome> <url>`
  - Exemplo adicional: Para adicionar um novo repositório remoto chamado "origin" com a URL do repositório, você usaria: `git remote add origin https://github.com/usuario/repositorio.git`
  - Exemplo adicional: Para remover um repositório remoto chamado "origin", use: `git remote remove origin`  
  
- **`git push`**
  - Sintaxe padrão: `git push <remote> <branch>`
  - Sintaxe padrão: `git push -u origin main`
  - Exemplo adicional: Para enviar commits da branch local "main" para a branch "main" no repositório remoto "origin", você usaria: `git push origin main`
  - Exemplo adicional: Para enviar todos os branches locais para o repositório remoto, use: `git push --all origin`
  - Exemplo adicional: Para forçar um push quando ocorrem conflitos, use: `git push origin main --force`

- **`git pull [alias] [branch]`**
  - Sintaxe padrão: `git pull origin main`
  - Exemplo adicional: Para fazer um pull e rebase em vez de merge, use: `git pull --rebase origin main`

- **`git branch`**
  - Sintaxe padrão: `git branch`
  - Exemplo adicional: Para listar todas as branches locais no repositório atual, você usaria: `git branch`
  - Exemplo adicional: Para criar uma nova branch chamada "feature_x", use: `git branch feature_x`

- **`git branch -d [branch]`**
  - Sintaxe padrão: `git branch -d feature_x`
  - Exemplo adicional: Para deletar uma branch chamada "feature_x" que já foi mesclada com a branch principal, você usaria: `git branch -d feature_x`
  - Exemplo adicional: Para forçar a deleção de uma branch chamada "feature_x" que não foi mesclada, use: `git branch -D feature_x`

- **`git branch -m [oldbranch] [newbranch]`**
  - Sintaxe padrão: `git branch -m old_name new_name`
  - Exemplo adicional: Para renomear uma branch de "old_name" para "new_name", você usaria: `git branch -m old_name new_name`

O comando git branch é usado para listar, criar ou deletar branches1. Ele não permite alternar entre branches ou juntar um histórico bifurcado novamente. Por essa razão, git branch é integrado com os comandos git checkout e git merge para operações adicionais2.

- **`git checkout`**
  - Sintaxe padrão: `git checkout [opções] <branch>`
  - Exemplo adicional: Para mudar para uma branch chamada "feature_x", você usaria: `git checkout feature_x`
  - Exemplo adicional: Para criar uma nova branch chamada "feature_y" e mudar para ela imediatamente, use: `git checkout -b feature_y`

- **`git checkout [commit]`**
  - Sintaxe padrão: `git checkout 5d7a14`
  - Exemplo adicional: Para restaurar um arquivo chamado `index.html` para o estado de um commit específico, você usaria: `git checkout 5d7a14 -- index.html`

- **`git stash`**
  - Sintaxe padrão: `git stash push`
  - Exemplo adicional: Para salvar suas alterações atuais e limpar o diretório de trabalho, você usaria: `git stash push -m "Salvando meu trabalho"`
  - Exemplo adicional: Para salvar também arquivos não rastreados, use: `git stash push -u`

- **`git merge`**
  - Sintaxe padrão: `git merge [nome_da_branch]`
  - Exemplo adicional: Para incorporar as mudanças da branch chamada "feature_x" na branch atual, você usaria: `git merge feature_x`
  - Exemplo adicional: Para realizar um merge e evitar um commit de merge (fast-forward), use: `git merge feature_x --ff-only`

- **`git fetch`**
  - Sintaxe padrão: `git fetch [opções] [nome_remoto] [branch]`
  - Exemplo adicional: Para buscar todas as atualizações do repositório remoto chamado "origin", você usaria: `git fetch origin`
  - Exemplo adicional: Para buscar atualizações de uma branch específica chamada "feature" do repositório remoto "origin", use: `git fetch origin feature`

- **`git fetch --all`**
  - Sintaxe padrão: `git fetch --all`
  - Exemplo adicional: Para buscar atualizações de todos os repositórios remotos configurados, você usaria: `git fetch --all`

- **`git diff`**
  - Sintaxe padrão: `git diff`
  - Exemplo adicional: Para ver as diferenças entre o diretório de trabalho e a área de staging, você usaria: `git diff`
  - Exemplo adicional: Para ver as diferenças entre o último commit e o diretório de trabalho, use: `git diff HEAD`

- **`git diff --staged`** ou **`git diff --cached`**
  - Sintaxe padrão: `git diff --staged`
  - Exemplo adicional: Para ver as diferenças entre a área de staging e o último commit, você usaria: `git diff --staged`
  - Exemplo adicional: Para ver as diferenças entre a área de staging e um commit específico, use: `git diff --staged <commit>`

- **`git diff [branch1] [branch2]`**
  - Sintaxe padrão: `git diff branch1 branch2`
  - Exemplo adicional: Para ver as diferenças entre duas branches, "master" e "feature", você usaria: `git diff master feature`

- **`git diff [commit1] [commit2]`**
  - Sintaxe padrão: `git diff commit1 commit2`
  - Exemplo adicional: Para ver as diferenças entre dois commits, use: `git diff commit1 commit2`
# 🧩 Aula Prática – Git Local (sem GitHub)

## 🎯 Objetivo
Aprender a utilizar o **Git** localmente para versionar projetos, criando commits, branches e manipulando o histórico de forma segura.

---

## 🧱 1. Configuração inicial

Esses comandos configuram o nome e o e-mail do usuário (necessário para registrar os commits).

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@exemplo.com"
git config --global core.editor "code --wait"   # Define o VS Code como editor padrão (opcional)
git config --list                                # Verifica as configurações atuais
```

---

## 📂 2. Criar e iniciar um repositório

```bash
mkdir meu_projeto
cd meu_projeto
git init
```

> O comando `git init` cria um repositório local, gerando a pasta oculta `.git`.

---

## 🏷️ 3. Alterar a branch padrão de `master` para `main`

Por padrão, o Git pode criar a branch inicial como **master**.  
Para padronizar e seguir boas práticas, altere para **main**:

```bash
git branch -m master main
```

Se quiser definir **main** como padrão para novos repositórios:

```bash
git config --global init.defaultBranch main
```

---

## 📄 4. Criar arquivos e verificar status

```bash
echo "Meu primeiro arquivo" > readme.txt
git status
```

> `git status` mostra arquivos novos, modificados ou prontos para commit.

---

## 🧺 5. Adicionar arquivos à área de staging

```bash
git add readme.txt       # adiciona um arquivo específico
git add .                # adiciona todos os arquivos do diretório
git status
```

> A área de staging é onde os arquivos ficam “preparados” antes do commit.

---

## 💾 6. Fazer o primeiro commit

```bash
git commit -m "Primeiro commit - adiciona readme.txt"
```

> Um commit é o “salvamento” oficial no histórico do repositório.

---

## 🔍 7. Ver histórico e detalhes

```bash
git log
git log --oneline
git show
```

> Use `--oneline` para visualizar um resumo simplificado.

---

## ✏️ 8. Editar arquivos e registrar mudanças

```bash
echo "Adicionando nova linha" >> readme.txt
git status
git diff
git add readme.txt
git commit -m "Atualiza readme.txt com nova linha"
```

> `git diff` mostra as diferenças entre a versão atual e a anterior.

---

## ♻️ 9. Desfazer mudanças

```bash
git restore readme.txt              # descarta mudanças não adicionadas
git restore --staged readme.txt     # remove da área de staging
```

> Ideal para corrigir erros antes de um commit.

---

## 🌿 10. Criar e alternar entre branches

```bash
git branch                         # lista branches
git branch nova_funcionalidade     # cria nova branch
git switch nova_funcionalidade     # muda para ela
```

> Cada branch é uma linha independente de desenvolvimento.

---

## 🧬 11. Fazer commits em outra branch

```bash
echo "Nova feature" > feature.txt
git add feature.txt
git commit -m "Adiciona nova feature"
```

---

## 🔀 12. Voltar e mesclar mudanças

```bash
git switch main
git merge nova_funcionalidade
```

> Junta as alterações da branch `nova_funcionalidade` na `main`.

---

## 🗑️ 13. Excluir branches locais

```bash
git branch -d nova_funcionalidade
```

---

## 🧹 14. Ignorar arquivos com `.gitignore`

Crie um arquivo chamado `.gitignore` e adicione:

```
*.log
*.tmp
node_modules/
```

Depois:

```bash
git add .gitignore
git commit -m "Adiciona arquivo .gitignore"
```

---

## 🧠 15. Visualizar informações úteis

```bash
git status
git log --oneline --graph --decorate
git diff
git show HEAD
```

> `--graph` mostra o histórico com ramificações visualmente.

---

## 💡 16. Exemplo de fluxo completo

```bash
git init
echo "Aula prática Git local" > readme.txt
git add .
git commit -m "Primeiro commit"
git branch dev
git switch dev
echo "Nova versão em desenvolvimento" >> readme.txt
git add .
git commit -m "Atualiza versão dev"
git switch main
git merge dev
git log --oneline --graph
```
Perfeito! Agora aqui está a continuação da documentação em **Markdown**, focada na integração entre Git local e GitHub, uso do GitFluence e colaboração em repositórios privados:

---


## 🎯 Objetivo
Aprender a integrar o **Git local** com o **GitHub**, utilizando comandos essenciais para colaboração, versionamento remoto e uso da ferramenta [GitFluence](https://www.gitfluence.com/) como apoio.

---

## 🔗 2.1 Clonagem e Configuração Local

Após realizar o **fork** do repositório original no GitHub:

| Tarefa                  | Comando Git                                | Explicação |
|------------------------|---------------------------------------------|------------|
| Clonar o Repositório   | `git clone <URL do seu fork>`               | Baixa a cópia do repositório para sua máquina local. |
| Acessar a Pasta        | `cd git-local`                              | Entra na pasta do repositório clonado. |
| Criar um novo Branch   | `git checkout -b documentacao-colaboracao`  | Cria um novo branch para a documentação, mantendo o `main` limpo. |

---

## 🧠 2.2 Uso do GitFluence para Comandos de Integração

O [GitFluence](https://www.gitfluence.com/) é uma ferramenta que sugere comandos Git com base em descrições simples.

| Descrição no GitFluence                     | Comando Git                                | Tópico da Documentação |
|--------------------------------------------|---------------------------------------------|------------------------|
| Push the new branch to the remote repository | `git push -u origin documentacao-colaboracao` | Enviar o novo branch para o GitHub. |
| See all my current branches                 | `git branch -a`                             | Visualizar branches locais e remotos. |
| Check the status of my files                | `git status`                                | Verificar o estado dos arquivos antes do commit. |

---

## 📝 2.3 Edição da Documentação (Local)

Edite os arquivos de documentação (ex: `README.md`) no seu ambiente local.

### ➕ Adicione as seções:

- **Integração Git Local com GitHub**:
  - `git clone`, `git add`, `git commit`, `git push`
- **Como adicionar colaboradores ao repositório privado**:
  - Instruções completas no Passo 3.
- **Como usar o GitFluence**:
  - Breve menção com exemplos de comandos gerados.

---

## 🚀 2.4 Commit e Push das Alterações

| Tarefa                  | Comando Git                                               | Explicação |
|------------------------|------------------------------------------------------------|------------|
| Adicionar os Arquivos  | `git add .`                                                | Prepara todos os arquivos modificados para o commit. |
| Criar o Commit         | `git commit -m "feat: Adiciona documentacao sobre integracao e colaboracao"` | Salva as alterações no histórico local. |
| Enviar para o GitHub   | `git push` ou `git push origin documentacao-colaboracao`   | Envia o novo branch com as alterações para o seu repositório no GitHub. |

---

# 🤝 3. Integração e Colaboração no GitHub

## 📤 3.1 Abrir um Pull Request (PR)

Após enviar o branch para o seu fork:

1. Acesse o seu fork no GitHub.
2. O GitHub irá sugerir automaticamente que você abra um PR.
3. Abra o PR do seu branch `documentacao-colaboracao` para o `main` do repositório original.

---

## 👥 3.2 Adicionar Colaboradores a um Repositório Privado

Para adicionar colaboradores ao seu repositório privado:

1. Acesse o repositório no GitHub.
2. Clique em **Settings** (Configurações).
3. No menu lateral esquerdo, vá em **Access** → **Collaborators**.
4. Clique em **Add people**.
5. Pesquise o usuário pelo nome de usuário, nome completo ou e-mail.
6. Clique no nome correto e depois em **Add NAME to REPOSITORY**.
7. O GitHub enviará um convite por e-mail.
8. O usuário deve aceitar o convite para ter acesso ao repositório e poder fazer commits.

> 🔒 Em repositórios privados, o acesso só é concedido após o aceite do convite.

---

## 🧩 Dica Final

Utilize o [GitFluence](https://www.gitfluence.com/) para explorar comandos Git com base em descrições simples.  
Exemplo: digite “create a new branch and switch to it” e receba o comando `git checkout -b nome-da-branch`.

---

## 📘 Créditos

Material complementar à aula prática de **Git Local + GitHub**,  
elaborado por *Anderson R. M. Gomes* 🧑‍🏫

--- 






---


# Comandos Git: Pull, Fetch, Commit, Push, Merge e Padronizações de Commits

Neste tutorial, vamos explorar alguns comandos fundamentais do Git, como `pull`, `fetch`, `commit`, `push` e `merge`, além de discutir algumas boas práticas para padronização de commits.

## 1. Comando `commit`

O comando `commit` é usado para salvar mudanças feitas no repositório local. Cada commit deve ser uma "foto" do estado do projeto em um determinado momento.

1. Após fazer alterações nos arquivos do seu projeto, adicione-os ao índice (stage):

   ```bash
   git add .
   ```

   Ou adicione um arquivo específico:

   ```bash
   git add nome_do_arquivo.txt
   ```

2. Faça um commit das alterações:

   ```bash
   git commit -m "Mensagem descritiva do commit"
   ```

   A mensagem de commit deve ser clara e descrever as mudanças feitas.

## 2. Comando `push`

O comando `push` é usado para enviar os commits do repositório local para o repositório remoto (por exemplo, no GitHub).

1. Envie suas alterações para o repositório remoto:

   ```bash
   git push origin main
   ```

   *Substitua `main` pelo nome da branch na qual está trabalhando.*

## 3. Comando `fetch`

O comando `fetch` é usado para baixar as atualizações do repositório remoto, sem integrá-las ao seu trabalho local. Esse comando é útil para conferir o que mudou no repositório remoto antes de realizar um merge.

1. Baixe as atualizações do repositório remoto:

   ```bash
   git fetch origin
   ```

   Esse comando irá baixar todas as atualizações da branch `origin`, mas não as aplicará automaticamente.

## 4. Comando `pull`

O comando `pull` é usado para baixar as atualizações do repositório remoto e integrá-las automaticamente ao seu trabalho local. É uma combinação dos comandos `fetch` e `merge`.

1. Atualize sua branch local com as mudanças do repositório remoto:

   ```bash
   git pull origin main
   ```

   *Substitua `main` pelo nome da branch na qual está trabalhando.*

## 5. Boas Práticas para Mensagens de Commits

Manter uma padronização clara para mensagens de commits é essencial para o entendimento do histórico do projeto e facilita a colaboração com outros desenvolvedores. Aqui estão algumas boas práticas para padronizar suas mensagens de commit:

1. **Use uma mensagem curta e descritiva**: As mensagens devem ser curtas (50 caracteres ou menos) e descrever o que foi alterado, por exemplo:

   ```
   git commit -m "Corrige bug na validação de e-mail"
   ```

2. **Use o imperativo presente**: Escreva as mensagens como se estivesse dando uma ordem. Por exemplo, em vez de "Corrigido bug", use "Corrige bug".

3. **Explique o motivo da mudança** (quando necessário): Para commits mais complexos, é uma boa prática adicionar uma explicação mais detalhada com `git commit` sem a flag `-m`, o que abrirá um editor de texto para você explicar as razões e implicações da mudança.

4. **Padronize os prefixos**: Para facilitar a leitura do histórico, utilize prefixos que expliquem a natureza do commit, por exemplo:
   - `feat`: Adição de uma nova funcionalidade.
   - `fix`: Correção de um bug.
   - `docs`: Mudanças na documentação.
   - `style`: Alterações de formatação ou estilo (não afetam a lógica do código).
   - `refactor`: Alterações no código que não corrigem bugs nem adicionam funcionalidades.

   Exemplo:
   ```
   git commit -m "feat: adiciona funcionalidade de login com OAuth"
   ```

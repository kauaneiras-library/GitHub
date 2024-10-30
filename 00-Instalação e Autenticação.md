# Tutorial de Instalação do Git e GitHub Desktop no Ubuntu

Neste tutorial, vamos aprender a instalar o **Git** e o **GitHub Desktop** no Ubuntu usando o terminal. Em seguida, veremos como configurar uma chave **SSH** para permitir que o computador faça alterações em repositórios no GitHub com a sua conta. 

## 1. Instalando o Git no Ubuntu

1. Abra o terminal.
2. Atualize a lista de pacotes:

   ```bash
   sudo apt update
   ```
3. Instale o Git com o comando:

   ```bash
   sudo apt install git -y
   ```
4. Verifique se a instalação foi bem-sucedida:

   ```bash
   git --version
   ```
   Isso deve exibir a versão do Git instalada.

## 2. Instalando o GitHub Desktop no Ubuntu

O GitHub Desktop não está disponível diretamente nos repositórios do Ubuntu, mas podemos instalá-lo utilizando um pacote `.deb`.

1. Primeiro, baixe o GitHub Desktop usando `wget`:

   ```bash
   wget https://github.com/shiftkey/desktop/releases/download/release-3.3.1-linux1/GitHubDesktop-linux-3.3.1-linux1.deb
   ```

   *(Nota: Verifique se existe uma versão mais recente no [GitHub do projeto](https://github.com/shiftkey/desktop/releases))*

2. Instale o GitHub Desktop com o comando:

   ```bash
   sudo apt install ./GitHubDesktop-linux-3.3.1-linux1.deb
   ```

3. Após a instalação, você pode abrir o GitHub Desktop digitando `github-desktop` no terminal ou procurando pelo aplicativo na sua lista de programas.

## 3. Configurando uma Chave SSH para o GitHub

Para permitir que o seu computador se conecte ao GitHub sem a necessidade de inserir a senha em cada operação, vamos criar uma chave SSH.

1. No terminal, crie uma nova chave SSH:

   ```bash
   ssh-keygen -t ed25519 -C "seu-email@example.com"
   ```

   *Substitua `seu-email@example.com` pelo e-mail associado à sua conta do GitHub.*

2. Quando solicitado o local para salvar o arquivo, pressione **Enter** para aceitar o caminho padrão. Você pode também definir uma senha para proteger a chave, mas isso é opcional.

3. Agora, adicione a chave SSH ao agente SSH:

   ```bash
   eval "$(ssh-agent -s)"
   ssh-add ~/.ssh/id_ed25519
   ```

4. Em seguida, copie a chave pública para adicioná-la ao GitHub:

   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```

   Isso imprimirá a chave pública no terminal. Copie o conteúdo.

5. Vá até o [GitHub](https://github.com) e faça login na sua conta.

6. No canto superior direito da tela, clique na sua foto de perfil e depois em **Settings**.

7. No menu à esquerda, clique em **SSH and GPG keys** e depois em **New SSH key**.

8. Cole a chave que você copiou no campo **Key** e dê um nome no campo **Title** (pode ser algo como "Meu Computador Ubuntu").

9. Clique em **Add SSH key**.

10. Para testar a conexão, digite no terminal:

    ```bash
    ssh -T git@github.com
    ```

    Se tudo estiver correto, você verá uma mensagem de boas-vindas do GitHub.

## Conclusão

Agora você tem o **Git** e o **GitHub Desktop** instalados no seu Ubuntu, e configurou uma chave **SSH** para fazer alterações em repositórios do GitHub sem precisar de senha.

Sinta-se à vontade para explorar mais comandos do Git e começar a colaborar em projetos com facilidade!
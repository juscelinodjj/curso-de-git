# Como obter ajuda com comando help

- **Comandos apresentados na aula**
  - ```console
      git help
    ```
  - ```console
      git help -a
    ```
  - ```console
      git help [comando]
    ```
- **Observações**
  - A pasta **html** contendo os arquivos de ajuda não existia, na minha maquina.
  - Corrir o problema baixando a documentação para a seguinte pasta: **/usr/share/doc/git/**
    - ```console
        sudo git clone git://git.kernel.org/pub/scm/git/git-htmldocs.git html
      ```
    - **Detalhes**
      - Distribuição: **Xubuntu 22.04, Jammy Jellyfish (LTS)**
      - Git version: **2.34.1**
- **Comandos adicionais**
  - ```console
      git config --global help.format web
    ```
  - ```console
      git config --global web.browser google-chrome
    ```
- **Documentação online em português**
  - https://git-scm.com/docs/git/pt_BR
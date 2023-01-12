# Como desfazer mudanças com git reset

- **Desfazer mudanças**
  - Às vezes precisamos desfazer alterações realizadas em nossos arquivos locais, após os commits terem sido executados.
  - Existem mais de uma maneira de fazer isso. Uma delas é o emprego do comando git reset.
- **Comando git reset**
  - Sintaxe
  - ```console
      git reset [modo] [arquivo | commit]
    ```
  - O comando git reset permite desfazer alterações.
  - O git reset move os ponteiros HEAD e da branch atual para um estado especificado.
  - Além de atualizar os ponteiros de referência do commit, também pode modificar o estado das três árvores.
- **Principais aplicações do git reset**
  - As principais aplicações do git reset são:
    - Descartar commits em uma branch privada.
    - Desfazer alterações não comitadas, também em uma branch privada.
    - Tirar arquivos da área de stage.
  - Para descartar commits em uma branch pública deve-se usar o comando git revert. Já para descartar alterações no diretório de trabalho, o indicado é o comando git checkout.
- **Modos do git reset**
  - O git reset possui três modos principais de invocação, correspondendo aos três estados internos do git (árvores):
    - --soft
    - --mixed (padrão)
    - -- hard
  - O git reset ainda possui outros modos adicionais:
    - --merge
    - --keep
- **Modos do git reset**
  - **--soft**
    - Não toca no arquivo de índice ou no diretória de trabalho, mas reseta a HEAD para o commit especificado. Muda todos os arquivos para o estado "*Changes to be commited*" **(é modo seguro)**.
  - **--mixed**
    - Reseta o índice mas não a árvore de trabalho e relata o que não foi atualizado. É a ação padrão. Tira o que está no stage, não toca no diretório de trabalho **(é modo seguro)**.
  - **--hard**
    - Reseta o índice e a árvore de trabalho. Quaisquer mudanças em arquivos rastreados na árvore de trabalho desde o commit são descartadas. Descarta o que está na stage area, o que não está, e atualiza o diretório de trabalho **(não é modo seguro)**.
  - **--merge**
    - Reseta o índice e atualiza os arquivos na árvore de trabalho que são diferentes entre o commit e HEAD, mas mantém aqueles que são diferentes entre o índice e a árvore de trabalho. Descarta a stage area, atualiza o diretório de trabalho **(aborta se não for seguro)**.
  - **--keep**
    - Reseta o índice e atualiza arquivos na árvore de trabalho que sejam diferentes entre o commit e HEAD. Se um arquivo que é diferente entre commit e HEAD possui alterações locais, o reset é abortado. Tira o que está na stage area, atualiza o diretório de trabalho **(aborta se não for seguro)**.
- **Git reset x git revert**
  - O git revert é projetado para desfazer de forma segura um commit público, ao passo que o git reset é projetado para desfazer alterações locais no stage e no diretório de trabalho.
  - Já o git reset remove completamente um conjunto de alterações, ao passo que o git revert mantém as alterações originais, criando um novo commit para desfazê-las.
  - Não se recomenda usar git reset quando um snapshot foi enviado a um repositório público - outros *devs* se baseiam no commit...[trecho ilegível]...
- **Exemplos**
  - ```console
      git reset
    ```
    - Reseta a staging area (tira todos os arquivos) para corresponder ao commit mais recente, sem modificar o diretório de trabalho.
  - ```console
      git reset --hard
    ```
    - Reseta a staging area e o diretório de trabalho para corresponder ao commit mais recente. Todas as alterações no diretório são sobrescritas.
  - ```console
      git reset [nome do arquivo]
    ```
    - Tira o [arquivo] da staging area, sem modificar o diretório de trabalho.
  - ```console
      git reset [hash do commit]
    ```
    - Move a branch atual para o commit indicado, reseta a staging area para corresponder a ele, mas não altera o diretório de trabalho.
  - ```console
      git reset --hard [hash do commit]
    ```
    - Move a branch atual para o commit indicado, e reseta tanto a staging area quanto o diretório de trabalho, para que correspondam ao commit.
# Como reverter commits com git revert

- **Reverter Commits**
  - Eventualmente você terá a necessidade de reverter um commit, por exemplo por conta de erros cometidos nos arquivos.
  - Desfazer um commit é basicamente comitar exatamente o oposto do commit em si. O Git na prática, cria um novo commit com as mudanças opostas.
  - Para tal usamos o comando git revert.
  - Com o git revert podemos desfazer as mudanças em um commit, mantendo alterações posteriores intactas.
  - Os arquivos retornam ao mesmo estado como se o commit revertido nunca tivesse existido.
  - O git reverse é, em si, um commit. Por isso, não é necessário fazer mais nada após executar esse comando.
- **Comando git revert**
  - Sintaxe
  - ```console
      git revert [hash do commit]
    ```
  - Para reverter especificamente o último commit podemos usar também:
  - ```console
      git revert HEAD
    ```
- **Cancelar uma operação revert**
  - Cancelar uma operação git revert com erros:
  - ```console
      git revert --abort
    ```
- **Regras importantes**
  - Deve-se trabalhar em um diretório de trabalho limpo. Executar sempre git add e git commit antes de tentar reverter um commit.
  - Novamente: não mude o passado - ao menos não por enquanto!
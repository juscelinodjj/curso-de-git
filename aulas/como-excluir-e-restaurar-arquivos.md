# Como excluir e restaurar arquivos

- **Comandos apresentados na aula**
  - Excluir arquivo
  - ```console
      git rm [nome do arquivo]
    ```
  - Listar arquivos deletados
  - ```console
      git log --diff-filter=D --summary
    ```
  - Restaurar arquivo deletado
  - ```console
      git checkout [nome do commit]~1 [nome do arquivo]
    ```
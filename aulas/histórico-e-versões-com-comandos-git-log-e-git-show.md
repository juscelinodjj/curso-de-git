# Histórico e versões com comandos git log e git show

- **Log do Commit**
  - O log do commit lista as seguintes informações.
    - Nome do commit (via hash)
    - Autor
    - Email
    - Data
    - Descrição
- **Visualizar alterações realizadas**
  - Podemos visualizar as alterações realizadas nos arquivos de um projeto, com detalhes, usando o comando git show.
  - O nome do commit pode ser obtido com o comando git log, e basta usar a partir dos quatros primeiros caracteres para realizar a consulta. Se não fornecido, serão mostrados detalhes do último arquivo consolidado.
- **Comandos apresentados na aula**
  - ```console
      git log [nome do arquivo]
    ```
  - ```console
      git show [nome do commit]
    ```
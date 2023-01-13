# Ignorar arquivos com arquivo gitignore

- **Ignorar arquivos**
  - Ao comitar arquivos em um repositório, pode acontecer de haver alguns arquivos que não queremos ou devemos incluir no commit.
  - Para evitar que esses arquivos sejam comitados por engano, podemos usar um arquivo especial que indica ao Git que determinados arquivos devem ser ignorados, e não rastreados.
  - Para  tal usamos um arquivo .gitignore.
- **Arquivo .gitignore**
  - Um arquivo .gitignore é um arquivo de texto plano no qual cada linha especifica um padrão de arquivos ou diretórios a ignorar.
  - Geralmente, o colocamos no diretório raiz de um repositório, mas é possível colocá-lo em outro lugar (mas não recomendado).
- **Quais arquivos ignorar?**
  - Recomendamos ignorar arquivos do tipo como:
    - Arquivos de log.
    - Arquivos que contenham senhas, credenciais ou informações confidenciais.
    - Arquivos de sistema e temporários.
    - Arquivos gerados, como executáveis de teste.
    - Saídas compiladas (executáveis, etc).
    - Arquivos pessoais.
    - Entre outros.
- **Arquivo .gitignore global**
  - Podemos criar um arquivo global para ignorar arquivos e diretórios em todos os projetos simultaneamente:
  - ```console
      touch ~/.gitignore
    ```
  - ```console
      git config --global core.excludesFile ~/.gitignore
    ```
  - Agora todos os repositórios git ignoram os arquivos colocados no arquivo **~/.gitignore** - que é global.
- **Padrões de correspondência**
  - Nomes de arquivos literais
    - tempArq
  - Diretórios
    - temp/
  - Caracteres-curinga
    - \* : Zero ou mais caracteres (exceto /).
    - ? : Um único  caractere (exceto /).
    - ! : Negação (nega ignore).
    - \# : Comentários no arquivo gitignore.
- **Exemplos de padrões**
  - **arqTeste** : Ignora o arquivo (ou diretório) arqTeste.
  - **\*.log** : Ignora todos os arquivos com extensão .log.
  - **arq\*** : Ignora todos os arquivos iniciados com arq.
  - **?rq** : Ignora todos os arquivos não importando o primeiro caractere, mas que possua rq na sequência.
  - **dirTest**/ : Ignora o diretório dirTest e seus arquivos.
  - **\*\*/dirTeste** : Ignora todos os diretórios de nome dirTeste.
  - **!saída.log** : Não ignora o arquivo saída.log.
- **Dicas importantes**
  - Não é necessário comitar o próprio arquivo .gitignore, a não ser que queira compartilhar suas entradas com outros usuários no projeto.
  - Mas é recomendável!
  - Evite criar muitos arquivos .gitignore. Se possível, trabalhe com arquivo global.
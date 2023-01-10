# Comandos Úteis

Lista de comando úteis.

## GIT

- Configurar usuário e email para commits no repositório;
  - ```git config user.name "Ezequiel da Silva Oliveira"```
  - ```git config user.email "95730033+EzequielSOliveira@users.noreply.github.com"```
- Clonar repositório git;
 - ```git clone git@github.com:EzequielSOliveira/temp.git```
- Excluir uma branch.
  - ```git branch --delete branch_name```
- Restaurar o repositório a partir de um commit específico
  - ```git reset --hard 1dcd88d2248d990a6dbeb840fbf0315732016343```
  - ```git reset --soft "HEAD@{1}"```
  - ```commit -m "1dcd88d2248d990a6dbeb840fbf0315732016343"```
- Multiplas linhas na mensagem do commit:
  - ```
    git commit -m "this is
    > a line
    > with new lines
    > maybe"
    ```

## MySQL (instalado manualmente pelo ZIP)

- Gerar bases de dados padrão do MySQL na primeira inicialização;
  - ```mysqld --initialize-insecure --console```
- Iniciar MySQL;
  - ```mysqld --console```
- Executar comandos diretamente no SGBD (a senha padrão é em branco);
  - ```mysql -u root -p```
- Alterar senha do usuário root para root.
  - ```mysql -u root -p```
  - ```ALTER USER 'root'@'localhost' IDENTIFIED BY 'root';```
  - ```FLUSH PRIVILEGES;```

## Visual Studio Code

- Utilize o comando a seguir para indentar o código fonte.
  - ```SHIFT + ALT + F```

# Convenção de Commits

É recomendado utilizar a convenção **Conventional Commits** na mensagem de commits.

A especificação **Conventional Commits** é uma convenção leve sobre as mensagens de confirmação. Ela fornece um conjunto fácil de regras para criar um histórico de confirmação explícito; o que facilita a escrita de ferramentas automatizadas.

https://www.conventionalcommits.org

A mensagem de confirmação deve ser estruturada da seguinte forma:

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

Tipos recomendados:
```build:, chore:, ci:, docs:, feat:, fix:, perf:, refactor:, revert:, style:, test:```

Descrição dos Tipos:

- **build**: alterações que afetam o sistema de compilação ou dependências externas
- **ci**: alterações em nossos arquivos e scripts de configuração de CI
- **docs**: alteração na documentação
- **feat**: um novo recurso
- **fix**: uma correção de bug
- **perf**: uma mudança de código que melhora o desempenho
- **refactor**: uma alteração de código que não corrige um bug nem adiciona um recurso
- **style**: alterações que não afetam o significado do código (espaço em branco, formatação, falta de ponto-e-vírgula etc.)
- **test**: adicionando testes ausentes ou corrige testes existentes

## Exemplos de Commits

Mensagem de commit sem corpo
```docs: correct spelling of CHANGELOG```

Mensagem de commit com multiplos parágrafos no copor e rodapé
```
fix: prevent racing of requests

Introduce a request id and a reference to latest request. Dismiss
incoming responses other than from latest request.

Remove timeouts which were used to mitigate the racing issue but are
obsolete now.

Reviewed-by: Z
Refs: #123
```
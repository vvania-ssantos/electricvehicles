# produtos
Minha primeira API
# Minha Primeira API PHP

Este projeto é uma API simples feita em PHP que se conecta a um banco de dados MySQL para buscar informações. Ela foi feita para estudos e para testar como APIs funcionam!

## O Que Tem Aqui?

* `conn.php`: Onde a API se conecta ao banco de dados.
* `model.php`: Onde a API busca os dados do banco de dados (no seu caso, da tabela `cidade`).
* `index.php`: O "coração" da API, que recebe os pedidos e mostra os dados.

## Como Fazer Funcionar (No Seu Computador)

1.  **Tenha o PHP e o MySQL:** Você precisa ter o XAMPP, WAMP, MAMP ou só o PHP e MySQL instalados.
2.  **Salve os arquivos:** Coloque a pasta `produtos` (com `conn.php`, `model.php`, `index.php` dentro) em algum lugar que seu servidor PHP possa ver. Por exemplo, se você usa o XAMPP, coloque em `C:\xampp\htdocs\`.
3.  **Crie o banco de dados:**
    * Abra o MySQL (pode ser pelo phpMyAdmin no XAMPP).
    * Crie um banco de dados chamado `meu primeiro banco`.
    * Crie uma tabela chamada `cidade` dentro dele. Você pode usar este comando SQL:
        ```sql
        CREATE TABLE IF NOT EXISTS ´produto' (
            id_produto INT AUTO_INCREMENT PRIMARY KEY,
            produto VARCHAR(255) NOT NULL,
            id_lojavirtual INT
        );
        ```
    * **Importante:** Verifique se as informações de usuário e senha do banco de dados no seu arquivo `conn.php` estão corretas (normalmente `user = "root"` e a senha que você usa para o MySQL, que no seu caso é `"aquela que você fez quando criou para entrar no banco de dados"`).
4.  **Ligue o servidor PHP:**
    * Abra o **terminal** (no VS Code, vá em `Terminal > New Terminal`).
    * Vá até a pasta `MinhasuperLoja` usando o comando `cd`:
        ```bash
        cd C:\Users\seu user\Downloads\MinhasuperLoja
        ```
        (Mude o caminho se sua pasta estiver em outro lugar)
    * Agora, ligue o servidor:
        ```bash
        php -S localhost:8000
        ```
    * Deixe este terminal **aberto**!

## Como Usar a API (No Navegador)

Depois que o servidor estiver ligado, abra seu navegador (Chrome, Firefox, Edge) e digite a seguinte URL:

`http://localhost:8000/index.php?action=list`

**O que você deve ver:**

* Se tudo estiver certo e você tiver mercadorias no seu banco de dados, vai aparecer um monte de texto parecido com:
    ```json
    [
        {"id_produto": "1", "meia": "ARTIGOS ESPORTIVOS", "id_lojavirtual": "26"},
        {"id_produto": "2", "bolsa": "ACESSÓRIOS", "id_lojavirtual": "19"}
    ]
    ```
* Se não tiver nenhum produto cadastrado na tabela, vai aparecer só a palavra: `"notfound"`
* Se aparecer alguma mensagem de erro do PHP ou "Site não pode ser alcançado", algo está errado na configuração (veja os passos acima de novo, principalmente o "Ligue o servidor PHP").





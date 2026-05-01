# Pesquisa-DAO-JDBC

## MVC — Model View Controller

O MVC é um padrão de arquitetura que divide a aplicação em três camadas, cada uma com uma função bem definida:

## View (Visão)

É a interface gráfica (telas, menus, botões).
Tudo o que o usuário enxerga e com o que interage.

## Controller (Controle)

Faz a "ponte" entre View e Model.
Interpreta ações do usuário e decide o que fazer (exemplo: cadastrar, buscar, atualizar).

## Model (Modelo)

Representa os dados e regras de negócio.
Guarda informações como nome, CPF, senha e outras entidades do sistema.

## DAO — Data Access Object

O DAO é um padrão de projeto criado para separar:

Regra de negócio (Model, Controller)
de
Regra de persistência (banco de dados)

Ou seja, o DAO define como os dados serão salvos, atualizados, removidos ou buscados, enquanto o Model continua com suas regras intactas.

Exemplo simples:

O Model diz que um cliente que compra 10 produtos ganha 10% de desconto.
O DAO apenas decide como salvar ou buscar esse cliente no banco.

## JDBC — Java Database Connectivity

O JDBC é uma API do Java que permite a comunicação com bancos de dados.

Ele funciona como um intérprete entre o Java e o MySQL:

Java fala “Inglês”
MySQL fala “Japonês”
JDBC é o tradutor entre os dois
Recursos utilizados:
Driver
DriverManager
PreparedStatement
ResultSet
Connection

## Mapa Conceitual (Visual e organizado)
                         [ USUÁRIO ]
                              |
                           interage
                              |
                            [ VIEW ]
                         (telas/menus)
                              |
                           chama ações
                              |
                        [ CONTROLLER ]
                     (coordena o fluxo)
                      /               \
                consulta              atualiza
                    |                   |
                [ MODEL ]           [ VIEW ]
         (dados e regras)      (exibe resultado)
                    |
                 acessa via
                    |
                   [ DAO ]
        (operações: insert, update, delete, select)
                    |
                usa conexão da
                    |
         [ ConnectionFactory ]
       (abre/fecha conexão JDBC)
                    |
                  conecta
                    |
               [ MySQL / Banco ]

               
## Estrutura de Pastas (Template Padrão — Maven)
projeto-dao-base/
├─ pom.xml
├─ README.md
└─ src/
   ├─ main/
   │  ├─ java/
   │  │  └─ br/escola/dao_base/
   │  │     ├─ app/
   │  │     │  └─ Main.java
   │  │     ├─ model/
   │  │     │  └─ (entidades do tema entram depois)
   │  │     ├─ dao/
   │  │     │  └─ (interfaces DAO entram depois)
   │  │     ├─ dao/impl/
   │  │     │  └─ (implementações JDBC entram depois)
   │  │     └─ db/
   │  │        ├─ ConnectionFactory.java
   │  │        └─ DbException.java
   │  └─ resources/
   │     ├─ db.properties
   │     └─ sql/
   │        ├─ schema.sql
   │        └─ seed.sql
   └─ test/
      └─ java/ (opcional)

      
## Fontes de Pesquisa

https://www.devmedia.com.br/introducao-ao-padrao-mvc/29308

https://www.devmedia.com.br/dao-pattern-persistencia-de-dados-utilizando-o-padrao-dao/30999

https://www.imperva.com/learn/application-security/business-logic/

https://www.blip.ai/blog/tecnologia/persistencia-de-dados/

https://www.alura.com.br/artigos/conhecendo-o-jdbc

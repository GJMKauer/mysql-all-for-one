# Boas vindas ao repositório do projeto <b>MYSQL All For One</b>!

Esse projeto foi desenvolvido durante o módulo de Backend na Trybe! #vqv 

Aqui você vai encontrar os detalhes de como foi o desenvolvimento do projeto e quais foram os requisitos técnicos necessários para a entrega do desafio.

---

# Habilidades desenvolvidas

Neste projeto, fui capaz de:

- Praticar todos os conceitos de MYSQL aprendidos até o momento;
- Utilizar banco de dados Northwind;
- Utilizar comandos como SELECT, COUNT, LIMIT, OFFSET, ORDER BY, AS, INSERT, UPDATE e DELETE.

---

# Funcionamento da aplicação

Para iniciar o projeto, é necessário possuir o [Docker](https://docs.docker.com/engine/install/ubuntu/) e o [MySQL Workbench](https://dev.mysql.com/downloads/workbench/) instalados no computador.

O projeto trata-se de um desafio para consolidar o aprendizado com os comandos iniciais mais básicos do MySQL, fazendo a busca, atualização, inserção e remoção de dados no Banco de Dados Northwind.

Após clonar o projeto em seu computador, para iniciá-lo é necessário executar o comando
```
docker-compose up -d && docker exec -it all_for_one bash
```
e na sequência
```
npm install
```

na pasta raíz do projeto. Isso fará com que os containers docker sejam orquestrados e a aplicação esteja disponível. Após isso, será necessário restaurar o banco de dados `Northwind` para rodar os comandos.

<br>

<details>
  <summary><strong>🗒️ Instruções para restaurar o banco de dados `Northwind`</strong></summary><br />

1. Faça o download do arquivo de backup [aqui](northwind.sql) clicando em "Raw", depois clicando com botão direito e selecionando "Salvar como" para salvar o arquivo em seu computador.
2. Abra o arquivo com algum editor de texto e selecione todo o conteúdo do arquivo usando `CTRL-A`.
3. Abra o MySQL Workbench.
4. Crie uma conexão local no MySQL Workbench utilizando o hostname `localhost`, a porta `3306`, o usuário `root` e a senha `password`.
5. Abra uma nova janela de query e cole dentro dela todo o conteúdo do arquivo `northwind.sql`.
6. Selecione todo o código com o atalho `CTRL-A` e depois clique no ícone de raio para executar a query.

    ![Restaurando o banco Northwind](images/restore_northwind.png)
7. Aguarde alguns segundos (espere em torno de 30 segundos antes de tentar fazer algo).
8. Clique no botão apontado na imagem a seguir para atualizar a listagem de banco de dados.

    ![Tabelas do banco Northwind](images/refresh_databases.png)
9. Verifique se o banco restaurado possui todas as seguintes tabelas:

    ![Tabelas do banco Northwind](images/northwind.png)
10. Clique com botão direito em cada tabela e selecione "Select Rows" e certifique-se que todas as tabelas possuem registros. Caso tenha alguma faltando, faça o passo a seguir. Caso contrário, pode ir para próxima seção.
11. Caso existam tabelas faltando, drope o banco de dados clicando com o botão direito em cima do banco de dados northwind e selecionando "Drop Schema" e refaça os passos novamente, dessa vez aguardando um tempo maior quando executar o script de restauração.

    ![Drop Schema](images/drop_database.png)

</details>

<br>

Feita a restauração do banco, você pode executar as _queries_ descritas em cada arquivo `desafioN.sql` desse projeto.

<br> 

---

# Histórico de Commits

É possível verificar todo o histórico de commits do projeto, de modo a visualizar passo-a-passo como foi desenvolvido o meu raciocínio até a finalização do projeto.

---

# Requisitos técnicos do desafio:

- ✅ 1. Exiba apenas os nomes dos produtos na tabela products.

- ✅ 2. Exiba os dados de todas as colunas da tabela products.

- ✅ 3. Escreva uma query que exiba os valores da coluna que representa a primary key da tabela products.

- ✅ 4. Conte quantos registros existem na coluna product_name da tabela products.

- ✅ 5. Monte uma query que exiba os dados da tabela products a partir do quarto registro até o décimo terceiro.

- ✅ 6. Exiba os dados das colunas product_name e id da tabela products de maneira que os resultados estejam em ordem alfabética dos nomes.

- ✅ 7. Mostre apenas os ids dos 5 últimos registros da tabela products (a ordernação deve ser baseada na coluna id).

- ✅ 8. Faça uma consulta que retorne três colunas, respectivamente, com os nomes 'A', 'Trybe' e 'eh', e com valores referentes a soma de '5 + 6', a string 'de', a soma de '2 + 8'.
  
- ✅ 9. Mostre todos os valores de notes da tabela purchase_orders que não são nulos.

- ✅ 10. Mostre todos os dados da tabela purchase_orders em ordem decrescente, ordenados por created_by em que o created_by é maior ou igual a 3.

- ✅ 11. Exiba os dados da coluna notes da tabela purchase_orders em que seu valor de Purchase generated based on Order é maior ou igual a 30 e menor ou igual a 39.

- ✅ 12. Mostre as submitted_date de purchase_orders em que a submitted_date é do dia 26 de abril de 2006.

- ✅ 13. Mostre o supplier_id das purchase_orders em que o supplier_id seja 1 ou 3.

- ✅ 14. Mostre os resultados da coluna supplier_id da tabela purchase_orders em que o supplier_id seja maior ou igual a 1 e menor ou igual 3.

- ✅ 15. Mostre somente as horas (sem os minutos e os segundos) da coluna submitted_date de todos registros da tabela purchase_orders.

- ✅ 16. Exiba a submitted_date das purchase_orders que estão entre 2006-01-26 00:00:00 e 2006-03-31 23:59:59.

- ✅ 17. Mostre os registros das colunas id e supplier_id das purchase_orders em que os supplier_id sejam tanto 1, ou 3, ou 5, ou 7.

- ✅ 18. Mostre todos os registros de purchase_orders que tem o supplier_id igual a 3 e status_id igual a 2.

- ✅ 19. Mostre a quantidade de pedidos que foram feitos na tabela orders pelo employee_id igual a 5 ou 6, e que foram enviados através do método(coluna) shipper_id igual a 2.
  
- ✅ 20. Adicione à tabela order_details um registro com order_id: 69, product_id: 80, quantity: 15.0000, unit_price: 15.0000, discount: 0, status_id: 2, date_allocated: NULL, purchase_order_id: NULL e inventory_id: 129.

- ✅ 21. Adicione com um único INSERT, duas linhas à tabela order_details com os mesmos dados do requisito 20.

- ✅ 22. Atualize os dados de discount do order_details para 15. (Não é necessário utilizar o SAFE UPDATE em sua query).

- ✅ 23. Atualize os dados da coluna discount da tabela order_details para 30, onde o valor na coluna unit_price seja menor que 10.0000.

- ✅ 24. Atualize os dados da coluna discount da tabela order_details para 45, onde o valor na coluna unit_price seja maior que 10.0000 e o id seja um número entre 30 e 40.
  
- ✅ 25. Delete todos os dados em que a unit_price da tabela order_details seja menor que 10.0000.

- ✅ 26. Delete todos os dados em que a unit_price da tabela order_details seja maior que 10.0000.

- ✅ 27. Delete todos os dados da tabela order_details.
<h1 align="center"> Jornada MySQL <img align="center" src="https://skillicons.dev/icons?i=mysql" height="50" alt="mysql logo" /></h1>
<br>
<h2>Sobre mim e a Jornada MySQL:</h2>

Prazer, podem me chamar de Nan! Atualmente estou cursando T.I. e decidi compartilhar e "documentar" meus aprendizados sobre MySQL por meio desse repositório!
Esse projeto foi fortemente inspirado pela [Jornada JavaScript](https://github.com/JoaoGomeszs/Jornada-JavaScript), do meu extremamente talentoso amigo e colega de curso: [João Gomes](https://github.com/JoaoGomeszs/)!

A Jornada MySQL está ativamente recebendo novas atualizações, modificações e correções ao longo do tempo para garantir que todos os conteúdos apresentados sejam fáceis e simples de se entender, mas eficientes e práticos para serem consultados.

> [!IMPORTANT]
> - Ao longo da jornada, estarei utilizando o realce de sintaxe do SQL nos blocos de código para facilitar a visualização de certos comandos, declarações, tabelas, etc.
> - <b>A "Jornada MySQL" foi criada para auxiliar e documentar apenas o meu aprendizado pessoal sobre o sistema, e não deve ser vista como uma substituição e/ou alternativa das documentações oficiais.</b> [Consulte a documentação oficial do MySQL por aqui.](https://dev.mysql.com/doc/)

<br>
<details>
<summary>Tabela de conteúdos (Clique para mostrar)</summary>

- [Introdução](#introdução)
    - [XAMPP](#xampp)
    - [Iniciando o MySQL](#iniciando-o-mysql)
- [Sintaxe Básica e Boas Práticas](#sintaxe-básica-e-boas-práticas)
    - [Sintaxe básica](#sintaxe-básica)
    - [Boas práticas](#boas-práticas)
- [Ferramentas Recomendadas](#ferramentas-recomendadas)
    - [DB Designer e dbdiagram.io](#db-designer-e-dbdiagramio-sites)
    - [MySQL (Extensão do VS Code)](#mysql-extensão-do-vs-code)
    - [DBeaver (Aplicativo)](#dbeaver-aplicativo)
- [Visualizando, criando e utilizando um banco de dados](#visualizando-criando-e-utilizando-um-banco-de-dados)
    - [Visualizar os bancos de dados já criados](#comando-para-visualizar-os-bancos-de-dados-já-criados)
    - [Criar um novo banco de dados](#comando-para-criar-um-novo-banco-de-dados)
    - [Utilizar o banco de dados desejado](#comando-para-utilizar-o-banco-de-dados-desejado)
- [Tipos de dados](#tipos-de-dados)
    - [Numéricos (Numerics)](#numéricos-numerics)
    - [Cadeia de caracteres (String)](#cadeia-de-caracteres-string)
    - [Temporais (Date and Time)](#temporais-date-and-time)
- [Visualizando, criando e descrevendo uma tabela](#visualizando-criando-e-descrevendo-uma-tabela)
    - [Visualizar as tabelas já criadas no banco de dados](#visualizar-as-tabelas-já-criadas-no-banco-de-dados)
    - [Criar uma nova tabela](#criar-uma-nova-tabela)
    - [Descrever as informações da tabela](#descrever-as-informações-da-tabela--exemplo-visual)
- [Inserindo e selecionando valores de uma tabela](#inserindo-e-selecionando-valores-de-uma-tabela)
    - [Inserir novos valores em uma tabela](#inserir-novos-valores-em-uma-tabela)
    - [Selecionando valores de uma tabela](#selecionando-valores-de-uma-tabela)
        - [Selecionar valores de uma tabela de forma ordenada](#selecionar-valores-de-uma-tabela-de-forma-ordenada) 
- [Incremento Automático (AUTO_INCREMENT)](#incremento-automático-auto_increment)
    - [Não Nulo (NOT NULL)](#não-nulo-not-null)
    - [Chave Primária (PRIMARY KEY)](#chave-primária-primary-key)
    - [Criando uma tabela com coluna de incremento automático](#criando-uma-tabela-com-coluna-de-incremento-automático)
- [Alterar Tabela (ALTER TABLE)](#alterar-tabela-alter-table)
    - [Adicionar nova coluna em uma tabela](#adicionar-nova-coluna-em-uma-tabela)
    - [Deletar coluna existente de uma tabela](#deletar-coluna-existente-de-uma-tabela)
    - [Mudando o nome e tipo de uma coluna na tabela](#mudando-o-nome-e-tipo-de-uma-coluna-na-tabela)
- [Atualizando as informações de uma tabela (UPDATE)](#atualizando-as-informações-de-uma-tabela-update)
    - [Condições](#condições)
        - [Definir (SET)](#definir-set)
        - [Onde (WHERE)](#onde-where)
    - [Atualizar as informações de uma tabela](#atualizar-as-informações-de-uma-tabela)
- [Operadores do "WHERE"](#operadores-do-where)
    - [Correspondente (LIKE)](#correspondente-like)
    - [E/Ou (AND/OR)](#eou-andor)
</details>

<h2 align="center">Introdução</h2>
<h3>XAMPP</h3>
Esse repositório foi inicialmente criado e planejado com a utilização da compilação de softwares livres <strong>XAMPP</strong> como base, então resultados e algumas instruções podem variar.

<h3>Iniciando o MySQL</h3>
<ul>
  <li>Abra o XAMPP Control Panel, procure pelo módulo "MySQL" e clique em "Start". Após isso, clique no botão "Shell" para abrir o CMD;</li>
  <li>Na janela recém-aberta do CMD, insira o seguinte comando:</li>
</ul> 

```cmd
mysql -h localhost -u root -p
```

> [!NOTE]
> - Ao inserir esse comando, o CMD solicitará uma senha (Enter password: );<br>
> - Por padrão, basta apenas apertar a tecla "ENTER" para ter acesso ao MySQL (MariaDB).

<h2 align="center">Sintaxe Básica e Boas Práticas</h2>
<h3>Sintaxe básica:</h3>
<ul>
  <li>Todos os comandos precisam ser finalizados com ponto e vírgula (;);</li><br>
  <li>Ao inserir uma linha de comando incompleta, o CMD exibirá uma setinha (->):<br>
      Ela serve para inserir o restante do comando, sem a necessidade de reescrevê-lo;</li><br>
  <li>Ao finalizar uma linha de comando com erro(s), uma mensagem de erro será exibida no CMD:<br>
      Caso um ou vários erros sejam exibidos, será necessário reescrever todo o comando novamente, de forma correta;</li><br>
  <li>Caracteres especiais não são reconhecidos por padrão e serão exibidos como "?", mas podem ser habilitados!</li>
</ul>

<h3>Boas práticas:</h3>
<ul>
  <li>Comandos do MySQL sempre em letras maiúsculas (UPPERCASE);</li>
  <li>Nomes atribuídos ao banco de dados, tabelas, tipos de dados, etc. sempre em letras minúsculas (lowercase).</li>
</ul>

<h2 align="center">Ferramentas Recomendadas</h2>
<h3>DB Designer e dbdiagram.io (Sites)</h3>

Para criar diagramas entidade-relacionamento (DER) do banco de dados MySQL, estarei inicialmente utilizando o site [DB Designer](https://www.dbdesigner.net/) por sua intuitividade, mas o [dbdiagram.io](https://dbdiagram.io/home) é a opção mais recomendada.

<h3>MySQL (Extensão do VS Code)</h3>

Facilitando o gerenciamento do banco de dados por meio de uma extensão para o Visual Studio Code distribuída pela Database Client, o [MySQL](https://marketplace.visualstudio.com/items?itemName=cweijan.vscode-mysql-client2) é uma ferramenta prática e conveniente, mas necessita de alguns passos e configurações para o seu funcionamento adequado:

- Após instalar a extensão, certifique-se de que o banco de dados MySQL está inicializado por meio do XAMPP Control Panel;
- Dois novos ícones devem aparecer na barra lateral do VS Code, clique no ícone de cilindro "Database";
- Na seção Database, clique em "Create Connection" e copie as seguintes configurações:<br><br>
    - Server Type: MySQL
    - Host: localhost
    - Port: 3306
    - Username: root<br><br>
- Agora, clique em "Connect" e a extensão deve estar pronta para gerenciar o banco de dados!

> [!WARNING]
> A documentação da Jornada MySQL não foi pensada e/ou adaptada para a extensão "MySQL", do Visual Studio Code. Todos os comandos ainda podem ser realizados por meio da extensão, mas por sua conta e risco.

<h3>DBeaver (Aplicativo)</h3>

Para gerenciar o banco de dados de forma prática e intuitiva, o aplicativo para desktop [DBeaver](https://dbeaver.io/) é uma ferramenta extremamente útil, com várias funcionalidades e recomendada para projetos pessoais!

<h2 align="center">Visualizando, criando e utilizando um banco de dados</h2>
<p align="center">PS: Estarei utilizando o nome "db_github" como exemplo, mas pode ser qualquer nome!</p>
<h4>Comando para visualizar os bancos de dados já criados:</h4>

```sql
SHOW DATABASES;
```

<h4>Comando para criar um novo banco de dados:</h4>

```sql
CREATE DATABASE db_github;
```

<h4>Comando para utilizar o banco de dados desejado:</h4>

```sql
USE db_github;
```

<h2 align="center">Tipos de dados</h2>
<h3>Até o momento, utilizei os seguintes tipos de dados:</h3>

<h4>Numéricos (Numerics):</h4>
<ul>
  <li><b>INTEGER()</b> ou <b>INT()</b></li>
  Utilizado para valores exatos e inteiros, declarado em conjunto de um limite máximo de casas numéricas dentro do parênteses;<br>
  Exemplo: INT(2) - Limita a quantidade de casas numéricas para 2, então 99 seria aceito, mas 100 não.<br><br>
  <li><b>DECIMAL()</b></li>
  Utilizado para valores quebrados (números com vírgula), declarado em conjunto de um limite máximo de casas numéricas dentro dos parênteses.
  O primeiro valor declarado dentro do parênteses será o limite de casas numéricas antes e após a vírgula, e o segundo será o limite de casas depois da vírgula;<br>
  Exemplo: DECIMAL(4,2) - Limita a quantidade de casas numéricas antes e após a vírgula para 4, enquanto as casas após a vírgula serão limitadas para 2.
</ul>

> [!NOTE]
> Ao inserir valores do tipo numérico, não os colocar dentro de aspas.

<h4>Cadeia de caracteres (String):</h4>
<ul>
  <li><b>VARCHAR()</b></li>
  Utilizado para armazenar uma sequência de caracteres com tamanhos variados, declarado em conjunto de um limite de caracteres dentro do parênteses;<br>
  Exemplo: VARCHAR(50) - Limita a quantidade máxima de caracteres para 50;<br>
</ul>

> [!NOTE]
> Ao inserir valores do tipo string, sempre os coloque dentro de aspas ("").

<h4>Temporais (Date and Time):</h4>
<ul>
  <li><b>DATE</b></li>
  Um tipo de dado para valores de datas no formato internacional (YYYY-MM-DD);<br>
  Ao inserir valores do tipo DATE, sempre os coloque dentro de aspas (""), ou serão exibidos como 0000-00-00.
</ul>

<h2 align="center">Visualizando, criando e descrevendo uma tabela</h2>
<p align="center">PS: Estarei simplificando a descrição de cada comando para não precisar repetir a palavra "comando" toda hora!</p>
<p align="center">PPS: Estarei utilizando o nome "tb_pessoas" como exemplo, mas pode ser qualquer nome!</p>
<h4>Visualizar as tabelas já criadas no banco de dados:</h4>

```sql
SHOW TABLES;
```

<h3>Criar uma nova tabela:</h3>

> [!IMPORTANT]  
> - Ao criar uma nova tabela, ao menos uma coluna também precisa ser criada;<br>
> - Os nomes e tipos de dados das colunas devem ser todos declarados dentro de parênteses ();<br>
> - Para criar várias colunas no mesmo comando, separe-as com vírgulas (,).

```sql
CREATE TABLE tb_pessoas(exemplo_nome VARCHAR(50), exemplo_idade INT(3));
```

<h4>Descrever as informações da tabela (+ Exemplo visual):</h4>

```sql
DESC tb_pessoas;
```

```sql
+---------------+-------------+------+-----+---------+-------+
| Field         | Type        | Null | Key | Default | Extra |
+---------------+-------------+------+-----+---------+-------+
| exemplo_nome  | varchar(50) | YES  |     | NULL    |       |
| exemplo_idade | int(3)      | YES  |     | NULL    |       |
+---------------+-------------+------+-----+---------+-------+
```

> [!WARNING]
> A tabela acima não deve ser copiada, e serve apenas para visualizar como seria o resultado do comando "DESC"!

<h2 align="center">Inserindo e selecionando valores de uma tabela</h2>

<h3>Inserir novos valores em uma tabela:</h3>

> [!IMPORTANT]
> - Para inserir um novo valor (linha) em uma tabela, é necessário atribuí-lo a pelo menos uma coluna;
> - Exemplo: Valores que representam uma pessoa seriam atribuídos às colunas "nome" e "idade";
> - Os valores devem ser separados por vírgula e colocados em ordem, como no exemplo abaixo: 

```sql
INSERT INTO tb_pessoas (exemplo_nome, exemplo_idade) VALUE ("Nan", 19);
```

- Para inserirmos mais de um valor em uma tabela no mesmo comando, utilizamos a declaração "VALUES", como no exemplo abaixo:

```sql
INSERT INTO tb_pessoas (exemplo_nome, exemplo_idade) VALUES ("Nan", 19), ("Nana", 20);
```

<h3>Selecionando valores de uma tabela:</h3>

> [!TIP]
> - O comando "SELECT" serve para visualizar os valores de uma tabela;
> - Pode ser usado para visualizar todos os valores inseridos, ou valores específicos;

<h4>Selecionar todos os valores da tabela:</h4>

```sql
SELECT * FROM tb_pessoas;
```

<h4>Selecionar valores específicos de uma tabela pelas colunas:</h4>
<ul>
    <li>Selecionar todos os valores da tabela "tb_pessoas" que foram atribuídos na coluna "exemplo_nome":</li>
</ul>

```sql
SELECT exemplo_nome FROM tb_pessoas;
```

<h4>Selecionar valores específicos de uma tabela pelas suas atribuições:</h4>
<ul>
    <li>Selecionar todos os valores da tabela que possuem a coluna "exemplo_nome" atribuída como "Nan":</li>
</ul>

```sql
SELECT * FROM tb_pessoas WHERE exemplo_nome = “Nan”;
```

<h3>Selecionar valores de uma tabela de forma ordenada:</h3>
Para selecionarmos os valores de uma tabela e os visualizarmos de forma ordenada, utilizamos a condição "ORDER BY" em conjunto das palavras-chaves "<b>ASC</b>" (Padrão ao executar o "ORDER BY", ordem crescente) e "<b>DESC</b>" (Ordem decrescente) da seguinte forma:<br><br>

<ul>
    <li>Selecionar todos os valores da tabela e organizá-los por ordem alfabética crescente das atribuições na coluna "exemplo_nome":</li>
</ul>

```sql
SELECT * FROM tb_pessoas ORDER BY exemplo_nome ASC;
```

<ul>
    <li>Selecionar todos os valores da tabela e organizá-los por ordem numérica decrescente das atribuições na coluna "exemplo_idade":</li>
</ul>

```sql
SELECT * FROM tb_pessoas ORDER BY exemplo_idade DESC;
```

<h2 align="center">Incremento Automático (AUTO_INCREMENT)</h2>
<h3>Introdução:</h3>
O incremento automático possui a função de atribuir valores únicos, em ordem crescente, a uma determinada coluna de forma automática, sem a necessidade de preenchê-la manualmente. É normalmente utilizado na criação de IDs únicos em uma tabela, assim diferenciando seus valores de forma exata e precisa.
<h3>Requerimentos:</h3>
Para a declaração do incremento automático, primeiro precisamos cumprir os seguintes requerimentos:

<h4>Não Nulo (NOT NULL):</h4>
<ul>
    <li>Por padrão, todos os tipos de dados declarados podem armazenar valores nulos, ou seja, sem um valor especificado;</li>
    <li>Ao declarar um tipo de dado (coluna) como "NOT NULL", todos os valores inseridos na tabela precisam de um valor definido na coluna especificada.</li>
</ul>

<h4>Chave Primária (PRIMARY KEY):</h4>
<ul>
    <li>A chave primária é declarada em uma coluna de importância vital para a tabela;</li>
    <li>Sua função é otimizar e melhorar a performance da coluna, geralmente a de IDs únicos.</li>
</ul>

<h3>Criando uma tabela com coluna de incremento automático:</h3>

Todos os comandos apresentados nessa seção serão utilizados em conjunto do "AUTO_INCREMENT" para declararmos uma coluna, ou seja:
<ul>
    <li>Uma coluna que não poderá armazenar valores nulos (NOT NULL);</li>
    <li>Estabelecida como chave primária (PRIMARY KEY).</li>
</ul>

> [!NOTE]
> - Não é necessário criar uma nova tabela para definir uma coluna com essas características;
> - Esse é apenas um exemplo, e a forma que eu inicialmente aprendi!

<h4>Criar uma tabela com coluna de incremento automático:</h4>

```sql
CREATE TABLE tb_exemplo(id_unico INT(4) NOT NULL PRIMARY KEY AUTO_INCREMENT);
```

> [!IMPORTANT]
> Todos os comandos são separados apenas por espaço, sem o uso de vírgula (,).

<h2 align="center">Alterar Tabela (ALTER TABLE)</h2>
<h3>Introdução:</h3>
A declaração "ALTER TABLE" possui a função de modificar a estrutura de uma tabela para diversas finalidades. Nos exemplos a seguir, estaremos a utilizando para adicionarmos e removermos colunas de uma tabela!

<h4>Adicionar nova coluna em uma tabela:</h4>
<ul>
    <li>Alterar a tabela "tb_exemplo" para adicionar a coluna "exemplo_sobrenome":</li>
</ul>

```sql
ALTER TABLE tb_exemplo ADD exemplo_sobrenome VARCHAR(50);
```

<h4>Deletar coluna existente de uma tabela:</h4>
<ul>
    <li>Alterar a tabela "tb_exemplo" para remover a coluna "exemplo_sobrenome":</li>
</ul>

```sql
ALTER TABLE tb_exemplo DROP COLUMN exemplo_sobrenome;
```

<h4>Mudando o nome e tipo de uma coluna na tabela:</h4>
<ul>
    <li>Alterar a tabela "tb_exemplo" para modificar a coluna "coluna_antiga", mudando seu nome para "coluna_nova" e adicionando o tipo de dado "VARCHAR":</li>
</ul>

```sql
ALTER TABLE tb_exemplo CHANGE coluna_antiga coluna_nova VARCHAR(50);
```

> [!TIP]
> - A condição "CHANGE" é extremamente útil para alterar o limite de caracteres ou casas numéricas de uma coluna;
> - Exemplo: Modificar o tipo de dado e limite de caracteres "VARCHAR(20)" de uma coluna para "VARCHAR(50)".

<h2 align="center">Atualizando as informações de uma tabela (UPDATE)</h2>
A declaração "UPDATE" possui a finalidade de atualizar as informações de uma tabela, podendo ser utilizada tanto para modificar informações já existentes, quanto para adicionar novas informações em determinada(s) coluna(s). Para utilizarmos o "UPDATE", é recomendado que a tabela possua uma coluna de IDs únicos para diferenciar os valores que serão modificados.

<h3>Condições:</h3>
O "UPDATE" possui algumas condições para ser executado corretamente, e é recomendado que as seguintes condições sejam cumpridas:

<h4>Definir (SET):</h4>
<ul>
    <li>A condição "SET" define a coluna que será alterada, e qual será a nova informação adicionada;</li>
    <li>Até onde eu sei, é uma condição obrigatória.</li>
</ul>

<h4>Onde (WHERE):</h4>
<ul>
    <li>A condição "WHERE" indica as condições que as linhas precisam cumprir para serem selecionadas;</li>
    <li>Ela indica os requerimentos que as linhas precisam possuir para serem atualizadas;</li>
    <li>O requerimento geralmente será o valor do ID único da linha desejada;</li>
</ul>

> [!IMPORTANT]
> O "WHERE" não é uma condição obrigatória, mas de <b>extrema importância</b> para a utilização segura do "UPDATE".

<h3>Atualizar as informações de uma tabela:</h3>
<ul>
    <li>Atualizar a tabela "tb_exemplo", definindo a informação presente na coluna "exemplo_nome" como "Nan" onde o "id_unico" da linha que será afetada possui o valor "123":</li>
</ul>

```sql
UPDATE tb_exemplo SET exemplo_nome = "Nan" WHERE id_unico = 123;
```

<h2 align="center">Operadores do "WHERE"</h2>
A condição "WHERE" pode ser utilizada em conjunto de certos operadores, com a finalidade de filtrar os resultados obtidos em consultas no banco de dados de forma precisa. Alguns desses operadores são:

<h3>Correspondente (LIKE):</h3>
<ul>
    <li>O operador "LIKE" é utilizado para filtrar resultados que possuam padrões correspondentes;</li>
    <li>Exemplo: Filtrar por nomes cadastrados em uma tabela que começam pela letra "A";</li>
    <li>O caractere "%" serve para sinalizar que existem caracteres antes ("%padrao") ou depois ("padrao%") do padrão desejado, ou para buscar qualquer valor que contém tal padrão, independentemente da posição do mesmo ("%padrao%");</li>
</ul>

<h4>Selecionar todos os valores da tabela "tb_amigos", filtrando os resultados para exibir apenas os que possuem os valores na coluna "nome" terminados pela letra "A":</h4>

```sql
SELECT * FROM tb_amigos WHERE nome LIKE "%A";
```

<h4>Filtrando os resultados para exibir apenas os que possuem os valores na coluna "nome" começados pela letra "A":</h4>

```sql
SELECT * FROM tb_amigos WHERE nome LIKE "A%";
```

<h4>Filtrando os resultados para exibir apenas os valores da coluna "nome" que possuem a letra "A" em qualquer posição:</h4>

```sql
SELECT * FROM tb_amigos WHERE nome LIKE "%A%";
```

<h3>E/Ou (AND/OR):</h3>
<ul>
    <li>Os operadores "AND" e "OR" possuem a finalidade de aplicar um filtro de condições, exibindo apenas os resultados que as cumprirem;</li>
    <li>Essas condições são aplicadas com a ajuda dos <b>operadores de comparação</b> (=, !=, <, >, <=, >=)</li>
    <li><b>Ambas as condições aplicadas pelo "AND" devem ser cumpridas</b> para que os valores sejam filtrados;</li>
    <li><b>Apenas uma das condições aplicadas pelo "OR" precisa ser cumprida</b> para que os valores sejam filtrados;</li>
</ul>

<h4>Selecionar todos os valores da tabela "tb_doces", filtrando os resultados com o operador "AND" para exibir apenas os que tiverem a coluna "quantidade" preenchida com um valor maior ou igual a 10, e menor ou igual a 20:</h4>

```sql
SELECT * FROM tb_doces WHERE quantidade >= 10 AND quantidade <= 20;
```

<h4>Filtrando os resultados com o operador "OR" para exibir os valores que tiverem a coluna "quantidade" preenchida com um valor maior ou igual a 20, ou menor ou igual a 5:</h4>

```sql
SELECT * FROM tb_doces WHERE quantidade >= 20 OR quantidade <= 5;
```

> [!WARNING]
> É possível utilizar ambos os operadores "AND" e "OR" em conjunto para criar condições no mesmo comando, mas por sua conta e risco!

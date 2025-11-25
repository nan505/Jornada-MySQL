<h1 align="center"> Jornada MySQL <img align="center" src="https://skillicons.dev/icons?i=mysql" height="50" alt="mysql logo" /></h1>
<br>
<h2>Sobre mim e a Jornada MySQL:</h2>

Prazer, podem me chamar de Nan! Atualmente estou fazendo um curso de T.I. e decidi "documentar" meus aprendizados sobre MySQL por meio desse repositório!
Esse projeto foi fortemente inspirado pela [Jornada JavaScript](https://github.com/JoaoGomeszs/Jornada-JavaScript), do meu extremamente talentoso amigo e colega de curso: [João Gomes](https://github.com/JoaoGomeszs/)!

> [!IMPORTANT]
> Ao longo da jornada, estarei utilizando o realce de sintaxe do SQL nos blocos de código para facilitar a visualização de certos comandos, declarações, tabelas, etc. A Jornada MySQL foi criada com o intuito de auxiliar e documentar apenas o meu aprendizado pessoal sobre o sistema, [consulte a documentação oficial do MySQL por aqui.](https://dev.mysql.com/doc/)

<br>
<details>
<summary>Tabela de conteúdos (Clique para mostrar)</summary>

- [Introdução](#introdução)
    - [XAMPP](#xampp)
    - [Iniciando o MySQL](#iniciando-o-mysql)
- [Sintaxe Básica e Boas Práticas](#sintaxe-básica-e-boas-práticas)
    - [Sintaxe básica](#sintaxe-básica)
    - [Boas práticas](#boas-práticas)
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
- [Incremento Automático (AUTO_INCREMENT)](#incremento-automático-auto_increment)
    - [Não Nulo (NOT NULL)](#não-nulo-not-null)
    - [Chave Primária (PRIMARY KEY)](#chave-primária-primary-key)
    - [Criando uma tabela com coluna de incremento automático](#criando-uma-tabela-com-coluna-de-incremento-automático)
</details>

<br>
<h2 align="center">Introdução</h2>
<h3>XAMPP</h3>
Esse repositório foi inicialmente criado e planejado com a utilização da compilação de softwares livres <strong>XAMPP</strong> como base, então resultados e algumas instruções podem possivelmente variar.

<h3>Iniciando o MySQL</h3>
<ul>
  <li>Abra o XAMPP Control Panel, procure pelo módulo "MySQL" e clique em "Start". Após isso, clique no botão "Shell" para abrir o CMD;</li>
  <li>Na recém aberta janela do CMD, insira o seguinte código:</li>
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
      Ela serve para inserir o restante do código, sem a necessidade de reescrevê-lo;</li><br>
  <li>Ao finalizar uma linha de código com erro(s), uma mensagem de erro será exibida no CMD:<br>
      Caso um ou vários erros sejam exibidos, será necessário reescrever todo o código novamente, de forma correta;</li><br>
  <li>Caracteres especiais não são reconhecidos por padrão e serão exibidos como "?", mas podem ser habilitados!</li>
</ul>

<h3>Boas práticas:</h3>
<ul>
  <li>Comandos do MySQL sempre em letras maiúsculas (UPPERCASE);</li>
  <li>Nomes atribuídos ao banco de dados, tabelas, tipos de dados, etc. sempre em letras minúsculas (lowercase).</li>
</ul>

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
  O primeiro valor declarado dentro do parênteses será o limite de casas númericas antes da vírgula, e o segundo será o limite de casas depois da vírgula;<br>
  Exemplo: DECIMAL(4,2) - Limita a quantidade de casas numéricas antes da vírgula para 4, enquanto as casas após a vírgula serão limitadas para 2.
</ul>

> [!NOTE]
> Ao inserir valores do tipo númerico, não os colocar dentro de aspas.

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
> - Ao criar uma nova tabela, ao menos um tipo de dado (coluna) precisa ser adicionado;<br>
> - Os nomes e tipos de dados devem ser todos declarados dentro de parênteses ();<br>
> - Para inserir vários tipos de dados no mesmo comando, separe-os com vírgulas (,).

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
> - Para inserir um novo valor em uma tabela, é necessário atribuí-lo a pelo menos um tipo de dado;
> - Exemplo: Um valor que represente uma pessoa seria atribuído aos tipos de dado "nome" e "idade";
> - Os valores (VALUE) devem ser separados por vírgula e colocados em ordem, como no exemplo abaixo: 

```sql
INSERT INTO tb_pessoas (exemplo_nome, exemplo_idade) VALUE ("Nan", 19);
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
    <li>Selecionar todos os valores da tabela "tb_pessoas" que possuem atribuições na coluna "exemplo_nome":</li>
</ul>

```sql
SELECT exemplo_nome FROM tb_pessoas;
```

<h4>Selecionar valores específicos de uma tabela pelas suas atribuições:</h4>
<ul>
    <li>Selecionar o valor da tabela que possui a coluna "exemplo_nome" atribuída como "Nan":</li>
</ul>

```sql
SELECT * FROM tb_pessoas WHERE exemplo_nome = “Nan”;
```

<h2 align="center">Incremento Automático (AUTO_INCREMENT)</h2>
<h3>Introdução:</h3>
O incremento automático possui a função de atribuir valores únicos, em ordem crescente, a uma determinada coluna de forma automática, sem a necessidade preenchê-la manualmente. É normalmente utilizado na criação de IDs únicos em uma tabela, assim diferenciando seus valores de forma exata e precisa.
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

<h1 align="center"> Jornada MySQL <img align="center" src="https://skillicons.dev/icons?i=mysql" height="50" alt="mysql logo" /></h1>
<br>
<h2>Sobre mim e a Jornada MySQL:</h2>

Prazer, podem me chamar de Nan! Atualmente estou fazendo um curso de T.I. e decidi "documentar" meus aprendizados sobre MySQL por meio desse repositório!
Esse projeto foi fortemente inspirado pelo repositório [Jornada JavaScript](https://github.com/JoaoGomeszs/Jornada-JavaScript), do meu extremamente talentoso amigo e colega de curso: [João Gomes](https://github.com/JoaoGomeszs/)!
<br><br>
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

```shell
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

```shell
SHOW DATABASES;
```

<h4>Comando para criar um novo banco de dados:</h4>

```shell
CREATE DATABASE db_github;
```

<h4>Comando para utilizar o banco de dados desejado:</h4>

```shell
USE db_github;
```

<h2 align="center">Tipos de dados</h2>
<h3>Até o momento, utilizei os seguintes tipos de dados:</h3>

<h4>Numéricos (Numerics):</h4>
<ul>
  <li><b>INTEGER()</b> ou <b>INT()</b></li>
  Utilizado para valores exatos e inteiros, declarado em conjunto de um limite máximo de casas numéricas dentro do parênteses;<br>
  Exemplo: INT(2) - Limita a quantidade de casas numéricas para 2, então 99 seria aceito, mas 100 não;<br>
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

```shell
SHOW TABLES;
```

<h3>Criar uma nova tabela:</h3>

> [!IMPORTANT]  
> - Ao criar uma nova tabela, ao menos um tipo de dado (ou coluna) precisa ser adicionado;<br>
> - Os nomes e tipos de dados devem ser todos declarados dentro de parênteses ();<br>
> - Para inserir vários tipos de dados no mesmo comando, separe-os com vírgulas (,).

```shell
CREATE TABLE tb_pessoas(exemplo_nome VARCHAR(50), exemplo_idade INT(3));
```

<h4>Descrever as informações da tabela (+ Exemplo visual):</h4>

```shell
DESC tb_pessoas;
```

```shell
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

```shell
INSERT INTO tb_pessoas (exemplo_nome, exemplo_idade) VALUE ("Nan", 19);
```

<h3>Selecionando valores de uma tabela:</h3>

> [!TIP]
> - O comando "SELECT" serve para visualizar os valores de uma tabela;
> - Pode ser usado para visualizar todos os valores inseridos, ou valores específicos;

<h4>Selecionar todos os valores da tabela:</h4>

```shell
SELECT * FROM tb_pessoas;
```

<h4>Selecionar valores específicos de uma tabela pelos seus tipos de dado:</h4>
<ul>
    <li>Comando para selecionar todos os valores da tabela "tb_pessoas" que possuem o tipo de dado "exemplo_nome":</li>
</ul>

```shell
SELECT exemplo_nome FROM tb_pessoas;
```

<h4>Selecionar valores específicos de uma tabela pelas suas atribuições:</h4>
<ul>
    <li>Comando para selecionar o valor da tabela que possui o tipo de dado "exemplo_nome" atribuído como "Nan":</li>
</ul>

```shell
SELECT * FROM tb_pessoas WHERE exemplo_nome = “Nan”;
```

<h2 align="center">Incremento Automático (AUTO_INCREMENT)</h2>
<h3>Introdução:</h3>
O incremento automático possui a função de atribuir valores a uma determinada coluna automaticamente, sem a necessidade preenchê-la de forma manual. É normalmente utilizado na criação de IDs únicos em uma tabela, assim diferenciando valores de forma precisa e única!
<h3>Requerimentos:</h3>
Para a declaração do incremento automático, primeiro precisamos cumprir os seguintes requerimentos:

<h4>Não Nulo (NOT NULL):</h4>
<ul>
    <li>Por padrão, todos os tipos de dados declarados podem armazenar valores nulos, ou seja, sem um valor especificado;</li>
    <li>Ao declarar um tipo de dado com o "NOT NULL", todos os valores atribuídos na tabela precisam de um valor definido na coluna especificada.</li>
</ul>

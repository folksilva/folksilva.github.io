---
layout: post
title: "Teoria Prática De Banco De Dados Com MySQL"
modified:
categories: articles
excerpt: "Conheça rapidamente os conceitos de Banco de Dados usando como referência o MySQL"
tags: [
    "apresentações",
    "banco de dados",
    "pratica",
    "ecc"
]
image:
  feature: "MySQL/MySQL-0.jpg"
  thumb: "MySQL/MySQLThumb.jpg"
date: 2015-05-24T17:05:51+00:00
comments: true
share: true
published: true
---

Olá pessoal!

Talvez você esteja cursando uma graduação em sistemas de informação, ciência da 
computação ou seja um curioso do mundo da tecnologia, assim como eu. Uma das primeiras
coisas que precisamos aprender é como armazenar e acessar dados, afinal esse é o
principal objetivo da **Tecnologia da Informação**.

Para te ajudar a entrar nesse mundo, preparei alguns slides rápidos que vão te dar
uma visão geral do que são e como funcinam os banco de dados. Vamos conhecer um dos
principais bancos de dados do mundo e que você pode começar a usar agora sem gastar nada, o **MySQL**.

Veja abaixo os slides e uma descrição completa.

<iframe src="//pt.slideshare.net/slideshow/embed_code/key/oWgAzA9XbmYM8" 
width="595" height="485" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" 
style="border:1px solid #CCC; border-width:1px; margin-bottom:5px; max-width: 100%;" 
allowfullscreen></iframe>

<!-- Begin MailChimp Signup Form -->
<div id="mc_embed_signup">
<form action="//github.us10.list-manage.com/subscribe/post?u=5853bde8ed9c322f380751264&amp;id=78cb1f1eb4" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_blank" novalidate>
  <div id="mc_embed_signup_scroll">
	  <label for="mce-EMAIL">Deixe seu e-mail para receber meus artigos sobre desenvolvimento, aprendizado e produtividade.</label>
  	<div class="clear">
  	  <input type="email" value="" name="EMAIL" class="email" id="mce-EMAIL" placeholder="email address" required>
  	  <input type="submit" value="Subscribe" name="subscribe" id="mc-embedded-subscribe" class="button">
  	</div>
    <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->
    <div style="position: absolute; left: -5000px;">
      <input type="text" name="b_5853bde8ed9c322f380751264_78cb1f1eb4" tabindex="-1" value="">
    </div>
  </div>
</form>
</div>
<!--End mc_embed_signup-->

##Os Bancos de Dados

![Introdução]({{site.url}}/images/MySQL/MySQL-1.jpg)

Pra começar vamos ver um pouquinho da história dos bancos de dados e já vamos 
partir pra prática que é o que interessa.

A ideia original com a apresentação era que cada um instalasse o MySQL e uma 
ferramenta de auxílio chamada MySQL Workbench, essa ferramenta facilita o acesso 
e a manutenção do banco de dados. Você pode instalar o MySQL Workbench nesse 
[link][mysql-workbench] e o próprio MySQL nesse [outro link][mysql-setup].

Talvez você esteja usando a máquina do trabalho para aprender e não pode instalar
aplicativos novos, ou seu computador é bem velhinho e te deixa com raiva quando 
você tenta instalar alguma coisa. 
Eu sei bem como é, não se preocupe, vou te ensinar como você pode ter um servidor
de desenvolvimento e testes gratuito.

###Usando o MySQL sem instalar

Com a evolução dos navegadores, da internet e da computação em nuvem não precisamos
mais instalar aplicativos no nosso computador, um exemplo são os ambientes de 
desenvolvimento integrados *(IDE na sigla em inglês)*, vou assumir que você vai seguir
os passos abaixo para o resto do artigo, mas se instalar o servidor na sua máquina e
tiver alguma dúvida deixe um comentário que eu respondo te auxiliando.

1. Vamos usar o [**CodeAnywhere**][codeanywhere-refer], uma IDE na nuvem muito poderosa 
e fácil de usar, crie sua conta gratuita para ter direito a uma *DevBox* (uma máquina virtual),
caso queira criar mais *DevBox* você pode fazer uma assinatura.
2. Depois da conta criada vamos criar uma *DevBox* genérica para nosso aprendizado:
![CodeAnywhere]({{site.url}}/images/MySQL/devbox-1.png)
Na tela da IDE clique em *DevBox*;
![Nova DevBox]({{site.url}}/images/MySQL/devbox-2.png)
Selecione *PHP* e clique em *Next*;
![Ubuntu]({{site.url}}/images/MySQL/devbox-4.png)
Selecione *Ubuntu*, dê um nome para a sua nova *DevBox* e clique em *Create*;
![Criando]({{site.url}}/images/MySQL/devbox-5.png)
Aguarde um pouquinho...
![Criado]({{site.url}}/images/MySQL/devbox-6.png)
Pronto! Sua *DevBox* está funcionando e com o MySQL já instalado.
3. Para acessar o MySQL digite `mysql -h localhost -u root` no terminal da IDE.


![Primeiros Bancos]({{site.url}}/images/MySQL/MySQL-2.jpg)

No início da computação todas as informações eram armazenadas em arquivos, e como
os papeis impressos não estavam relacionados. 

Tentando resolver esse problema surgiu o **Banco de Dados Hierárquico**, os dados 
ficavam relacionados em uma árvore, como uma estrutura de pastas que é usada até
hoje no seu computador.

Esse modelo permitia que uma informação tivesse apenas um relacionamento do tipo 
*pai - filho*, para evoluir surgiu o **Banco de Dados em Rede** que permitia que
um registro tivesse mais de um *pai*. Isso resolveu alguns problemas, mas mesmo 
assim esses modelos eram muito restritivos para os tipos de relacionamentos.


![Bancos Relacionais]({{site.url}}/images/MySQL/MySQL-3.jpg)

A revolução dos dados começou quando surgiram os **Bancos de Dados Relacionais**,
em conjunto com a ascenção da computação pessoal e a grande necessidade de aplicações
mais robustas e complexas para as empresas.

O Modelo Relacional utiliza uma estrutura de **tabelas** e **chaves** que consegue imitar
com maior fidelidade o mundo real, usando como fundamento alguns principios de 
matemática básica.


![Teoria dos Conjuntos]({{site.url}}/images/MySQL/MySQL-4.jpg)

No ensino fundamental aprendemos sobre a Teoria dos Conjuntos, mas para entender como
os bancos relacionais usam a teoria dos conjuntos vamos pensar em duas familias.
Os *Capuletos* e os *Montecchios*, cada familia possui seus membros isolados, mas
pode acontecer de uma Capuleto se casar com um Montecchio, se sua história não fosse 
trágica provavelmente teriam filhos, esses filhos representariam uma união das duas 
familias, criando um novo sub conjunto.

Nos modelos relacionais você consegue trabalhar com cada *familia* individualmente ou
com seus sub conjuntos de forma muito simples e intuitiva, vamos ver em breve como isso
funciona.

![MySQL]({{site.url}}/images/MySQL/MySQL-5.jpg)

O MySQL é um Sistema Gerenciador de Bancos de Dados muito popular e acessível, ele
funciona em todos os sistemas operacionais populares e é usado por grandes empresas no
mundo todo.

Seus princípios estão na facilidade para instalar, configurar e usar, por isso é uma
excelente maneira de você começar seus estudos sobre banco de dados antes de avançar
para outros mais complexos.


![Uma Coleção]({{site.url}}/images/MySQL/MySQL-6.jpg)

Para entendermos na prática os bancos de dados relacionais vamos pensar em tudo
como uma coleção de itens, a primeira coisa que me vem na cabeça quando penso em
coleções são os albuns de figurinhas, vamos criar um banco de dados para registrar
nossos albuns e suas figurinhas.


##O Modelo Relacional

<figure class="half">
  <img src="/images/MySQL/MySQL-7.jpg">
  <img src="/images/MySQL/MySQL-8.jpg">
</figure>

Com o *MySQL Workbench* podemos criar graficamente nossas tabelas para nosso banco
de dados. O mais importante é entender alguns conceitos:

* Cada tabela representa uma **entidade** do mundo real;
* Cada propriedade da entidade é representada por uma **coluna** na tabela;
* Cada registro na tabela possui uma identificação exclusiva em um coluna do 
tipo **chave primária**;
* Um registro de uma tabela se relaciona com outro de outra tabela através de 
uma coluna do tipo **chave estrangeira** que faz uma referência a chave primária 
da outra tabela.
* As colunas possuem tipos de dados que definem como a informação dela é 
armazenada, alguns dos tipos são:
    * _INT_: Um número inteiro comum (1, 2, 1000, etc.)
    * _FLOAT_: Um número de ponto flutuante comum (1,5, 100,59, etc.)
    * _BIT_: Um valor único (bit), podemos usá-lo para definir coisas como 
verdadeiro ou falso
    * _VARCHAR_: Um texto comum
    * _TIMESTAMP_: Uma representação de data e hora

Vamos pensar no nosso banco de dados, possuímos duas entidades para nossa coleção:

* __Album__: Onde vamos registrar todos os nossos albuns de figurinhas, pode 
possuir as seguintes propriedades:
    * __id__: A nossa chave primária, vai ser do tipo _INT_;
    * __nome__: O nome do album de figurinhas, do tipo _VARCHAR_;
    * __ano__: O ano do album de figurinhas, afinal podemos colecionar um mesmo 
album de vários anos diferentes, do tipo _INT_.
* __Figurinha__: Onde vamos registrar todas as figurinhas do nsso album, pode 
possuir essas propriedades:
    * __id__: A chave primária das figurinhas, também do tipo _INT_;
    * __album_id__: Uma chave estrangeira que relaciona a figurinha com o seu 
album, precisa ter o mesmo tipo da chave primária a que se refere, no caso _INT_;
    * __numero__: O número da figurinha no album, do tipo _INT_;
    * __especial__: Alguns albuns possuem figurinhas especiais, podem ser as 
brilhantes ou que valem algum prêmio, vamos registrar isso nesse campo com o tipo _BIT_.


##Comandos *SQL* Básicos

Para interagir com o banco de dados foi criada uma linguagem estruturada de 
consulta, o <abbr title="Structured Query Language">SQL</abbr>. É uma linguagem
padronizada que pode ser usada em todos os bancos de dados relacionais, as vezes
apenas com algumas particularidades do banco de dados escolhido.

O SQL possui comandos divididos em sub grupos, o que precisamos conhecer agora são os
três mais utilizados:

* __*DML* - Linguagem de Manipulação de Dados__: Que usamos para inserir, atualizar ou remover dados do banco de dados
* __*DDL* - Linguagem de Definição de Dados__: Que usamos para criar, alterar ou remover tabelas do banco de dados
* __*DQL* - Linguagem de Consulta de Dados__: Que usamos para selecionar dados do banco de dados


![Criando Estrutura]({{site.url}}/images/MySQL/MySQL-9.jpg)

Para criar tabelas no MySQL usamos o comando `CREATE`, você pode usar o próprio 
MySQL Workbench para fazer isso com a ajuda da interface gráfica. Mas se quiser 
*botar a mão na massa* segue abaixo o comando SQL:

{% highlight sql %}
CREATE DATABASE album_de_figurinhas;

USE album_de_figurinhas;

CREATE TABLE album (
    id INT NOT NULL AUTO_INCREMENT,
    nome VARCHAR(200) NOT NULL,
    ano INT NOT NULL,
    PRIMARY KEY (id)
);

CREATE TABLE figurinha (
    id INT NOT NULL AUTO_INCREMENT,
    album_id INT,
    numero INT NOT NULL,
    especial BIT,
    PRIMARY KEY (id),
    FOREIGN KEY (album_id) REFERENCES album (id)
);
{% endhighlight %}

> Primeiro criamos um novo banco de dados chamado `album_de_figurinhas`, 
selecionamos ele com o comando `USE` e depois criamos as nossas duas tabelas.


![Inserindo Dados]({{site.url}}/images/MySQL/MySQL-10.jpg)

Para inserir registros nas tabelas usamos o comando `INSERT`, vamos entendê-lo:

{% highlight sql %}
INSERT INTO nome_da_tabela (colunas) VALUES (valores);
{% endhighlight %}

* `nome_da_tabela`: Troque pelo nome da tabela onde vai inserir os registros
* `colunas`: Troque por uma lista das colunas que vai preencher
* `valores`: Troque por uma lista dos valores que está inserindo

No nosso exemplo vamos criar dois albuns e inserir algumas figurinhas neles (Os 
números de figurinha que usei são aleatórios, mas se você tem algum dos albuns 
do exemplo pode usar os números verdadeiros).

{% highlight sql %}
INSERT INTO album (nome, ano) VALUES ('Copa do Mundo - Brasil', 2014);
INSERT INTO album (nome, ano) VALUES ('Copa América - Chile', 2015);
INSERT INTO album (nome, ano) VALUES ('UEFA Champions League', 2015);

INSERT INTO figurinha (album_id, numero, especial) VALUES (1, 10, FALSE);
INSERT INTO figurinha (album_id, numero, especial) VALUES (1, 100, TRUE);
INSERT INTO figurinha (album_id, numero, especial) VALUES (1, 57, FALSE);
INSERT INTO figurinha (album_id, numero, especial) VALUES (1, 22, TRUE);
INSERT INTO figurinha (album_id, numero, especial) VALUES (2, 1, FALSE);
INSERT INTO figurinha (album_id, numero, especial) VALUES (2, 15, FALSE);
INSERT INTO figurinha (album_id, numero, especial) VALUES (2, 50, TRUE);
INSERT INTO figurinha (album_id, numero, especial) VALUES (2, 78, FALSE);
INSERT INTO figurinha (album_id, numero, especial) VALUES (NULL, 138, TRUE);
{% endhighlight %}

> Repare que na hora de inserir as figurinhas usamos os números 1 e 2 para a coluna 
`album_id`, isso porque na hora que criamos a tabela album informamos que a coluna 
`id` deve ser incrementada automáticamente (`auto_increment`), assim o MySQL sozinho
associa um número em sequência para os novos registros.


![Consultas]({{site.url}}/images/MySQL/MySQL-11.jpg)

Para selecionar registros das tabelas usamos o comando `SELECT`:

{% highlight sql %}
SELECT colunas FROM nome_da_tabela;

SELECT colunas FROM nome_da_tabela WHERE condicao;
{% endhighlight %}

* `colunas`: Troque por uma lista das colunas que quer selecionar, ou use `*` 
para selecionar todas
* `nome_da_tabela`: Troque pelo nome da tabela onde vai buscar os dados
* `condicao`: Troque por uma condição de seleção, para filtrar os resultados

Como exemplo, podemos selecionar todos os albuns que inserimos:

{% highlight sql %}
SELECT * FROM album;
{% endhighlight %}

Podemos também selecionar todas as figurinhas especiais:

{% highlight sql %}
SELECT * FROM figurinha WHERE especial = TRUE;
{% endhighlight %}


![Atualizando]({{site.url}}/images/MySQL/MySQL-12.jpg)

Para atualizar registros das tabelas usamos o comando `UPDATE`:

{% highlight sql %}
UPDATE nome_da_tabela SET coluna = valor;

UPDATE nome_da_tabela SET coluna = valor WHERE condicao;
{% endhighlight %}

* `nome_da_tabela`: Troque pelo nome da tabela onde vai buscar os dados
* `coluna`: Troque pelo nome da coluna que vai atualizar
* `valor`: Troque pelo novo valor para a coluna
* `condicao`: Troque por uma condição de seleção, caso contrário todos os 
registros serão atualizados

Podemos alterar a figurinha número 1 para especial, por exemplo:

{% highlight sql %}
UPDATE figurinha SET especial = TRUE WHERE numero = 1;
{% endhighlight %}


![Excluindo]({{site.url}}/images/MySQL/MySQL-13.jpg)

Para excluir registros das tabelas usamos o comando `DELETE`:

{% highlight sql %}
DELETE FROM nome_da_tabela;

DELETE FROM nome_da_tabela WHERE condicao;
{% endhighlight %}

* `nome_da_tabela`: Troque pelo nome da tabela onde vai buscar os dados
* `condicao`: Troque por uma condição de seleção, caso contrário todos os 
registros da tabela serão excluídos

Podemos remover a figurinha número 78:

{% highlight sql %}
DELETE FROM figurinha WHERE numero = 78;
{% endhighlight %}


<!-- Begin MailChimp Signup Form -->
<div id="mc_embed_signup">
<form action="//github.us10.list-manage.com/subscribe/post?u=5853bde8ed9c322f380751264&amp;id=78cb1f1eb4" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_blank" novalidate>
  <div id="mc_embed_signup_scroll">
	  <label for="mce-EMAIL">Como está sua leitura? Deixe seu e-mail para receber mais.</label>
  	<div class="clear">
  	  <input type="email" value="" name="EMAIL" class="email" id="mce-EMAIL" placeholder="email address" required>
  	  <input type="submit" value="Subscribe" name="subscribe" id="mc-embedded-subscribe" class="button">
  	</div>
    <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->
    <div style="position: absolute; left: -5000px;">
      <input type="text" name="b_5853bde8ed9c322f380751264_78cb1f1eb4" tabindex="-1" value="">
    </div>
  </div>
</form>
</div>
<!--End mc_embed_signup-->


##Comandos *SQL* Mais Avançados

![Consultas Avançadas]({{site.url}}/images/MySQL/MySQL-14.jpg)

Vamos complicar um pouquinho os comandos, com SQL é possível:

* Selecionar apenas alguns resultados
* Ordernar os resultados selecionados
* Unir tabelas numa consulta


![LIMIT]({{site.url}}/images/MySQL/MySQL-15.jpg)

Para limitar a quantidade de resultados adicionamos o `LIMIT` no comando `SELECT`,
no exemplo, vamos selecionar apenas 3 figurinhas:

{% highlight sql %}
SELECT * FROM figurinha LIMIT 3;
{% endhighlight %}


![ORDER BY]({{site.url}}/images/MySQL/MySQL-16.jpg)

Para ordernar os resultados do comando `SELECT` usamos o `ORDER BY`, vamos ordenar
as figurinhas pelo número:

{% highlight sql %}
SELECT * FROM figurinha ORDER BY numero;
{% endhighlight %}


###Combinação de tabelas na consulta

<figure class="third">
  <img src="/images/MySQL/MySQL-17.jpg">
  <img src="/images/MySQL/MySQL-18.jpg">
  <img src="/images/MySQL/MySQL-19.jpg">
</figure>

A maior vantagem dos bancos de dados relacionais é a capacidade de combinar várias
tabelas relacionadas em uma única consulta, aqui aplicamos os conceitos da teoria 
dos conjuntos que vimos a pouco, vamos entender a sintaxe:

{% highlight sql %}
SELECT colunas FROM nome_da_tabela JOIN nome_da_outra_tabela ON condicao_de_uniao;
{% endhighlight %}

* `colunas`: Como na seleção comum troque pelas colunas que quer selecionar, das 
duas tabelas
* `nome_da_tabela`: Troque pelo nome da primeira tabela na seleção
* `nome_da_outra_tabela`: Troque pelo nome da segunda tabela na seleção
* `condicao_de_uniao`: Troque pela condição de união das duas tabelas, que define 
quando os registros combinam


Existem três tipos de combinações que podemos fazer:

* __INNER JOIN__: Selecionamos apenas o sub conjunto onde os registros combinam 
nas duas tabelas, no exemplo vamos combinar os albuns e figurinhas em uma consulta

{% highlight sql %}
SELECT * FROM album INNER JOIN figurinha ON figurinha.album_id = album.id;
{% endhighlight %}

* __LEFT JOIN__: Selecionamos todos os registros da primeira tabela e os que 
combinam da segunda, por exemplo podemos selecionar todos os albuns e apenas as 
figurinhas que combinam

{% highlight sql %}
SELECT * FROM album LEFT JOIN figurinha ON figurinha.album_id = album.id WHERE album.id = 1;
{% endhighlight %}

* __RIGHT JOIN__: Selecionamos todos os registros da segunda tabela e apenas os 
que combinam da primeira, neste exemplo vamos selecionar todas as figurinhas e
apenas os albuns que combinam

{% highlight sql %}
SELECT * FROM album RIGHT JOIN figurinha ON figurinha.album_id = album.id WHERE figurinha.especial = TRUE;
{% endhighlight %}


##O Futuro dos Bancos de Dados

![Futuro]({{site.url}}/images/MySQL/MySQL-20.jpg)

Atualmente existem outras alternativas para o modelo relacional com comandos SQL, 
é um modelo muito poderos mas ainda possui algumas restrições, principalmente para
novos tipos de aplicações modernas que precisam de cada vez mais desempenho.

Essas alternativas são conhecidas como bancos de dados não relacionais, ou **NoSQL**. 
Em breve vou falar mais sobre esses novos bancos que já estão mudando o gerenciamento
e armazenamento de dados, conheça alguns exemplos:

* [MongoDB][mongodb]: Um banco de dados orientado a documentos no formato JSON
* [Redis][redis]: Um banco de dados de chave-valor
* [Cassandra][cassandra]: Um híbrido entre chave-valor e colunas

#Continue Aprendendo

Nesse artigo tentei te mostrar um pouco dos conceitos de banco de dados com exemplos
práticos usando o MySQL, foi apenas uma pincelada no imenso universo dos bancos
de dados, você tem muito mais a explorar ainda, veja algumas referências para você
continuar seu aprendizado:

* [Centro do Desenvolvedor MySQL][dev-mysql]: O centro oficial do MySQL para 
desenvolvedores, possui uma documentação completa, fóruns para tirar dúvidas e
ferramentas para desenvolver com MySQL
* [MySQL - Guia do Programador (AD)][guia-mysql]: Esse guia traz exemplos práticos
desde o mais básico até o mais avançado do MySQL, um livro para acompanhar a 
carreira de um novo DBA.
* [Curso Completo de MySQL][curso-mysql]: A Devmedia possui esse curso com aulas
online e gratuitas para iniciantes no mundo dos bancos de dados.
* Se ficou curioso veja mais sobre a [Teoria dos Conjuntos][teoria-conjuntos].

Continue explorando e aprendendo, se ficou com alguma dúvida, se encontrou algum
erro meu ou se quer apenas conversar deixe o seu comentário abaixo. Se gostou 
compartilhe para os seus amigos e deixe o seu e-mail no formulário abaixo para 
receber mais artigos sobre desenvolvimento, aprendizado e produtividade.

Nos vemos em breve, um grande abraço!




<!-- Begin MailChimp Signup Form -->
<div id="mc_embed_signup">
<form action="//github.us10.list-manage.com/subscribe/post?u=5853bde8ed9c322f380751264&amp;id=78cb1f1eb4" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_blank" novalidate>
  <div id="mc_embed_signup_scroll">
	  <label for="mce-EMAIL">Deixe seu e-mail para receber mais novidades.</label>
  	<div class="clear">
  	  <input type="email" value="" name="EMAIL" class="email" id="mce-EMAIL" placeholder="email address" required>
  	  <input type="submit" value="Subscribe" name="subscribe" id="mc-embedded-subscribe" class="button">
  	</div>
    <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->
    <div style="position: absolute; left: -5000px;">
      <input type="text" name="b_5853bde8ed9c322f380751264_78cb1f1eb4" tabindex="-1" value="">
    </div>
  </div>
</form>
</div>
<!--End mc_embed_signup-->



[mysql-workbench]: https://dev.mysql.com/downloads/workbench/
[mysql-setup]: https://dev.mysql.com/downloads/mysql/
[codeanywhere-refer]: http://codeanywhere.com/referralsignup/?r=6d36206032353031
[mongodb]: http://www.mongodb.org/
[redis]: http://redis.io
[cassandra]: http://cassandra.apache.org/
[dev-mysql]: http://dev.mysql.com/
[guia-mysql]: http://oferta.vc/7QJH
[curso-mysql]: http://www.devmedia.com.br/curso/curso-completo-de-mysql/281
[teoria-conjuntos]: http://pt.wikipedia.org/wiki/Teoria_dos_conjuntos
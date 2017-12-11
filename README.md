### Introdução

Banco de dados objeto-relacional (BDOR) ou sistema de gerenciamento de banco de dados relacional de objetos (SGBDRO), do inglês object-relational database (ORD) ou object-relational database management system (ORDBMS), é um sistema de gerenciamento de banco de dados (SGBD) semelhante a um banco de dados relacional, porém com um modelo de banco de dados orientado a objetos: objetos, classes e herança são suportados diretamente nos esquemas do banco de dados e na linguagem de consulta. Além disso, ele suporta extensão do modelo de dados com a personalização de tipos de dados e métodos.

A partir do SQL Server 2005 é possível utilizar o SQL Server como um banco OO através da criação de tipos personalizados criados no CLR e carregados para o SQL Server. Essa possibilidade extrapola a utilização dos User Defined Data Types (ou Alias Data Types). Ao invés de criarmos um tipo VARCHAR ou no máximo um tipo e-mail (VARCHAR com um número conhecido de posições), podemos utilizar um objeto como um Cliente por exemplo. A tabela poderia então conter não apenas uma coluna VARCHAR mas uma coluna do tipo Cliente onde a definição de seus atributos e métodos reside em um Assembly codificado em C# e tanto os métodos quanto os atributos podem ser utilizados em cláusula SQL.

Em todo caso, o fato do SQL Server dar algum suporte a esse tipo de construção não significa que ele é um banco orientado a objeto. Não adianta ter a casca parecida com o OO e o miolo continuar sendo relacional. O que ele está fazendo é apenas disponibilizando um ADD-IN para parecer-se com um banco de dados OO (diversos outros SGBDs também o fazem).

É certo que ter uma aplicação OO e um banco OO agiliza muito o desenvolvimento de aplicações visto que a persistência é transparente, ou seja, pode-se persistir as classes diretamente uma vez que a aplicação é OO e o banco é OO. Não haverá necessidade de converter diversos atributos de uma classe para colunas de uma, duas ou diversas tabelas.

Em todo caso, devemos lembrar que um objeto é uma unidade lógica composta de atributos e métodos e não podemos dissecá-lo. O objeto é aquilo e pronto. Não faz sentido repartí-lo em pedaços menores. Se levarmos esse pensamento para o banco de dados, seremos levado a pensar que aplicações que tenham esse mesmo raciocínio são ótimas candidatas a utilizar um banco OO. Aplicações de exames clínicos, aplicações de rádios, etc. As partes de um exame clínico dificilmente fazem sentido separadas (sempre desejar-se-á ter o exame como uma unidade). Uma música também segue o mesmo princípio.

Do outro lado temos os bancos de dados relacionais cuja a natureza normalizada faz com que os dados sejam repartidos por tantas tabelas. No caso das aplicações médicas e rádio teremos que sempre fazer JOINs para consultar os objetos como uma unidade, mas para aplicações transacionais típicas como um sistema de passagens aéreas ou uma aplicação bancária fará muito sentido tratar os dados de forma separada. Isso será vital para o desempenho.

Um dos grandes slogan do SQL Server 2008 é ir além do relacional. De fato ele já ultrapassou essa barreira quando possibilitou a implementação de cubos de dados, o armazenamento de imagens no banco (com devida indexação) e a implementação do XML que é um dado semiestruturado. A presença de dados geográficos só o torna de fato capaz de continuar indo além do relacional, mas por mais que ele esteja rodando as outras implementações não relacionais está com o pé mais fincado no mundo relacional do que qualquer outra coisa (e não acho que vá e nem que deva mudar por enquanto).



### Mapeamento Objeto-Relacional

ORM (Object-Relational Mapping) é uma técnica que consiste da conversão das classes da aplicação para tabelas do banco de dados e vice-versa. Da mesma forma, também faz parte desse processo a conversão entre os objetos da aplicação e as linhas da tabela. Ou seja, enquanto no código trabalhamos com classes e objetos, esses são gravados e recuperados do banco de dados na forma de registros/linhas.

Quando efetuamos esse processo manualmente, cabe a nós ler as linhas e colunas da tabela e preencher objetos e suas propriedades. No entanto, no .NET framework (assim como em outras linguagens) temos à disposição frameworks que se encarregam desse processo. Dessa forma, podemos trabalhar apenas com classes e objetos, sem escrever instruções SQL, e o framework faz todas as conversões necessárias para nós.

Neste microexemplo utilizaremos o Entity Framework, que é o principal framework ORM do ecossistema .NET. Confira abaixo o passo a passo de como proceder para efetuar seu primeiro Mapeamento Objeto-Relacional em C#. Para demonstrar esse processo partiremos de um projeto do tipo Console Application criado no Visual Studio.

#### Passo 1: Criar a classe de domínio

Normalmente em nossos sistemas precisaremos representar elementos do mundo real envolvidos no problema que queremos resolver com esse software. Por exemplo, em um sistema de automação comercial precisaremos representar entidades como Cliente, Produto, Fornecedor, etc. Essas são nossas classes de domínio.

Neste microexemplo criaremos uma classe chamada Cliente a partir da qual vamos persistir dados em uma tabela chamada Clientes no banco de dados. O código dessa classe pode ser visto abaixo:

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/dariogabriel113/banco-de-dados-2/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

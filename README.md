### Introdução

Banco de dados objeto-relacional (BDOR) ou sistema de gerenciamento de banco de dados relacional de objetos (SGBDRO), do inglês object-relational database (ORD) ou object-relational database management system (ORDBMS), é um sistema de gerenciamento de banco de dados (SGBD) semelhante a um banco de dados relacional, porém com um modelo de banco de dados orientado a objetos: objetos, classes e herança são suportados diretamente nos esquemas do banco de dados e na linguagem de consulta. Além disso, ele suporta extensão do modelo de dados com a personalização de tipos de dados e métodos.

A partir do SQL Server 2005 é possível utilizar o SQL Server como um banco OO através da criação de tipos personalizados criados no CLR e carregados para o SQL Server. Essa possibilidade extrapola a utilização dos User Defined Data Types (ou Alias Data Types). Ao invés de criarmos um tipo VARCHAR ou no máximo um tipo e-mail (VARCHAR com um número conhecido de posições), podemos utilizar um objeto como um Cliente por exemplo. A tabela poderia então conter não apenas uma coluna VARCHAR mas uma coluna do tipo Cliente onde a definição de seus atributos e métodos reside em um Assembly codificado em C# e tanto os métodos quanto os atributos podem ser utilizados em cláusula SQL.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

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

# TRABALHO 01:  E-Market
Trabalho desenvolvido durante a disciplina de BD1

# Sumário

### 1. COMPONENTES<br>
Integrantes do grupo<br>
Felipe Gante Maia de Sousa : gante.ufes@gmail.com<br>
Diego Rodrigo Perez Pacheco : diegopacheco.ufes@gmail.com<br>
...<br>

### 2.INTRODUÇÃO E MOTIVAÇÃO<br>
A empresa "Brabo's Comporation" visa facilitar a vida de todos que neste tempo não estão tendo como sair de casa devido a pandemia do Novo corona virus. Sabendo-se dos desafios ficamos motivados com o desenvolvimento deste sistema. O Sistema "E-Market" tem como objetivo criar uma interface entre o comprador e os mercados. levando alimentos e produtos essenciais para todos e ajudado os mercados a não fecharem as portas.  

### 3.MINI-MUNDO<br>

Minimundo
E-Market
<br>
<br>
Estámos produzindo um software com o objetivo de terceirizar as compras nesse periodo de quarentena, permitindo que pessoas em grau de maior de risco possam efetuar as compras sem precisar se expor diretamente.
Cada cliente possui, código identificador, nome, cpf, um telefone, e-mail e endereco. 
O cliente pode realizar uma compra através do menu de itens onde cada cliente pode fazer de nenhum a até varios pedidos independentes. Ao efetuar o pedido, o vendedor reserva os produtos do pedido. O vendedos possui codigo de identificacao e seu nome. 
O menu é igual para todos os vendedores. Ao fazer o pedido são enviados a quantidade de itens e o código do pedido. Os pedidos vão ser reservados pelo vendedor, retirados do menu e atribuido para o entregador.
<br>


### 4.PROTOTIPAÇÃO, PERGUNTAS A SEREM RESPONDIDAS E TABELA DE DADOS<br>
#### 4.1 RASCUNHOS BÁSICOS DA INTERFACE (MOCKUPS)<br>
![Arquivo PDF do Protótipo Balsamiq do E-Market](https://github.com/FelipeGante/E-Market/blob/master/arquivos/prototipo.pdf?raw=true "E-market prototipo")
#### 4.2 QUAIS PERGUNTAS PODEM SER RESPONDIDAS COM O SISTEMA PROPOSTO?
     O vendedor relatorio precisa inicialmente dos seguintes relatórios: 
    - Relatório de produtos mais vendidos:Mostrar qual o nome e numero de vendas dos produtos. Ordenados do mais vendido para o menos vendido. 
    - Relatório de frequêcia de Clientes: Mostrar nome e frenquência que do cleinte. Ordenados do mais vezes compra para o menos vezes compra. 
    - Relátorio de Faturamento do mes: mostrar o valor  fatramento do mes. 
    - Relatorio de média de gasto por cliente: mostrar a media de gasto por cliente. 

 
#### 4.3 TABELA DE DADOS DO SISTEMA:
    
![Exemplo de Tabela de dados do E-Market](https://github.com/FelipeGante/E-Market/blob/master/arquivos/tabela_pedidos.csv "Tabela - E-Market")
    
    
### 5.MODELO CONCEITUAL<br>
    Modelo feito utilizando o software "Br Modelo 3"    
        
![Alt text](https://github.com/FelipeGante/E-Market/blob/master/images/modelo_conceitual.png?raw=true "Modelo Conceitual")
    
    

    
#### 5.1 Validação do Modelo Conceitual
    [Grupo01]: [Nomes dos que participaram na avaliação]
    [Grupo02]: [Nomes dos que participaram na avaliação]

#### 5.2 Descrição dos dados 
    [Tabela]: [Menu]
    Codigo do produto - Identificador unico para controle dos itens no sistema.
    preço - Preço unitario de um dado produto
    nome do produto - Nome do item cadastrado para identificação por pessoas.

    [Tabela]: [Pedidos]
    Quantidade - Informa no momento do pedido a quantidade associada ao item solicitado.
    Codigo do pedido - Identificador unico para gerênciar cada pedido de forma singular.

    [Tabela]: [Vendedor]
    nome - Nome do funcionario ao qual um pedido foi atribuído.
    codigo_vendedor - Identificador unico do vendedor para ter um controle sistematico permitindo responsabilização de tarefas.

    [Tabela]: [Cliente]
    cpf - Identificador unico para o cliente baseado em um documento comum e de facil acesso.
    ddd - Código referente a localização do numero do cliente.
    telefone - Numero de contato do cliente.
    nome - Nome do cliente ao qual estará vinculado a solicitação.
    Endereço - Dividido em 4 campos que são rua,bairro,cidade e complemento. Com isso é possivel ter uma melhor precisão das informações obtidas para melhor atender o cliente. 
    


### 6	MODELO LÓGICO<br>
        Modelo Lógico gerado a partir do "Br Modelo 3"
![Alt text](https://github.com/FelipeGante/E-Market/blob/master/images/modelo_logico.png?raw=true "Modelo Lógico")

### 7	MODELO FÍSICO<br>
        CREATE TABLE trabalho_bd.cliente (
        cpf varchar(11) NOT NULL,
        telefone int4 NOT NULL,
        nome varchar(80) NOT NULL,
        ddd int4 NOT NULL,
        rua varchar(20) NULL,
        bairro varchar(20) NULL,
        cidade varchar(20) NULL,
        complemento varchar(20) NULL,
        CONSTRAINT cliente_pkey PRIMARY KEY (cpf)
        );

        CREATE TABLE trabalho_bd.pedidos (
        quantidade int4 NULL,
        codigo_pedido int4 NOT NULL,
        CONSTRAINT codigo_pedido_pk PRIMARY KEY (codigo_pedido)
        );

        CREATE TABLE trabalho_bd.vendedor_1 (
        nome varchar(80) NOT NULL,
        codigo_vendedor int4 NOT NULL,
        CONSTRAINT codigo_vendedor_pk PRIMARY KEY (codigo_vendedor)
        );

        CREATE TABLE trabalho_bd.menu (
        nome_produto varchar(40) NULL,
        codigo_produto int4 NOT NULL,
        quantidade int4 NULL,
        CONSTRAINT codigo_produto_pk PRIMARY KEY (codigo_produto)
        );
        
       
### 8	INSERT APLICADO NAS TABELAS DO BANCO DE DADOS<br>
        a) inclusão das instruções de inserção dos dados nas tabelas criadas pelo script de modelo físico
        (Drop para exclusão de tabelas + create definição de para tabelas e estruturas de dados + insert para dados a serem inseridos)
        b) Criar um novo banco de dados para testar a restauracao 
        (em caso de falha na restauração o grupo não pontuará neste quesito)
        c) formato .SQL


### 9	TABELAS E PRINCIPAIS CONSULTAS<br>
    OBS: Incluir para cada tópico as instruções SQL + imagens (print da tela) mostrando os resultados.<br>
#### 9.1	CONSULTAS DAS TABELAS COM TODOS OS DADOS INSERIDOS (Todas) <br>

># Marco de Entrega 01: Do item 1 até o item 9.1<br>

#### 9.2	CONSULTAS DAS TABELAS COM FILTROS WHERE (Mínimo 4)<br>
#### 9.3	CONSULTAS QUE USAM OPERADORES LÓGICOS, ARITMÉTICOS E TABELAS OU CAMPOS RENOMEADOS (Mínimo 11)
    a) Criar 5 consultas que envolvam os operadores lógicos AND, OR e Not
    b) Criar no mínimo 3 consultas com operadores aritméticos 
    c) Criar no mínimo 3 consultas com operação de renomear nomes de campos ou tabelas

#### 9.4	CONSULTAS QUE USAM OPERADORES LIKE E DATAS (Mínimo 12) <br>
    a) Criar outras 5 consultas que envolvam like ou ilike
    b) Criar uma consulta para cada tipo de função data apresentada.

#### 9.5	INSTRUÇÕES APLICANDO ATUALIZAÇÃO E EXCLUSÃO DE DADOS (Mínimo 6)<br>
    a) Criar minimo 3 de exclusão
    b) Criar minimo 3 de atualização

#### 9.6	CONSULTAS COM INNER JOIN E ORDER BY (Mínimo 6)<br>
    a) Uma junção que envolva todas as tabelas possuindo no mínimo 2 registros no resultado
    b) Outras junções que o grupo considere como sendo as de principal importância para o trabalho

#### 9.7	CONSULTAS COM GROUP BY E FUNÇÕES DE AGRUPAMENTO (Mínimo 6)<br>
    a) Criar minimo 2 envolvendo algum tipo de junção

#### 9.8	CONSULTAS COM LEFT, RIGHT E FULL JOIN (Mínimo 4)<br>
    a) Criar minimo 1 de cada tipo

#### 9.9	CONSULTAS COM SELF JOIN E VIEW (Mínimo 6)<br>
        a) Uma junção que envolva Self Join (caso não ocorra na base justificar e substituir por uma view)
        b) Outras junções com views que o grupo considere como sendo de relevante importância para o trabalho

#### 9.10	SUBCONSULTAS (Mínimo 4)<br>
     a) Criar minimo 1 envolvendo GROUP BY
     b) Criar minimo 1 envolvendo algum tipo de junção

># Marco de Entrega 02: Do item 9.2 até o ítem 9.10<br>

### 10 RELATÓRIOS E GRÁFICOS

#### a) análises e resultados provenientes do banco de dados desenvolvido (usar modelo disponível)
#### b) link com exemplo de relatórios será disponiblizado pelo professor no AVA
#### OBS: Esta é uma atividade de grande relevância no contexto do trabalho. Mantenha o foco nos 5 principais relatórios/resultados visando obter o melhor resultado possível.

    

### 11	AJUSTES DA DOCUMENTAÇÃO, CRIAÇÃO DOS SLIDES E VÍDEO PARA APRESENTAÇAO FINAL <br>

#### a) Modelo (pecha kucha)<br>
#### b) Tempo de apresentação 6:40 

># Marco de Entrega 03: Itens 10 e 11<br>
<br>
<br>
<br> 



### 12 FORMATACAO NO GIT:<br> 
https://help.github.com/articles/basic-writing-and-formatting-syntax/
<comentario no git>
    
##### About Formatting
    https://help.github.com/articles/about-writing-and-formatting-on-github/
    
##### Basic Formatting in Git
    
    https://help.github.com/articles/basic-writing-and-formatting-syntax/#referencing-issues-and-pull-requests
    
    
##### Working with advanced formatting
    https://help.github.com/articles/working-with-advanced-formatting/
#### Mastering Markdown
    https://guides.github.com/features/mastering-markdown/

    
### OBSERVAÇÕES IMPORTANTES

#### Todos os arquivos que fazem parte do projeto (Imagens, pdfs, arquivos fonte, etc..), devem estar presentes no GIT. Os arquivos do projeto vigente não devem ser armazenados em quaisquer outras plataformas.
1. <strong>Caso existam arquivos com conteúdos sigilosos<strong>, comunicar o professor que definirá em conjunto com o grupo a melhor forma de armazenamento do arquivo.

#### Todos os grupos deverão fazer Fork deste repositório e dar permissões administrativas ao usuário do git "profmoisesomena", para acompanhamento do trabalho.

#### Os usuários criados no GIT devem possuir o nome de identificação do aluno (não serão aceitos nomes como Eu123, meuprojeto, pro456, etc). Em caso de dúvida comunicar o professor.


Link para BrModelo:<br>
http://www.sis4.com/brModelo/download.html
<br>


Link para curso de GIT<br>
![https://www.youtube.com/curso_git](https://www.youtube.com/playlist?list=PLo7sFyCeiGUdIyEmHdfbuD2eR4XPDqnN2?raw=true "Title")



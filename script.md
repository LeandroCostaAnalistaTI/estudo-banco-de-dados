```sql

create database universidade_u;
use universidade_u;

/* universidade_u_logico: */

/* universidade_u_logico: */

CREATE TABLE ALUNO (
    endereco text,
    telefone varchar(20),
    idade int,
    nome varchar(25),
    sexo char(1),
    data_inscricao_curso date,
    valor_pago_curso float(10,2),
    ativo_sn int
);

use universidade_u;

/*insert into ALUNO(... colunas...) value(...valores)   inserir dados na coluna e valores */

insert into aluno(
	endereco , telefone , idade , nome , sexo , data_inscricao_curso , valor_pago_curso , ativo_sn)
values('AVENIDA PAULISTA, 1500, AP315 - SÃO PAULO - SP','11 5555-2233' ,55,'LEANDRO COSTA','M','2021-12-05', 645.22, 1

);

insert into aluno(
	endereco , telefone , idade , nome , sexo , data_inscricao_curso , valor_pago_curso , ativo_sn)
values('RUA BENTA, 10 - SP','11 4455-8585' ,29,'FERNANDA','F','2021-10-05', 580.22, 1

);

insert into aluno(
	endereco , telefone , idade , nome , sexo , data_inscricao_curso , valor_pago_curso , ativo_sn)
values('RUA LUIS, 30 - BELO HORIZONTE','11 8888-9989' ,54,'JOSE','M','2021-08-10', 430.22, 0

);
insert into aluno(
	endereco , telefone , idade , nome , sexo , data_inscricao_curso , valor_pago_curso , ativo_sn)
values('RUA VINTE DE MAIO, 1958 - MACEIO - MA','11 8745-9632' ,33,'FLAVIA','F','2021-05-05', 320.22, 1

);
insert into aluno(
	endereco , telefone , idade , nome , sexo , data_inscricao_curso , valor_pago_curso , ativo_sn)
values('RUA DOZE, 19 - MACEIO - MA','11 7777-9632' ,39,'MARCELO','M','2021-11-05', 612.22, 1

);

/* COMANDO PARA VER O REGISTRO TODO DA TABELA INSERIDO */

select * from aluno;

/* COMANDO PARA VER O REGISTRO ESPECIFICO  DA TABELA INSERIDO */

select NOME, IDADE, TELEFONE from aluno;

/* FILTRANDO REGISTRO (WHERE) com operadores de comparacao e logicos */

select nome, idade, telefone from aluno where valor_pago_curso < 600.00;
select nome, idade, telefone from aluno where valor_pago_curso > 600.00;

select nome, idade, telefone from aluno where valor_pago_curso <= 600.55;

select nome, idade, telefone from aluno where valor_pago_curso < 600.00 and idade >35;


/* quero trazer so registro que o sexo e feminino */

select * from aluno where sexo = 'f' ;

select * from aluno where valor_pago_curso >= 600.00;



select * from aluno where sexo = 'M' AND ativo_sn =1 and valor_pago_curso <=625;



select * from aluno where sexo = 'f' or idade >=30 ;



/* select filtro com operadores BETWEEN ( TRABALHA COM BASE DE E ATE PARA NUMERICO E DATA 
EXEMPLO WHERE IDADE >=18 AND IDADEDA <=21           WHERE IDADE BETWEEN 18 AND 21
EXEMPLO WHERE DATA >= '2018-12-01' AND DATA <= '2018-12-31'        WHERE DATA BETWEEN '2018-12-01' AND '2018-12-31'
  */
  
select * from aluno where IDADE >=18 AND IDADE <=41;

select * from aluno where IDADE between 18 AND 40;

select * from aluno where data_inscricao_curso >= '2021-12-01' AND data_inscricao_curso <= '2021-12-31';

select * from aluno where data_inscricao_curso between '2021-12-01' AND '2021-12-31';


/* select filtro operador IN - PERMITE REALIZAR FILTRO COM BASE DE POSSIBILIDADE */


select * from aluno;

select * from aluno where nome ='FERNANDA' OR nome = 'JOSE' or nome ='MARCELO';

select * from aluno where nome in ('FERNANDA','JOSE','MARCELO');

select * from aluno where nome not in ('FERNANDA','JOSE','MARCELO');


/* select filtro operador like - PERMITE REALIZAR FILTRO COM BASE EM UMA PESQUISA DE CARACTERES DENTRO DE UMA COLUNA TEXTUAL ( CARACTERES CURINGA % E _ ) */ 


select * from aluno;

select * from aluno where nome like '%A';

select * from aluno where nome like '%R%';

select * from aluno where nome like 'M%';

select * from aluno where nome like 'F%A';

select * from aluno where nome like '_OSE';

select * from aluno where nome like '_RN_';

/* SELECT ORDENANDO O RESULTADO  ORDER BY 

SELECT
	<coluna(s)>
FROM
	<tabela(s)>
WHERE
    <filtro(s)>
ORDER BY
    idade ASC, nome DESC  (ASC - ASCEDENTE   DESC - DECRECENTE)   

*/ 

select * from aluno;

select * from aluno order by NOME ASC;

select * from aluno order by NOME DESC;

select * from aluno order by SEXO ASC, IDADE DESC;


/* UPDATE - ATUALIZANDO O REGISTRO DE TABELAS */

select * from aluno;

update ALUNO SET ativo_sn = 1, valor_pago_curso = 900  where nome = 'MARCELO';

/* DELETE - DELETANDO REGISTRO DE TABELAS */ 

select * from aluno;

delete FROM aluno where ativo_sn = 0;

delete FROM aluno where idade in (34,29);

delete FROM aluno where idade in (34,29) or sexo = 'M';


use universidade_u;

insert into aluno(
	sexo, idade, data_inscricao_curso, telefone, valor_pago_curso,
    ativo_sn, endereco, nome
)values(
	'M', 55, '2018-12-01', '11 5555-2222', 645.22, 
    1, 'Avenida Paulista, 1500, ap315 - São Paulo - SP', 'João'
);

insert into aluno(
	data_inscricao_curso, telefone, valor_pago_curso,
    ativo_sn, endereco, nome, 
    sexo, idade
)values(
	'2018-11-01', '11 3333-2222', 589.12, 
    1, 'Rua Francisco Sá, 10 - Belo Horizonte - MG', 'Fernanda', 
    'F', 30
);


insert into aluno(
	data_inscricao_curso, telefone, valor_pago_curso,
    ativo_sn, endereco, nome, 
    sexo, idade
)values(
	'2018-12-02', '11 3333-7777', 600.55, 
    0, 'Avenida Dom Manuel, 300 - Fortaleza - CE', 'José', 
    'M', 29
);


insert into aluno(
	data_inscricao_curso, telefone, valor_pago_curso,
    ativo_sn, endereco, nome, 
    sexo, idade
)values(
	'2018-12-02', '11 7777-7777', 655.45, 
    1, 'Rua Miramar, 1200, ap112 - Natal - RN', 'Maria', 
    'F', 42
);


insert into aluno(
	data_inscricao_curso, telefone, valor_pago_curso,
    ativo_sn, endereco, nome, 
    sexo, idade
)values(
	'2018-11-15', '11 1111-7777', 612.99, 
    1, 'Rua João de Abreu, 650 - Goiânia - GO', 'Marcelo', 
    'M', 37
);


select * from aluno;



/* PROJETO UNIVERSIDADE U - REFINANFO A MODELAGEM CONCEITUAL   e modificar estrutura da tabela com os registro ja incluidos*/



desc aluno;

/* add serve para inclusao */

alter table aluno add cpf varchar(11);

/* after significa coloca apos a tabela idade  */

alter table aluno add email varchar(150) after idade;


/* modify modificar uma coluna */ 

alter table aluno modify column cpf varchar(14);

/* drop permite remover uma determinada coluna */ 

alter table aluno drop column cpf;

alter table aluno add cpf varchar(14) after email;


/*  NORMALIZAÇÃO DE DADOS E AS FORMAS NORMAIS */

/* TRABALHANDO COM CHAVE PRIMARIA SIMPLES */

select * from aluno;


update aluno set cpf = '111.111.111-11' where nome = 'João';
update aluno set cpf = '222.111.111-11' where nome = 'Fernanda';
update aluno set cpf = '333.111.111-11' where nome = 'José';
update aluno set cpf = '444.111.111-11' where nome = 'Maria';
update aluno set cpf = '555.111.111-11' where nome = 'Marcelo';

select * from aluno where cpf = '333.111.111-11';

desc aluno;

/* coloca uma coluna como chave primaria a famosa primary key */

alter table aluno modify cpf varchar(14) primary key;

/* removendo chave primary da coluna especifica nesse caso cpf */

alter table aluno drop  cpf;

/* cria de novo cpf sem chave primari */

alter table aluno add cpf varchar(14) after email;

select * from aluno;


update aluno set cpf = '111.111.111-11' where nome = 'João';
update aluno set cpf = '222.111.111-11' where nome = 'Fernanda';
update aluno set cpf = '333.111.111-11' where nome = 'José';
update aluno set cpf = '444.111.111-11' where nome = 'Maria';
update aluno set cpf = '555.111.111-11' where nome = 'Marcelo';


/* criando colunda chave primary artificial */

alter table aluno add idaluno int primary key auto_increment;

/* se eu quiser seleciona um nome pelo id */

select * from aluno where idaluno = 4;


use universidade_u;

select * from aluno;

/* decompondo a coluna endereco em outras coluna pra ficar atonico pra seguir as regras 1fn padrao */

alter table aluno add logradouro varchar(100);
alter table aluno add numero varchar(10);
alter table aluno add complemento varchar(20);
alter table aluno add bairro varchar(100);
alter table aluno add cidade varchar(100);
alter table aluno add estado char(2);

/* agora temos que atualizar as colunas que foram criadas pelo id */

update
	aluno
 set   
	logradouro = 'Rua João de Abreu',
	numero = '650',
    complemento = 'ap112',
    bairro = 'Setor Oeste',
    cidade = 'Goiânia',
    estado = 'GO'
where
	idaluno = 5;

/* feito isso remova a coluna endereco */

alter table aluno drop endereco;


/* TRABALHANDO COM ATRIBUTOS MULTIVALORADOS  = coloca mais de um telefone*/

desc aluno;

select * from aluno;
select * from telefone;

alter table aluno modify column telefone varchar(60);

update aluno set telefone ='11 5555-2222 11 3333-4444' where idaluno = 1;

create table telefone(
	idtelefone int auto_increment primary key,
    numero varchar(20),
    tipo char(3)
    
);

insert into telefone(numero, tipo)value('11 5555-2222','res'); 
insert into telefone(numero, tipo)value('11 3333-4444','com');


alter table aluno drop column telefone;

/* CARDINALIDADE DE RELACIONAMENTO 1:N ENTRE TABELAS */


select idaluno,nome from aluno;
select * from telefone;

alter table telefone add column fk_idaluno int;

alter table telefone add constraint fk_aluno_telefone
	foreign key(fk_idaluno)
    references aluno (idaluno);

desc telefone;

/* CARDINALIDADE 1:N - INSERINDO REGISTRO RELACIONADOS */


select * from aluno;
select * from telefone;

update telefone set fk_idaluno = 1 where numero in ('11 5555-2222','11 3333-4444');

insert into telefone(numero, tipo, fk_idaluno) /*comando para inserir dados para registro */
	values('11 5555-5555', 'res' , 4);
    
    insert into telefone(numero, tipo, fk_idaluno) /*comando para inserir dados para registro */
	values('11 5555-7777', 'res' , 3 );
    
    insert into telefone(numero, tipo, fk_idaluno) /*comando para inserir dados para registro */
	values('11 5555-8888', 'res' , 3 );
    
    insert into telefone(numero, tipo, fk_idaluno) /*comando para inserir dados para registro */
	values('11 5555-9999', 'res' , 3 );
    

/* criando outro tabela endereco para associar a tabela aluno */



select * from aluno;



CREATE TABLE ENDERECO (
    idendereco int auto_increment PRIMARY KEY,
    logradouro varchar(100),
    numero varchar(10),
    complemento varchar(20),
    bairro varchar(100),
    cidade varchar(50),
    estado char(2),
    fk_idaluno int
);
 


ALTER TABLE ENDERECO ADD CONSTRAINT fk_aluno_endereco
    FOREIGN KEY (fk_idaluno)
    REFERENCES ALUNO (idaluno);


select * from endereco;
desc endereco;



/* CARDINALIDADE 1:1 - INSERINDO REGISTRO RELACIONADOS NA TABELA ENDERECO  */

insert into endereco (logradouro, numero, complemento, bairro, cidade, estado, fk_idaluno)
select logradouro, numero, complemento, bairro, cidade, estado, idaluno from aluno;

select * from aluno;

/* eleiminando essas colunas */

alter table aluno drop column logradouro;
alter table aluno drop column numero;
alter table aluno drop column complemento;
alter table aluno drop column bairro;
alter table aluno drop column cidade;
alter table aluno drop column estado;

select * from endereco where fk_idaluno = 1;

/* aumentando a complexibilidade do projeto criando tabela curso */



CREATE TABLE CURSO (
    idcurso int auto_increment PRIMARY KEY,
    descricao varchar(50)
);

select * from curso;


insert into curso(descricao)
	values('Curso Completo do Desenvolvedor NodeJS e MongoDB');
   
insert into curso(descricao)
	values('Desenvolvedor MUltiplataforma Android e IOS');
    
insert into curso(descricao)
	values('Desenvolvimento Web com Angular');
    
insert into curso(descricao)
	values('Desenvolvimento Web Completo 2019');
    
    
    /* CARDINALIDADE DE RELACIONAMENTO N:N  */
    
use universidade_u;

CREATE TABLE ALUNO_CURSO (
    id_alunocurso int auto_increment PRIMARY KEY,
    fk_idaluno int,
    fk_idcurso int
);

select * from aluno_curso;
 

 
ALTER TABLE ALUNO_CURSO ADD CONSTRAINT fk_aluno_curso
    FOREIGN KEY (fk_idaluno)
    REFERENCES ALUNO (idaluno);
 
ALTER TABLE ALUNO_CURSO ADD CONSTRAINT fk_curso_aluno
    FOREIGN KEY (fk_idcurso)
    REFERENCES CURSO (idcurso);

desc aluno_curso;

/* CARDINALIDADE N:N - INSERNDO REGISTRO RELACIONADOS */

select * from aluno;
select * from curso;

insert into aluno_curso(fk_idaluno, fk_idcurso)values(1, 3);
insert into aluno_curso(fk_idaluno, fk_idcurso)values(1, 4);

insert into aluno_curso(fk_idaluno, fk_idcurso)values(2, 2);
insert into aluno_curso(fk_idaluno, fk_idcurso)values(3, 1);
insert into aluno_curso(fk_idaluno, fk_idcurso)values(3, 2);
insert into aluno_curso(fk_idaluno, fk_idcurso)values(3, 3);
insert into aluno_curso(fk_idaluno, fk_idcurso)values(3, 4);
insert into aluno_curso(fk_idaluno, fk_idcurso)values(4, 1);


select * from aluno_curso;

/* TIPO DE DADOS ENUM 
permite a inclusao de apenas um unico dado entre  as opcoes possiveis

*/

use universidade_u;


select * from telefone;

alter table telefone drop column tipo;

alter table telefone add column tipo enum('res','com','cel');

desc telefone;

update telefone set tipo = 'res' where idtelefone = 1;
update telefone set tipo = 'cel' where idtelefone = 2;
update telefone set tipo = 'com' where idtelefone = 3;
update telefone set tipo = 'cel' where idtelefone = 4;
update telefone set tipo = 'com' where idtelefone = 5;
update telefone set tipo = 'cel' where idtelefone = 6;


/* null : indica que as coluna podem aceitar valores nulos (padrao)
NOT NULL : restricoes que impede a atribuição de valores nulos a coluna
*/

select * from telefone;
desc telefone;


alter table telefone modify column	numero varchar(20)not null;
alter table telefone modify column	tipo enum('res','com','cel')not null;
alter table telefone modify column	fk_idaluno int not null;



CREATE TABLE ENDERECO (
    idendereco int auto_increment PRIMARY KEY,
    logradouro varchar(100) not null,
    numero varchar(10) not null,
    complemento varchar(20),
    bairro varchar(100) not null,
    cidade varchar(50) not null,
    estado char(2) not null,
    fk_idaluno int not null
);

desc endereco;


alter table endereco modify column	logradouro varchar(100) not null;
alter table endereco modify column	numero varchar(10)not null;
alter table endereco modify column	bairro varchar(100) not null;
alter table endereco modify column	cidade varchar(50) not null;
alter table endereco modify column	estado char(2) not null;
alter table endereco modify column	fk_idaluno int not null;


/*  Unique Constraint

indica que os valores de uma determinada coluna devem ser unicos para todos os registros.

*/


alter table aluno add constraint uc_aluno_cpf unique(cpf);

select nome, cpf from aluno;

insert into aluno(sexo, idade, email, data_inscricao_curso, valor_pago_curso, ativo_sn, nome, cpf)
	values('F', 25, 'rosa@teste.com.br', '2019-01-05', 625, 1, 'rosa', '444.111.111-12');



desc aluno;

select * from aluno;

alter table aluno add constraint uc_aluno_email unique(email);


/* RESTRIÇOES DE INTEGRIDADE (ENTENDA MELHOR AS CONSTRAINTS)

RESTRIÇAO DE INTEGRIDADE (OU CONSTRAINT) É UMA REGRA DE CONSISTENCIA DE DADOS QUE É GARANTIDA PELO PROPRIO SGBD

PRIMARY KEY  ( INTEGRIDADE DE CHAVE + INTEGRIDADE DE ENTIDADE(UNIQUE E NOT NULL)
FOREIGN KEY ( INTEGRIDADE REFERENCIAL ( FAZ REFERENCIA PARA UMA PRIMARY KEY DE OUTRA TABELA)
UNIQUE - CONSTRAINT - (INTEGRIDADE DE UNICIDADE (PERMITE A INCLUSAO APENAS DE VALORES UNICOS)
ENUM ( INTEGRIDADE DE DOMINIO (LIMITA AS OPCOES DE VALORES PARA A COLUNA)
NOT NULL (INTEGRIDADE DE VAZIO ( IMPEDE A INCLUSAO DE VALORES NULOS)

*/

select * from endereco;
desc endereco;

alter table endereco add constraint uc_endereco_fk_idaluno unique(fk_idaluno);


insert into endereco (logradouro, numero, complemento, bairro, cidade, estado, fk_idaluno)
	values('Avenida Paulista', 500, null, 'Bela Vista', 'São Paulo', 'SP', 7);




/* SELECT - TRABALHANDO COM FUNCOES DE AGREGAÇÃO: COUNT, MAX, MIN, AVG, E SUM

COUNT - projeta o total registro da tabela conta
MAX - projeta o maior valor de todos os registro de uma tabela com base em uma coluna
MIN - projeta o menor valor de todos os registro de uma tabela com base em uma coluna
AVG - projeta a media dos valor de todos os registro de uma tabela com base em uma coluna
SUM - projeta a soma dos valor de todos os registro de uma tabela com base em uma coluna

*/


use universidade_u;

/* funcao count = conta qtos registro que tem na tabela */


select * from aluno;

select count(*) from aluno;

select count(distinct nome) from aluno; /* pra conta todos os registro com distinçao de nomes repetidos pra nao conta nome repetidos */

/* funcao max = retorna o maior valor com base em uma determinada coluna */

select max(valor_pago_curso) from aluno;


/* funcao min = retorna o menor valor com base em uma determinada coluna */

select min(valor_pago_curso) from aluno;

/* funcao avg = retorna a media de valor com base em uma determinada coluna */

select avg(valor_pago_curso) from aluno;


/* funcao sum = retorna a soma de valor com base em uma determinada coluna */

select sum(valor_pago_curso) from aluno;



/* fazendo todos em um unico comando */

select 
	max(valor_pago_curso),
    min(valor_pago_curso), 
    avg(valor_pago_curso), 
    sum(valor_pago_curso) 
from
	aluno;


/* seleciona so alunos cujos sexo seja 'F' */


select count(*) from aluno where sexo ='F';

```
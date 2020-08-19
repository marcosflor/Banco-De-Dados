// foi usado o comando para se criar o banco de dados e também um comando para definir as características que serão aceitas pelo banco de dados //

create database Industria

default char set utf8

default collate utf8_general_ci;


//Foi usado um comando para criar uma tabela para que os funcionários sejam cadastrados e junto com sua característica única, aqui chamada de RE//



create table funcionario(

RE int NOT NULL auto_increment,

nome varchar(40) NOT NULL,

Nascimento date NOT NULL,

Sexo enum ('Masculino', 'Feminino') NOT NULL,

primary key (RE)

) default charset = utf8;


//Usado o comando para alterar a tabela e inserir uma coluna no caso aqui foi acrescentado uma coluna responsável //



alter table funcionario

add column Responsavel varchar(10) Not Null;



//Foi usado um comando para inserir dados na tabela funcionário e assim fora acrescentado os dados na tabela //



insert into funcionario values

(DEFAULT,'Fernando Almeida Fachio', '1987-10-09', 'Masculino', 'Carlos'),

(DEFAULT,'Roberto Mathias Gonçalves', '1976-03-27', 'Masculino', 'Maza'),

(DEFAULT,'Cristiane Pereira Sampaio', '1980-07-23', 'Feminino', 'André'),

(DEFAULT,'Luciana Fagundes Neto', '1990-08-10', 'Feminino', 'André'),

(DEFAULT,'Marcos Renato Flor de Oliveira', '1998-04-10', 'Masculino', 'Maza');


//Foi usado um comando para criar uma tabela, areas, para que as áreas sejam cadastradas e junto com sua característica única, aqui fora chamada de CA//



create table areas(

CA int NOT NULL auto_increment,

area varchar (20) NOT NULL,

primary key (CA)

);


//Foi usado um comando para inserir dados na tabela funcionário e assim fora acrescentado os dados na tabela //



insert into areas values

(default,'Produção'),

(default,'Compras'),

(default,'Manutenção');



//Usado o comando para alterar a tabela e inserir uma coluna no caso aqui foi acrescentado uma coluna com o nome areadetrabalho e adicionado uma característica de chave estrangeira para a mesma//


alter table funcionario add areadetrabalho int;

alter table funcionario

add foreign key (areadetrabalho)

references areas(CA);



//Foi usado o comando para que fosse exibido os dados cadastrados relacionando usando o relacionamento entre as duas tabelas//



select Funcionario.RE, funcionario.nome, funcionario.Nascimento, funcionario.Sexo, funcionario.responsavel, areas.area

from funcionario join areas

on areas.CA = funcionario.areadetrabalho;​

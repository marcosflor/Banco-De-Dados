# Banco-De-Dados
create database Industria
default char set utf8
default collate utf8_general_ci;

create table funcionario(
nome varchar(40) NOT NULL,
Nascimento date,
Sexo enum ('Masculino', 'Feminino')
) default charset = utf8;

create table areas(
area varchar (20) NOT NULL
) default charset = utf8;

alter table funcionario
add column registro varchar(10) after sexo;

insert into funcionario
(nome, nascimento, sexo, registro)
values
('Marcos Renato Flor de Oliveira', '1998-04-10', 'Masculino', '0001');

insert into areas
(area)
values
('Manuteção');

select * from funcionario, areas

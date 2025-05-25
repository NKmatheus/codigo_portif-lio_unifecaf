create database db_sistema_faculdade;
drop database db_sistema_faculdade;
use db_sistema_faculdade;

create table tbl_aluno (
  id_aluno int not null primary key auto_increment,
  nome_aluno varchar(255) not null,
  rg varchar(12) not null,
  cpf varchar(11) not null,
  data_nascimento date not null,
  unique index(id_aluno)
  );
  
  insert into tbl_aluno (nome_aluno, rg, cpf, data_nascimento) values
  ('joão', '123456789101', '12345678910', '2004-05-09'),
  ('Ronaldo', '098765432112', '98765432101', '2003-09-22');
  
  select * from tbl_aluno;
  
  create table tbl_email(
  id_email int not null primary key auto_increment,
  email varchar(100) not null,
  id_aluno int not null,
  
  constraint FK_aluno_email
  foreign key(id_aluno) references tbl_aluno(id_aluno),
  
unique index (id_email)
  );
  
  insert into tbl_email (email, id_aluno) values
  ('joao@gmail.com',  1),
  ('ronaldinho@gmail.com', 2);
  
  select * from tbl_email;
  
  create table tbl_telefone(
  id_telefone int not null primary key auto_increment,
  telefone varchar(45),
  id_aluno int not null,
  
  constraint FK_aluno_telefone
  foreign key (id_aluno) references tbl_aluno(id_aluno)
  );
  
  insert into tbl_telefone(telefone, id_aluno) values 
  ('11987654321', 1 ),
  ('11912345678', 2 );
  
  select * from tbl_telefone;
  
  
  create table tbl_curso (
  id_curso int not null primary key auto_increment,
  nome_curso varchar(45) not null,
  unique index(id_curso)
  
  );
  
  insert into tbl_curso(nome_curso)values
  ('gestão de tecnologia'),
  ('desenvolvimento de sistemas'),
  ('educação fisica');
  
  select * from tbl_curso;
  
  create table tbl_professor(
  id_professor int not null primary key auto_increment,
  nome_professor varchar(255) not null,
  cpf varchar(11) not null,
  unique index (id_professor)
  );
  
  insert into tbl_professor(nome_professor, cpf) values
  ('cristiano', '09090807051'),
  ('junior', '11111111111'),
  ('romário', '22222222222');
  
  select * from tbl_professor;
  
  create table tbl_materia(
  id_materia int not null primary key auto_increment,
  nome_materia varchar(255) not null,
  unique index (id_materia)
  );
  
  insert into tbl_materia(nome_materia) values
  ('lógica de programação'),
  ('métodos ageis'),
  ('database modeling sql'),
  ('anatomia');
  
  select * from tbl_materia;
  
  create table tbl_aluno_curso(
  id int not null primary key auto_increment,
  id_aluno int not null,
  id_curso int not null,
  
  constraint FK_aluno_aluno_curso
  foreign key (id_aluno) references tbl_aluno(id_aluno),
  
  constraint FK_curso_aluno_curso
  foreign key (id_curso) references tbl_curso(id_curso),
  
  unique index(id)
  );
  
  insert into tbl_aluno_curso(id_aluno, id_curso) values
  ('1', '2'),
  ('2', '1' );
  
  create table tbl_curso_materia(
  id int not null primary key auto_increment,
  id_curso int not null,
  id_materia int not null,
  
  constraint FK_curso_curso_materia
  foreign key(id_curso) references tbl_curso(id_curso),
  
  constraint FK_materia_curso_materia
  foreign key(id_materia) references tbl_materia(id_materia),
  unique index(id)
  );
  
  insert into tbl_curso_materia(id_curso, id_materia) values
  ('1', 2),
  ('2', 2);
  

  create table tbl_professor_materia(
  id int not null primary key auto_increment,
  id_professor int not null,
  id_materia int not null,
  
  constraint FK_professor_professor_materia
  foreign key(id_professor) references tbl_professor(id_professor),
  
  constraint FK_materia_professor_materia
  foreign key(id_materia) references tbl_materia(id_materia), 
  unique index(id)
  );
  
insert into tbl_professor_materia(id_professor, id_materia)values
('1', '2'),
('2', '1');

create table tbl_nota_aluno_materia(
id int not null primary key auto_increment,
nota decimal(2,1) not null,
id_aluno int not null,
id_materia int not null,

constraint FK_aluno_nota_aluno_materia
foreign key(id_aluno) references tbl_aluno(id_aluno),

constraint FK_materia_nota_aluno_materia
foreign key (id_materia) references tbl_materia(id_materia),

unique index (id)
);

insert into tbl_nota_aluno_materia(nota, id_aluno, id_materia) values
('9.5', 1, 2),
('6.0', 2, 2);   

  
  select tbl_aluno.nome_aluno, tbl_aluno.cpf,
		 tbl_email.email,
         tbl_telefone.telefone,
         tbl_curso.nome_curso,
         tbl_materia.nome_materia,
         tbl_nota_aluno_materia.nota,
         tbl_professor.nome_professor

  from tbl_aluno inner join tbl_curso
  on tbl_aluno.id_aluno = tbl_curso.id_curso
  inner join tbl_curso_materia
     on tbl_curso.id_curso = tbl_curso_materia.id_curso
  inner join tbl_materia
     on tbl_materia.id_materia = tbl_curso_materia.id_materia
  inner join tbl_nota_aluno_materia
     on tbl_aluno.id_aluno = tbl_nota_aluno_materia.id_aluno
  inner join tbl_professor_materia
     on tbl_materia.id_materia = tbl_professor_materia.id_materia
  inner join tbl_professor
     on tbl_professor.id_professor = tbl_professor_materia.id_professor
  inner join tbl_email
     on tbl_aluno.id_aluno = tbl_email.id_email
  inner join tbl_telefone
     on tbl_aluno.id_aluno = tbl_telefone.id_telefone
  
  
  
  

  

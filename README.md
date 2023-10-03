# EXERCÍCIOS BANCO DE DADOS  
## Descrição

*Para está atividade duplique a base de dados utilizada na ATIVIDADE INDIVIDUAL – TEMA: BASE DE DADOS ANIMAIS;*


	CREATE TABLE animais (
	id int,
	nome varchar(50),
	nasc date,
 	peso decimal(10,2),
  	cor varchar(50)
	);

	INSERT INTO animais VALUES (01, 'Ágata','2015-04-09',13.9,'branco');
	INSERT INTO animais VALUES (02, 'Félix','2016-06-06',14.3,'preto');
	INSERT INTO animais VALUES (03, 'Tom','2013-02-08', 11.2,'azul');
	INSERT INTO animais VALUES(04, 'Garfield','2015-07-07',17.1,'laranja');
	INSERT INTO animais VALUES(05,'Frajola','2013-08-01',13.7,'preto');
	INSERT INTO animais VALUES(06,'Manda-chuva','2012-02-03',12.3,'amarelo');
	INSERT INTO animais VALUES(07,'Snowball','2014-04-06',13.2,'preto');
	INSERT INTO animais VALUES(10,'Ágata','2015-08-03',11.9,'azul');
	INSERT INTO animais VALUES(11,'Gato de Botas','2012-12-10',11.6,'amarelo');
	INSERT INTO animais VALUES(12,'Kitty','2020-04-06',11.6,'amarelo');
	INSERT INTO animais VALUES(13,'Milu','2013-02-04',17.9,'branco');
	INSERT INTO animais VALUES(14,'Pluto','2012-01-03',12.3,'amarelo');
	INSERT INTO animais VALUES(15,'Pateta','2015-05-01',17.7,'preto');
	INSERT INTO animais VALUES(16,'Snoopy','2013-07-02',18.2,'branco');
	INSERT INTO animais VALUES(17,'rex','2019-11-03',19.7,'beje');
	INSERT INTO animais VALUES(20,'Bidu','2012-09-08',12.4,'azul');
	INSERT INTO animais VALUES(21,'Dum Dum','2015-04-06',11.2,'laranja');
	INSERT INTO animais VALUES(22,'Muttley','2011-02-03',14.3,'lvaranja');
	INsERT INTO animais VALUES(23,'Scooby','2012-01-02',19.9,'marrom');
	INSERT INTO animais VALUES(24,'Rufus','2014-04-05',19.7,'branco');
	INSERT INTO animais VALUES(25,'Rex','2021-08-19',19.7,'branco');

A imagem abaixo mostra a tabela criada ao lado.
![exer1](https://raw.githubusercontent.com/FabioCCamarg/Aula8BD/main/imagem/BaseDadosAnimais.png)

 *Após a criação de uma nova base, execute os códigos abaixo:*

 /*Altere o nome do Pateta para Goofy;*/
 /*comando para remover segurança da plataforma*/
 
  		SET SQL_SAFE_UPDATES = 0;

	UPDATE animais
	SET nome = 'Goofy'
	WHERE nome = 'Pateta';

/*Altere o peso do Garfield para 10 quilogramas;*/

	UPDATE animais
	SET peso = 10.0
	WHERE nome = 'Garfield';

/*Crie um campo altura para os animais;*/

	ALTER TABLE animais
	ADD altura decimal(3,2);

/*Altere a cor de todos os gatos para laranja;*/

	ALTER TABLE animais
	ADD especie VARCHAR(100);

	UPDATE animais
	SET especie = 'cachorro'
	WHERE nome in ('Félix','Pluto','Pateta','Snoopy','rex','Bidu');

	UPDATE animais
	SET especie = 'gato'
	WHERE nome in ('Tom','Garfield','Gato de Botas','Dum Dum');

	UPDATE animais
	SET cor = 'laranja'
	WHERE especie = 'gato';

/*Crie um campo altura para os animais;*/

	ALTER TABLE animais
	ADD observacao VARCHAR(50);

/*Remova todos os animais que pesam mais que 200 quilogramas.*/

	DELETE FROM animais
	WHERE peso >200;
 
/*Remova todos os animais que o nome inicie com a letra ‘C’.*/

	DELETE FROM animais
	WHERE nome like 'C%';

/*Remova o campo cor dos animais;*/

	ALTER TABLE animais
	DROP cor;

/*Aumente o tamanho do campo nome dos animais para 80 caracteres;*/

	ALTER TABLE animais
	MODIFY nome VARCHAR(80)NOT NULL;

/*Remova todos os gatos e cachorros.*/

	DELETE FROM animais
	WHERE especie = 'cachorro';

	DELETE FROM animais
	WHERE especie = 'gato';

/*Remova o campo data de nascimento dos animais.*/

	ALTER TABLE animais
	DROP nasc;

/*Remova todos os animais.*/

	DELETE FROM animais;

/*Remova a tabela especies.*/

	ALTER TABLE animais
 	DROP especie;

	

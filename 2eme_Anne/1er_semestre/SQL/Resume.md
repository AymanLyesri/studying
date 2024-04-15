	   PRIMARY KEY (ID),
    	FOREIGN KEY (ID) REFERENCES origin_table(PID)

CREATE/DROP DATABASE NomBD ;

USE NomBD ;                                          DROP -> all  /// delete -> values

CREATE/DROP TABLE NomTable( ... ) ;

ALTER TABLE nomTable ADD|DROP|CHANGE|MODIFY column ;           --->(columns)

$$CHANGE$$ ---> rename       ||ex : ...CHANGE COLUMN id-old id-new int ;
$$MODIFY$$---> modify type ||ex : ...MODIFY COLUMN id-current int-new ;
                                                    
INSERT INTO  nomTable (champ1,champ2,...) VALUES (...) ;

UPDATE NomTable SET column WHERE condition ;            --->(values)

DELETE FROM NomTable WHERE condition ;

SELECT colonne1,colonne2,... FROM table1,table2,... WHERE table1.col=table2.col ;

SELECT DISTINCT id aut FROM auteur ;                      --->**no repetition
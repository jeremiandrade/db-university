# 1.Selezionare tutti gli studenti nati nel 1990 (160)
SELECT * 
FROM schemauniversity.students
WHERE YEAR(`date_of_birth`)= '1990';


# 2.Selezionare tutti i corsi che valgono più di 10 crediti (479)
SELECT * 
FROM schemauniversity.courses
WHERE `cfu` > 10;


# 3.Selezionare tutti gli studenti che hanno più di 30 anni

SELECT * 
FROM schemauniversity.students
WHERE `date_of_birth`<'1996-06-11';


# 4.Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)
SELECT * 
FROM schemauniversity.courses
WHERE `period`= 'I semestre'
AND `year`= 1;


# 5.Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)
SELECT * 
FROM schemauniversity.exams
WHERE `hour`>= '14:00:00'
AND `date`= '2020-06-20';


# 6.Selezionare tutti i corsi di laurea magistrale (38)
SELECT * 
FROM schemauniversity.degrees
WHERE `name` LIKE '%magistrale%';

# 7.Da quanti dipartimenti è composta l'università? (12)
SELECT * 
FROM schemauniversity.departments;


# 8.Quanti sono gli insegnanti che non hanno un numero di telefono? (50)
SELECT * 
FROM schemauniversity.teachers
WHERE `phone`IS NULL;

-------------------------------------------------------------


# 1.Contare quanti iscritti ci sono stati ogni anno
SELECT COUNT(id) AS`registered`
FROM schemauniversity.students
GROUP BY `enrolment_date`;
# chiedere



# 2.Contare gli insegnanti che hanno l'ufficio nello stesso edificio
SELECT COUNT(id) AS `teachers`, `office_number`
FROM schemauniversity.teachers
GROUP BY `office_number`;



# 3.Calcolare la media dei voti di ogni appello d'esame
SELECT AVG(vote) AS `med_vote`,`exam_id` 
FROM schemauniversity.exam_student
GROUP BY `exam_id`;
# chiedere 



# 4.Contare quanti corsi di laurea ci sono per ogni dipartimento
SELECT COUNT(id) AS `courses`,`name`
FROM schemauniversity.degrees
GROUP BY `name`;
 # chiedere
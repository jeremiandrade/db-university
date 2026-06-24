
# Join exercises


# 1.Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
SELECT *
FROM `students`
JOIN `degrees` ON `students`.`degree_id`= `degrees`.`id`
WHERE `degrees`.`name`= "Corso di Laurea in Economia";


# 2.Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

SELECT *
FROM schemauniversity.degrees
JOIN schemauniversity.departments ON `degrees`.`department_id`= `departments`.`id`
WHERE `departments`.`name`= "Dipartimento di Neuroscienze" AND `degrees`.`level`="magistrale";


# 3.Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
SELECT `teachers`.`name` AS 'Insegnante', courses.name AS "Corso"
FROM `course_teacher`
JOIN `teachers` ON `course_teacher`.`teacher_id`= `teachers`.`id`
JOIN `courses` ON `course_teacher`.`course_id`= `courses`.`id`
WHERE `teachers`.`id`= 44;


# 4.Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui
# sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

SELECT *
FROM `students`
JOIN `degrees` ON `students`.`degree_id`= `degrees`.`id`
JOIN `departments` ON `degrees`.`department_id`= `departments`.`id`
ORDER BY `students`.`surname` ASC, `students`.`name` ASC;

# 5.Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

SELECT teachers.name, teachers.surname, degrees.name AS degrees, courses.name AS courses, courses.description AS description
FROM `course_teacher`
JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id`
JOIN `teachers` ON `course_teacher`.`teacher_id` = `teachers`.`id`
JOIN `degrees` ON `courses`.`degree_id` = `degrees`.`id`;


# 6.Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

SELECT  DISTINCT teachers.name, teachers.surname, departments.name AS departments
FROM `course_teacher`
JOIN `teachers` ON `course_teacher`.`teacher_id` = `teachers`.`id`
JOIN `courses` ON `course_teacher`. `course_id` = `courses`.`id`
JOIN `degrees` ON `courses`.`degree_id` = `degrees`.`id`
JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
WHERE `departments`.`name` = "Dipartimento di Matematica"
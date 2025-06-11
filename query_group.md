1. Contare quanti iscritti ci sono stati ogni anno

2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

SELECT `office_address`, COUNT(\*) AS number_teachers
FROM `teachers`
GROUP BY `office_address`;

3.  Calcolare la media dei voti di ogni appello d'esame

4.  Contare quanti corsi di laurea ci sono per ogni dipartimento
    SELECT `department_id`, COUNT(\*) AS number_courses
    FROM `degrees`
    GROUP BY `department_id`;

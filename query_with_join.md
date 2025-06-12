### 1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```sql

SELECT
`students`.\*,
`degrees`.`id` AS `degree_id`,
`degrees`.`name` AS `degree_name`

FROM `students`
INNER JOIN `degrees`
ON `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = "Corso di Laurea in Economia"
```

### 2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di

### Neuroscienze

```sql

   SELECT
   `courses`.\*,
   `degrees`.`id` AS `degree_id`,
   `degrees`.`name` AS `degree_name`,
   `departments`.`id` AS `department_id`,
   `departments`.`name` AS `department_name`

FROM `courses`
INNER JOIN `degrees`
ON `courses`.`degree_id` = `degrees`.`id`
INNER JOIN `departments`
ON `degrees`.`department_id` = `departments`.`id`
WHERE `departments`.`name` = "Dipartimento di Neuroscienze"
AND `degrees`.`level`= "magistrale";
```

### 3.Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```sql

SELECT
`courses`.\*,
`teachers`.`id` AS `teacher_id`,
`teachers`.`name` AS `teacher_name`,
`teachers`.`surname` AS `teacher_surname`

FROM `courses`
INNER JOIN `course_teacher`
ON `courses`.`id` = `course_teacher`.`teacher_id`
INNER JOIN`teachers`
ON `course_teacher`.`teacher_id` = `teachers`.`id`
WHERE `teacher_id` = 44
```

### 4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui

### sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e

### nome

```sql

SELECT
`students`._ ,
`degrees`._,
`departments`.\*

FROM `students`
INNER JOIN `degrees`
ON `students`.`degree_id` = `degrees`.`id`
INNER JOIN `departments`
ON `degrees`.`department_id` = `departments`.`id`
ORDER BY `surname` ASC
```

#### 5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

```sql

SELECT
`degrees`.`id`AS `degree_id`,
`degrees`.`name`AS `degree_name`,
`courses`. `id`AS `course_id`,
`courses`. `name`AS `course_name`,
`teachers`.`id` AS `teacher_id`,
`teachers`.`name` AS `teacher_name`

FROM `degrees`
INNER JOIN `courses`
ON `degrees`.`id` = `courses`.`degree_id`
INNER JOIN `course_teacher`
ON `courses`.`id` = `course_teacher`.`teacher_id`
INNER JOIN`teachers`
ON `course_teacher`.`teacher_id` = `teachers`.`id`
```

### 6. Selezionare tutti i docenti che insegnano nel Dipartimento di

### Matematica (54)

```sql

SELECT

`teachers`.\*,
`departments`.`id` AS `department_id`,
`departments`.`name` AS `department_name`

FROM `teachers`
INNER JOIN `course_teacher`
ON `teachers`.`id` = `course_teacher`.`teacher_id`
INNER JOIN `courses`
ON `courses`.`id` = `course_teacher`.`course_id`
INNER JOIN `degrees`
ON `courses`.`degree_id` = `degrees`.`id`
INNER JOIN `departments`
ON `degrees`.`department_id` = `departments`.`id`
WHERE `departments`.`name` = "Dipartimento di matematica"

```

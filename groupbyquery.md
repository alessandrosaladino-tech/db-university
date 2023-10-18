# Group by query

## 1.Group Contare quanti iscritti ci sono stati ogni anno
```sql
SELECT COUNT(*) AS `student_count`, YEAR(`enrolment_date`)
FROM `students`
GROUP BY BY YEAR(`enrolment_date`)
```

## 2.Group Contare gli insegnanti che hanno l'ufficio nello stesso edificio
```sql
SELECT COUNT(*) AS `teachers_count`, `office_address`
FROM `teachers`
GROUP BY `office_address`;
```
## 3.Group Calcolare la media dei voti di ogni appello d'esame
```sql
SELECT COUNT(`exam_id`) AS `exams_count`, AVG(`vote`) AS `average_vote` 
FROM `exam_student` 
GROUP BY `exam_id`;
```

### 4.Group Divisione per singolo esame
```sql
SELECT COUNT(`exam_id`) AS `exams_count`, AVG(`vote`) AS `average_vote`, `courses`.`name` AS `course_name`
FROM `exam_student`
JOIN `exams` ON `exam_id` = `exams`.`id`
JOIN `courses` ON `course_id` = `courses`.`id`
GROUP BY `exam_id`;
```

## 5.Group Contare quanti corsi di laurea ci sono per ogni dipartimento
```sql
SELECT COUNT(*) AS `degrees_count`, `department_id`
FROM `degrees`
GROUP BY `department_id`;
```

### 6.Group Con nome dipartimento
```sql
SELECT COUNT(*) AS `degrees_count`, `department_id`, `departments`.`name` AS `department_name`
FROM `degrees`
JOIN `departments` ON `department_id` = `departments`.`id`
GROUP BY `department_id`;
```





## Joins

## 1.Joins Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
```sql
SELECT `students`.`name`, `students`.`surname`, `students`.`registration_number`, `degrees`.`name` AS `degree_name`
FROM `students`
JOIN `degrees` ON `degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia';
```


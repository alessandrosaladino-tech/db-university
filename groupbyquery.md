# Group by query

## 1. Contare quanti iscritti ci sono stati ogni anno
```sql
SELECT COUNT(*) AS `student_count`, YEAR(`enrolment_date`)
FROM `students`
GROUP BY BY YEAR(`enrolment_date`)
```

## 2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio
```sql
SELECT COUNT(*) AS `teachers_count`, `office_address`
FROM `teachers`
GROUP BY `office_address`;
```
## 3. Calcolare la media dei voti di ogni appello d'esame
```sql
SELECT COUNT(`exam_id`) AS `exams_count`, AVG(`vote`) AS `average_vote` 
FROM `exam_student` 
GROUP BY `exam_id`;
```

### 4. Divisione per singolo esame
```sql
SELECT COUNT(`exam_id`) AS `exams_count`, AVG(`vote`) AS `average_vote`, `courses`.`name` AS `course_name`
FROM `exam_student`
JOIN `exams` ON `exam_id` = `exams`.`id`
JOIN `courses` ON `course_id` = `courses`.`id`
GROUP BY `exam_id`;
```

## 5. Contare quanti corsi di laurea ci sono per ogni dipartimento
```sql
SELECT COUNT(*) AS `degrees_count`, `department_id`
FROM `degrees`
GROUP BY `department_id`;
```


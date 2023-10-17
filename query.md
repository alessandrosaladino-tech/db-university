DB University

## 1. Selezionare tutti gli studenti nati nel 1990 (160)
SELECT * FROM `students`
WHERE YEAR(date_of_birth) = 1990;

## 2. Selezionare tutti i corsi che valgono più di 10 crediti (479)
SELECT * FROM `courses` 
WHERE cfu > 10;

## 3. Selezionare tutti gli studenti che hanno più di 30 anni
# https://www.w3resource.com/mysql/date-and-time-functions/mysql-timestampdiff-function.php
SELECT * FROM `students` 
WHERE TIMESTAMPDIFF(YEAR, `date_of_birth`, CURRENT_DATE) > 30;

(3468 TOTAL)

## 4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)
SELECT *FROM `courses`
WHERE `period` = 'I semestre' AND year = '1';
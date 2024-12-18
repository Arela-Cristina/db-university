
### 1. Selezionare tutti gli studenti nati nel 1990 (160)

```SELECT *
FROM `db_university`.`students`
WHERE year(`date_of_birth`) = 1990
```
160 row(s) returned


### 2. Selezionare tutti i corsi che valgono più di 10 crediti

```SELECT *
FROM `db_university`.`courses`
WHERE `cfu` > 10
```

479 row(s) returned


### 3. Selezionare tutti gli studenti che hanno più di 30 anni

```SELECT *
FROM `db_university`.`students`
WHERE year(`date_of_birth`) < 1994
```
1000 row(s) returned limit 1000


### 4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di
laurea (286)

```SELECT *
FROM `db_university`.`courses`
WHERE `degree_id` = 1 AND `period` = 'I semestre'
```
<!-- controlar -->
10 row(s) returned limit 1000   


### 5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del
20/06/2020 (21)

```SELECT *
FROM `db_university`.`exams`
WHERE `date` = '2020-06-20' AND `hour` > '14:00'
```
21 row(s) returned limit 1000  


### 6. Selezionare tutti i corsi di laurea magistrale (38)

```SELECT *
FROM `db_university`.`degrees`
WHERE `name` LIKE '%Magistrale%'
```
38 row(s) returned limit 1000 


### 7. Da quanti dipartimenti è composta l'università? (12)

```
SELECT COUNT(`name`) AS 'Total_departments'
FROM `db_university`.`departments`
```
total_departaments 12


### 8. Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

```SELECT *
FROM `db_university`.`teachers`
WHERE `phone` IS  NULL
```

50 row(s) returned limit 1000 


### 9. Inserire nella tabella degli studenti un nuovo record con i propri dati (per il campo
degree_id, inserire un valore casuale)

```
INSERT INTO `db_university`.`students` (`degree_id`,`name`, `surname`, `date_of_birth`, `fiscal_code`, `enrolment_date`, `registration_number`, `email`);

VALUES ('20','Cristina', 'arela', '1995-11-13', 'ABCDEEFHIJK8', '2017-03-21', '666', 'instagrandine@gmail.com');
```

```SELECT * 
FROM `db_university`.`students`
WHERE `surname` LIKE '%arela'
```

### 10. Cambiare il numero dell’ufficio del professor Pietro Rizzo in 126

```
UPDATE `db_university`.`teachers`
SET `phone` = '320-747-4428'
WHERE `id` = 58;
```


11. Eliminare dalla tabella studenti il record creato precedentemente al punto 9

```
DELETE FROM `db_university`.`students`
WHERE `id` = '5001'
```
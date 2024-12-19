### 1. Contare quanti iscritti ci sono stati ogni anno
``` 
SELECT COUNT(*) AS `iscritti`, YEAR(`enrolment_date`) AS `enrolment_year`
FROM `db_university`.`students`
GROUP BY `enrolment_date`
```

### 2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

```
SELECT COUNT(*), `office_address`
FROM `db_university`.`teachers`
GROUP BY `office_address`;
```


### 3. Calcolare la media dei voti di ogni appello d'esame
```
SELECT COUNT(*), AVG(`vote`) AS `vote_avg`
FROM `db_university`.`exam_student`
GROUP BY `vote`;
```

### 4. Contare quanti corsi di laurea ci sono per ogni dipartimento
```
SELECT `department_id`, COUNT(*) AS `numeri_corsi_di_laurea`
FROM `db_university`.`degrees`
GROUP BY  `department_id`
```


### 1. Selezionare tutti gli studenti iscritti al 
```
SELECT * 
FROM `degrees`
JOIN `students`
ON `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia' 
```

### 2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

```
SELECT * 
FROM `degrees`
JOIN `departments`
ON `departments`.`id` = `degrees`.`department_id`
WHERE `department_id` = '7'
```



### 3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
### 4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome
### 5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
### 6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)
### 7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.
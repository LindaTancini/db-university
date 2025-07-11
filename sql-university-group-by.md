# MySQL: GROUP BY

### 1. Contare quanti iscritti ci sono stati ogni anno

```
SELECT
    YEAR(enrolment_date) AS `anno`,
    COUNT(*) AS `numero_iscritti`
FROM
    `students`
GROUP BY `anno`
ORDER BY `numero_iscritti`;
```

---

### 2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

```
SELECT
    COUNT(*)
FROM
    `teachers`
GROUP BY `office_address`;
```

---

### 3. Calcolare la media dei voti di ogni appello d'esame

```
SELECT
    AVG(`vote`) AS `media`, `exam_id`
FROM
    `exam_student`
GROUP BY `exam_id`;
```

---

### 4. Contare quanti corsi di laurea ci sono per ogni dipartimento

```
SELECT
    `department_id`, COUNT(*) AS `numero_corsi`
FROM
    `degrees`
GROUP BY `department_id`;
```

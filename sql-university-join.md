# MySQL: JOIN

### 1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```
SELECT
    `students`.name, `students`.surname
FROM
    `students`
        JOIN
    `degrees` ON `degree_id` = `students`.degree_id
WHERE
    `degrees`.name = 'Corso di Laurea in Economia'
```

---

### 2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

```
SELECT
    `courses`.name
FROM
    `courses`
        JOIN
    `degrees` ON `degrees`.id = `courses`.degree_id
        JOIN
    `departments` ON `departments`.id = `degrees`.department_id
WHERE
    `departments`.name = 'Dipartimento di Neuroscienze'
        AND `degrees`.level = 'magistrale';
```

---

### 3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```
SELECT
    `courses`.name
FROM
    `courses`
        JOIN
    `course_teacher` ON `courses`.id = `course_teacher`.course_id
        JOIN
    `teachers` ON `teachers`.id = `course_teacher`.teacher_id
WHERE
    `teachers`.id = 44;
```

---

### 4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

```
SELECT
    `students`.name AS `nome_studente`,
    `students`.surname AS `cognome_studente`,
    `degrees`.name AS `corso_di_laurea`,
    `departments`.name AS `dipartimento`
FROM
    `students`
        JOIN
    `degrees` ON `degrees`.id = `students`.degree_id
        JOIN
    `departments` ON `departments`.id = `degrees`.department_id
ORDER BY nome_studente , cognome_studente
```

---

### 5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

```
SELECT
    `courses`.name AS `nome_corso`,
    `degrees`.name AS `laurea`,
    `teachers`.name AS `nome_insegnante`,
    `teachers`.surname AS `cognome_insegnante`
FROM
    `courses`
        JOIN
    `degrees` ON `degrees`.id = `courses`.degree_id
        JOIN
    `course_teacher` ON `courses`.id = `course_teacher`.course_id
        JOIN
    `teachers` ON `teachers`.id = `course_teacher`.teacher_id
```

---

### 6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

```
SELECT DISTINCT
    `teachers`.name AS `nome_insegnante`,
    `teachers`.surname AS `cognome_insegnante`
FROM
    `teachers`
        JOIN
    `course_teacher` ON `teachers`.id = `course_teacher`.teacher_id
        JOIN
    `courses` ON `courses`.id = `course_teacher`.course_id
        JOIN
    `degrees` ON `degrees`.id = `courses`.degree_id
        JOIN
    `departments` ON `departments`.id = `degrees`.department_id
WHERE
    `departments`.name = 'Dipartimento di Matematica'
```

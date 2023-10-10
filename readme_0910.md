## DB_university

1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
   <br><br>

   SELECT \* FROM `students`
   JOIN `degrees`
   ON `degrees` . `id` = `students` . `degree_id`
   WHERE `degrees` . `name` = "Corso di Laurea in Economia";

---

2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di
   Neuroscienze <br><br>
   SELECT \* FROM `degrees`
   JOIN `departments`
   on `departments` . `id` = `degrees`. `department_id`
   WHERE `level` = "magistrale";

---

3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
   <br><br>
   SELECT \* FROM `courses`
   JOIN `teachers`
   ON `teachers` . `id` = `courses` . `degree_id`
   WHERE `teachers` . `name` = "Fulvio"
   AND `teachers` . `surname` = "Amato";

---

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui
   sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e
   nome <br><br>

   SELECT `students`.`name`, `students` . `surname`, `degrees`. `name` , `departments` . `name`

   FROM `students`

   JOIN `degrees`

   ON `degrees` . `id` = `students` . `degree_id`

   JOIN `departments`

   ON `departments` . `id` = `degrees` . `department_id`;

---

5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti <br><br>
   SELECT `courses`.`name`, `degrees` . `name`, `teachers`. `name`

   FROM `courses`

   JOIN `degrees`
   ON `degrees` . `id` = `courses` . `degree_id`

   JOIN `teachers`
   ON `teachers` . `id` = `courses` . `degree_id`;

---

6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54) <br><br>
   SELECT DISTINCT `teachers` .`name`, `teachers` . `surname`
   FROM `departments`

   JOIN `degrees` ON `departments` . `id` = `degrees`. `department_id`
   JOIN `courses` ON `courses` . `degree_id` = `degrees` . `id`
   JOIN `course_teacher` ON `courses` . `id` = `course_teacher` . `course_id`
   JOIN `teachers` ON `teachers` . `id` = `course_teacher` . `teacher_id`

   WHERE `departments`.`name` = "Dipartimento di Matematica";

---

## GROUP BY

1. Contare quanti iscritti ci sono stati ogni anno <br><br>
   SELECT YEAR(`enrolment_date`) AS "anno_iscrizione", COUNT(\*) AS "numero_studenti"
   FROM `students`
   GROUP BY YEAR(`enrolment_date`);

---

2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio <br><br>

---

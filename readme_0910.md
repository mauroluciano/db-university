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

---

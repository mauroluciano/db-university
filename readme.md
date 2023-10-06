## DB_university

1. Selezionare tutti gli studenti nati nel 1990 (160)<br><br>
   SELECT \* FROM `students` WHERE `date_of_birth`BETWEEN '1990-01-01' AND '1990-12-31';

---

2. Selezionare tutti i corsi che valgono più di 10 crediti (479)<br><br>
   SELECT \* FROM `courses` WHERE `cfu`> 10;

---

3. Selezionare tutti gli studenti che hanno più di 30 anni <br><br>
   SELECT \* FROM `students` WHERE `date_of_birth` BETWEEN '1993-10-06' AND '2023-10-06';

---

4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di
   laurea (286)<br><br>
   SELECT \* FROM `courses` WHERE `year` = 1 AND `period` = "I semestre";

---

5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del
   20/06/2020 (21)<br><br>
   SELECT \* FROM `exams` WHERE HOUR >= "14:00";

---

6. Selezionare tutti i corsi di laurea magistrale (38)<br><br>
   SELECT \* FROM `degrees` WHERE `level` = "magistrale";

---

7. Da quanti dipartimenti è composta l'università? (12)<br><br>
   SELECT \* FROM `departments`AS `name`;

---

8. Quanti sono gli insegnanti che non hanno un numero di telefono? (50)<br><br>
   SELECT \* FROM `teachers` WHERE `phone` is NULL;

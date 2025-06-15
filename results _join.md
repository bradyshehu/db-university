# SELECT

## Prima query

SELECT `*`
FROM
`students`

INNER JOIN `degrees`
ON `students`.`degree_id` = `degrees`.`id`

WHERE `degrees`.`id` = 53

LIMIT 0, 1000 **68 row(s)** returned 0.000 sec / 0.000 sec

## Seconda query

SELECT `*`
FROM
`degrees`

INNER JOIN `departments`
ON `degrees`.`department_id` = `departments`.`id`

WHERE `departments`.`id` = 7 AND
`degrees`.`level` = "Magistrale"

LIMIT 0, 1000 **1 row(s)** returned 0.000 sec / 0.000 sec

## Terza query

SELECT `*`
FROM
`courses`

INNER JOIN `course_teacher`
ON `course_teacher`.`course_id` = `courses`.`id`

WHERE `course_teacher`.`teacher_id` = 44

LIMIT 0, 1000 **11 row(s)** returned 0.000 sec / 0.000 sec

### OPPURE

SELECT `*`
FROM
`courses`

INNER JOIN `course_teacher`
ON `course_teacher`.`course_id` = `courses`.`id`

INNER JOIN `teachers`
ON `course_teacher`.`teacher_id` = `teachers`.`id`

WHERE `teachers`.`id` = 44

LIMIT 0, 1000 **11 row(s)** returned 0.000 sec / 0.000 sec

## Quarta query

SELECT `*` FROM
`students`

LEFT JOIN `degrees`
ON `degrees`.`id` = `students`.`degree_id`

INNER JOIN `departments`
ON `departments`.`id`=`degrees`.`department_id`

ORDER BY `students`.`surname` ASC, `students`.`name` ASC

LIMIT 0, 1000 **1000 row(s)** returned 0.015 sec / 0.000 sec

## Quinta query

SELECT `*`
FROM
`degrees`

RIGHT JOIN `courses`
ON `degrees`.`id`= `courses`.`degree_id`

INNER JOIN `course_teacher`
ON `courses`.`id` = `course_teacher`.`course_id`

INNER JOIN `teachers`
ON `course_teacher`.`teacher_id` = `teachers`.`id`
LIMIT 0, 1000 1000 row(s) returned 0.000 sec / 0.000 sec

## Sesta query

SELECT DISTINCT `teachers`.`*`

FROM
`teachers`

INNER JOIN `course_teacher`
ON `teachers`.`id` = `course_teacher`.`teacher_id`

INNER JOIN `courses`
ON `course_teacher`.`course_id`= `courses`.`id`

INNER JOIN `degrees`
ON `degrees`.`id` = `courses`.`degree_id`

INNER JOIN `departments`
ON `departments`.`id` = `degrees`.`department_id`

WHERE `departments`.`id` = 5

LIMIT 0, 1000 **54 row(s)** returned 0.000 sec / 0.000 sec

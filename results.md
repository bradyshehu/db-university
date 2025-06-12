# SELECT

## Prima query

SELECT \*
FROM
`students`
WHERE YEAR(`date_of_birth`) = 1990

LIMIT 0, 1000 **160 row(s)** returned 0.000 sec / 0.000 sec

## Seconda query

SELECT \*
FROM
`courses`
WHERE `cfu` > 10

LIMIT 0, 1000 **479 row(s)** returned 0.000 sec / 0.000 sec

## Terza query

SELECT \*
FROM
`students`
WHERE `date_of_birth` <= DATE_SUB(NOW(), INTERVAL 30 YEAR)

LIMIT 0, 1000 **1000 row(s)** returned 0.000 sec / 0.000 sec

## Quarta query

SELECT \*
FROM
`courses`
WHERE `year`=1 AND `period` = "I semestre"

LIMIT 0, 1000 **286 row(s)** returned 0.000 sec / 0.000 sec

## Quinta query

SELECT \*
FROM
`exams`
WHERE `date` = '2020-06-20'
AND `hour` > '14:00:00'

LIMIT 0, 1000 **21 row(s)** returned 0.000 sec / 0.000 sec

## Sesta query

SELECT \*
FROM
`degrees`
WHERE `level` = 'magistrale'

LIMIT 0, 1000 **38 row(s)** returned 0.000 sec / 0.000 sec

## Settima query

SELECT COUNT(\*)
FROM
`departments`

ANS(12)

LIMIT 0, 1000 1 row(s) returned 0.000 sec / 0.000 sec

## Ottava query

SELECT \*
FROM
`teachers`
WHERE `phone` IS NULL

LIMIT 0, 1000 **50 row(s)** returned 0.000 sec / 0.000 sec

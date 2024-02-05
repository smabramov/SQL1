# «SQL. Часть 1»-Абрамов Сергей

---

### Задание 1
Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.

# Решение.

`SELECT DISTINCT district FROM address WHERE (district LIKE 'K%a' AND district NOT LIKE '% %');`

![1](https://github.com/smabramov/SQL1/blob/e12468790edf0c72fe3d0c77d06841e4fbd3342e/jpg/1.jpg)


---

### Задание 2
Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года включительно и стоимость которых превышает 10.00

# Решение.

`SELECT * FROM payment WHERE (DATE(payment_date) BETWEEN '2005-06-15' AND '2005-07-18') AND amount > 10;`

![2](https://github.com/smabramov/SQL1/blob/e12468790edf0c72fe3d0c77d06841e4fbd3342e/jpg/2.jpg)

---

### Задание 3
Получите последние пять аренд фильмов.

# Решение.

`SELECT * FROM payment ORDER BY payment_date DESC LIMIT 5;`

![3](https://github.com/smabramov/SQL1/blob/e12468790edf0c72fe3d0c77d06841e4fbd3342e/jpg/3.jpg)

---

### Задание 4
Одним запросом получите активных покупателей, имена которых Kelly или Willie.

Сформируйте вывод в результат таким образом:

все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,
замените буквы 'll' в именах на 'pp'.

# Решение.

`SELECT customer_id, last_name, LOWER( REPLACE(first_name,'LL','PP')) FROM customer WHERE (first_name LIKE "Kelly" OR first_name LIKE "Willie");`


![4](https://github.com/smabramov/SQL1/blob/e12468790edf0c72fe3d0c77d06841e4fbd3342e/jpg/4.jpg)

---

### Задание 5*

Выведите Email каждого покупателя, разделив значение Email на две отдельных колонки: в первой колонке должно быть значение, указанное до @, во второй — значение, указанное после @.


# Решение.

`SELECT LEFT(email, POSITION('@' IN email)), RIGHT(email, POSITION('@' IN email)) FROM customer; `


![5](https://github.com/smabramov/SQL1/blob/c8823f316307b817e80422a5ed3b4d89e36eba50/jpg/5.jpg)


---

### Задание 6*

Доработайте запрос из предыдущего задания, скорректируйте значения в новых колонках: первая буква должна быть заглавной, остальные — строчными.


# Решение.

Не могу понять , как сделать первую букву заглавной, получется все строчными сделать. На зачет не влияет, но очень интересно как. Покажите пожалуйста.


`SELECT LEFT(LOWER(email), POSITION('@' IN email)), RIGHT(email, POSITION('@' IN email)) FROM customer;`

![6](https://github.com/smabramov/SQL1/blob/bd743333bfc6acc43b8a15392175bcfa9c0f1647/jpg/6.jpg)
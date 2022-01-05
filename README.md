# postgreSQL_odev1
PostgreSQL - İlk ödev - Ilgar Babashli

# _Q1_ 
film tablosunda bulunan title ve description sütunlarındaki verileri sıralayınız.
# _Ans_
SELECT title, description FROM film;

# _Q2_ 
film tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük VE 75 ten küçük olma koşullarıyla sıralayınız.
# _Ans_
SELECT * FROM film
WHERE length > 60 AND length < 75;

# _Q3_ 
film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 VE replacement_cost 12.99 VEYA 28.99 olma koşullarıyla sıralayınız.
# _Ans_
Eğer rental_rate = 0.99 olmasını istiyor ve replacement_cost 12.99 veya 28.99 olması fark etmiyorsa:
SELECT * FROM film
WHERE rental_rate = 0.99 AND (replacement_cost = 12.99 OR replacement_cost = 28.99);

Eğer rental_rate = 0.99 ve replacement_cost = 12.99 olanları veya tüm replacement_cost = 28.99 olanları görmek istiyorsak:

SELECT * FROM film
WHERE rental_rate = 0.99 AND replacement_cost = 12.99 OR replacement_cost = 28.99;

# _Q4_ 
customer tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir?
# _Ans_
SELECT last_name FROM customer
WHERE first_name = 'Mary';

Çıktı: Smith

# _Q5_ 
film tablosundaki uzunluğu(length) 50 ten büyük OLMAYIP aynı zamanda rental_rate değeri 2.99 veya 4.99 OLMAYAN verileri sıralayınız.
# _Ans_
SELECT * from film
WHERE NOT length > 50 AND NOT (rental_rate = 4.99 OR rental_rate = 2.99);

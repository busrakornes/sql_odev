
# SQL Eğitim Patika

## ÖDEV 1 

1- **film** tablosunda bulunan __title__ ve **description** sütunlarındaki verileri sıralayınız.

```
SELECT title,description FROM film;
```



2-**film** tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük __VE__ 75 ten küçük olma koşullarıyla sıralayınız.

SELECT * FROM film
WHERE length >60 AND length <70 ;


3-film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 VE replacement_cost 12.99 VEYA 28.99 olma koşullarıyla sıralayınız.


4-customer tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir?


5-film tablosundaki uzunluğu(length) 50 ten büyük OLMAYIP aynı zamanda rental_rate değeri 2.99 veya 4.99 OLMAYAN verileri sıralayınız.


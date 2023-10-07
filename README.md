
# SQL Eğitim Patika


##### ÖDEV 1 [Bağlantı](https://github.com/busrakornes/sql_odev/blob/main/README.md#%C3%B6dev-1)
##### ÖDEV 2 [Bağlantı](https://github.com/busrakornes/sql_odev/blob/main/README.md#%C3%B6dev-2)
##### ÖDEV 3 [Bağlantı](https://github.com/busrakornes/sql_odev/blob/main/README.md#%C3%B6dev-3)




## ÖDEV 1 

1-) **film** tablosunda bulunan __title__ ve **description** sütunlarındaki verileri sıralayınız.

```

SELECT title,description FROM film;

```



2-) **film** tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük __VE__ 75 ten küçük olma koşullarıyla sıralayınız.

```

SELECT * FROM film
WHERE length >60 AND length <70 ;

```



3-) **film** tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 __VE__ replacement_cost 12.99 __VEYA__ 28.99 olma koşullarıyla sıralayınız.

```

SELECT * FROM film
WHERE rental_rate = 0.99 AND replacement_cost = 12.99 OR replacement_cost = 28.99;

```



4-) __customer__ tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir?

```

SELECT last_name FROM customer
WHERE first_name='Mary';

```



5-) **film** tablosundaki uzunluğu(length) 50 ten büyük OLMAYIP aynı zamanda rental_rate değeri 2.99 veya 4.99 OLMAYAN verileri sıralayınız.

```

Select * from film
Where length <50 AND (rental_rate != 2.99 AND rental_rate != 4.99);

```



## ÖDEV 2 

1-) __film__ tablosunda bulunan tüm sütunlardaki verileri replacement cost değeri 12.99 dan büyük eşit ve 16.99 küçük olma koşuluyla sıralayınız ( BETWEEN - AND yapısını kullanınız.)

```    

SELECT * FROM film
WHERE replacement_cost BETWEEN 12.99 AND 16.99;

```



2-) **actor** tablosunda bulunan first_name ve last_name sütunlardaki verileri first_name 'Penelope' veya 'Nick' veya 'Ed' değerleri olması koşuluyla sıralayınız. ( IN operatörünü kullanınız.)

```

SELECT first_name,last_name FROM actor
WHERE first_name IN('Penelope','Nick','Ed');

```



3-) **film** tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99, 2.99, 4.99 __VE__ replacement_cost 12.99, 15.99, 28.99 olma koşullarıyla sıralayınız. ( IN operatörünü kullanınız.)

```

SELECT * FROM film
WHERE rental_rate IN (0.99,2.99,4.99) AND replacement_cost IN (12.99,15.99,28.99);

```



## ÖDEV 3

1-) **country** tablosunda bulunan **country** sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralayınız.

```

SELECT * FROM country
WHERE country LIKE 'A%a';

```



2-) **country** tablosunda bulunan __country__ sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız.

```

SELECT * FROM country
WHERE country LIKE '_____n';

```

3-) **film** tablosunda bulunan __title__ sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin 'T' karakteri içeren film isimlerini sıralayınız.

```

SELECT * FROM film
WHERE title ~~* '%T%t%t%t%';

```



4-) **film** tablosunda bulunan tüm sütunlardaki verilerden **title** 'C' karakteri ile başlayan ve uzunluğu (length) 90 dan büyük olan ve rental_rate 2.99 olan verileri sıralayınız.

```

SELECT * FROM film
WHERE title ~~* 'c%' AND length >90 AND rental_rate=2.99;

```



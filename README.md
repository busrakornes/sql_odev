
# SQL Eğitim Patika


##### ÖDEV 1 [Bağlantı](https://github.com/busrakornes/sql_odev/blob/main/README.md#%C3%B6dev-1)
##### ÖDEV 2 [Bağlantı](https://github.com/busrakornes/sql_odev/blob/main/README.md#%C3%B6dev-2)
##### ÖDEV 3 [Bağlantı](https://github.com/busrakornes/sql_odev/blob/main/README.md#%C3%B6dev-3)
##### ÖDEV 4 [Bağlantı](https://github.com/busrakornes/sql_odev/blob/main/README.md#%C3%B6dev-4)
##### ÖDEV 5 [Bağlantı](https://github.com/busrakornes/sql_odev/blob/main/README.md#%C3%B6dev-5)
##### ÖDEV 6 [Bağlantı](https://github.com/busrakornes/sql_odev/blob/main/README.md#%C3%B6dev-6)
##### ÖDEV 7 [Bağlantı](https://github.com/busrakornes/sql_odev/blob/main/README.md#%C3%B6dev-7)
##### ÖDEV 8 [Bağlantı](https://github.com/busrakornes/sql_odev/blob/main/README.md#%C3%B6dev-8)




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




## ÖDEV 4

1-) **film** tablosunda bulunan **replacement_cost** sütununda bulunan birbirinden farklı değerleri sıralayınız.

```

SELECT DISTINCT replacement_cost FROM film;

```



2-) **film** tablosunda bulunan __replacement_cost__ sütununda birbirinden farklı kaç tane veri vardır?

```

SELECT COUNT(DISTINCT replacement_cost) FROM film;

```



3-) **film** tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir?

```

SELECT COUNT(*) FROM film
WHERE title LIKE 'T%' AND rating='G';

```



4-) **country** tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır?

```

SELECT COUNT(*) FROM country
WHERE country LIKE '_____';

```



5-) **city** tablosundaki şehir isimlerinin kaç tanesi 'R' veya r karakteri ile biter?

```

SELECT COUNT(*) FROM city
WHERE city ILIKE '%R';

```




## ÖDEV 5

1-) **film** tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız.

```

SELECT * FROM film
WHERE title ILIKE '%n'
ORDER BY length DESC
LIMIT 5;

```



2-) **film** tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) ikinci(6,7,8,9,10) 5 filmi(6,7,8,9,10) sıralayınız.

```

SELECT * FROM film
WHERE title LIKE '%n'
ORDER BY length 
OFFSET 5
LIMIT 5;

```



3-) **customer** tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız.

```

SELECT last_name,store_id FROM customer
WHERE store_id=1
ORDER BY last_name DESC
LIMIT 4;

```




## ÖDEV 6

1-) **film** tablosunda bulunan **rental_rate** sütunundaki değerlerin ortalaması nedir?

```

SELECT AVG(rental_rate) FROM film;

```



2-) **film** tablosunda bulunan filmlerden kaç tanesi 'C' karakteri ile başlar?

```

SELECT COUNT(*) FROM film
WHERE title LIKE 'C%';

```




3-) **film**  tablosunda bulunan filmlerden rental_rate değeri 0.99 a eşit olan en uzun (length) film kaç dakikadır?

```

SELECT MAX(length) FROM film
WHERE rental_rate=0.99;

```



4-) **film** tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı replacement_cost değeri vardır?

```

SELECT COUNT(DISTINCT(replacement_cost)) FROM film
WHERE length>150;

```





## ÖDEV 7

1-) **film** tablosunda bulunan filmleri rating değerlerine göre gruplayınız.

```

SELECT rating FROM film
GROUP BY rating;

```



2-) **film** tablosunda bulunan filmleri **replacement_cost** sütununa göre grupladığımızda film sayısı 50 den fazla olan replacement_cost değerini ve karşılık gelen film sayısını sıralayınız.

```

 SELECT replacement_cost,COUNT(*) FROM film
 GROUP BY replacement_cost
 HAVING COUNT(*)>50;

```



3-) **customer** tablosunda bulunan store_id değerlerine karşılık gelen müşteri sayılarını nelerdir?

```

 SELECT store_id,COUNT(*) FROM customer
 GROUP BY store_id;

```



4-) **city** tablosunda bulunan şehir verilerini **country_id** sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıran country_id bilgisini ve şehir sayısını paylaşınız.

```

 SELECT country_id,COUNT(*) FROM city
 GROUP BY country_id
 ORDER BY COUNT(city) DESC
 LIMIT 1;

```





## ÖDEV 8 

1-) **test** veritabanınızda **employee** isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım.

```

CREATE TABLE employee ( 
    id INTEGER, 
    name VARCHAR(50) NOT NULL , 
	birthday DATE,
	email VARCHAR(100)
);

```



2-)Oluşturduğumuz **employee** tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim.

```

insert into employee (id, name, email, birthday) values (1, 'Theressa Mathis', 'tmathis0@histats.com', null);
insert into employee (id, name, email, birthday) values (2, 'Nannie Matteo', null, '2/19/1914');
insert into employee (id, name, email, birthday) values (3, 'Sherman Boreland', 'sboreland2@t-online.de', null);
insert into employee (id, name, email, birthday) values (4, 'Ignaz Whitchurch', 'iwhitchurch3@msu.edu', '5/21/1931');
insert into employee (id, name, email, birthday) values (5, 'Maryl Bartusek', 'mbartusek4@vkontakte.ru', null);
insert into employee (id, name, email, birthday) values (6, 'Bradan Corness', 'bcorness5@vinaora.com', null);
insert into employee (id, name, email, birthday) values (7, 'Aldrich Pethick', 'apethick6@godaddy.com', '11/28/1925');
insert into employee (id, name, email, birthday) values (8, 'Alix Crowdson', 'acrowdson7@prweb.com', null);
insert into employee (id, name, email, birthday) values (9, 'Nelson Boller', 'nboller8@bbb.org', '3/6/1994');
insert into employee (id, name, email, birthday) values (10, 'Fletcher Deyes', 'fdeyes9@mysql.com', '10/23/1913');
insert into employee (id, name, email, birthday) values (11, 'Hedwig Carlsson', 'hcarlssona@surveymonkey.com', null);
insert into employee (id, name, email, birthday) values (12, 'Phelia Hunt', 'phuntb@altervista.org', null);
insert into employee (id, name, email, birthday) values (13, 'Sidnee Bowfin', 'sbowfinc@marketwatch.com', '10/31/1957');
insert into employee (id, name, email, birthday) values (14, 'Elspeth Goricke', 'egoricked@army.mil', '1/10/1939');
insert into employee (id, name, email, birthday) values (15, 'Forrest Pumfrey', 'fpumfreye@devhub.com', '10/15/1960');
insert into employee (id, name, email, birthday) values (16, 'Kent Trusslove', 'ktrusslovef@blinklist.com', '6/6/1942');
insert into employee (id, name, email, birthday) values (17, 'Hillyer Dunmuir', 'hdunmuirg@devhub.com', '9/9/1996');
insert into employee (id, name, email, birthday) values (18, 'Matt Bolgar', 'mbolgarh@github.com', '4/10/1996');
insert into employee (id, name, email, birthday) values (19, 'Mohammed Kobiera', 'mkobierai@ameblo.jp', '11/12/1906');
insert into employee (id, name, email, birthday) values (20, 'Jada Broscombe', null, '7/26/1923');
insert into employee (id, name, email, birthday) values (21, 'Der Lye', 'dlyek@icio.us', '7/2/1990');
insert into employee (id, name, email, birthday) values (22, 'Adiana Pointer', 'apointerl@360.cn', '11/8/1980');
insert into employee (id, name, email, birthday) values (23, 'Catherina Shambroke', 'cshambrokem@springer.com', '12/27/1955');
insert into employee (id, name, email, birthday) values (24, 'Verina Jozefczak', 'vjozefczakn@yellowpages.com', '3/26/1921');
insert into employee (id, name, email, birthday) values (25, 'Ed O''Mara', null, null);
insert into employee (id, name, email, birthday) values (26, 'Clemence Pavkovic', 'cpavkovicp@diigo.com', '9/13/2018');
insert into employee (id, name, email, birthday) values (27, 'Anastasie Chyuerton', 'achyuertonq@newsvine.com', '8/19/1909');
insert into employee (id, name, email, birthday) values (28, 'Malory Peaddie', 'mpeaddier@usda.gov', null);
insert into employee (id, name, email, birthday) values (29, 'Burch Nealon', 'bnealons@joomla.org', '11/3/1941');
insert into employee (id, name, email, birthday) values (30, 'Massimo Wewell', 'mwewellt@networkadvertising.org', '9/11/1908');
insert into employee (id, name, email, birthday) values (31, 'Elga Eslemont', 'eeslemontu@miitbeian.gov.cn', null);
insert into employee (id, name, email, birthday) values (32, 'Guillermo Pallaske', 'gpallaskev@tiny.cc', null);
insert into employee (id, name, email, birthday) values (33, 'Sheffy Kelinge', 'skelingew@timesonline.co.uk', '8/6/2015');
insert into employee (id, name, email, birthday) values (34, 'Flori Lewcock', 'flewcockx@mapy.cz', null);
insert into employee (id, name, email, birthday) values (35, 'Derril Ringsell', null, '5/30/1914');
insert into employee (id, name, email, birthday) values (36, 'Galen Neame', 'gneamez@chronoengine.com', null);
insert into employee (id, name, email, birthday) values (37, 'Leela Midden', 'lmidden10@skyrock.com', '4/8/2015');
insert into employee (id, name, email, birthday) values (38, 'Minnnie Grinnov', 'mgrinnov11@amazon.de', null);
insert into employee (id, name, email, birthday) values (39, 'Ernest Jagoe', 'ejagoe12@etsy.com', null);
insert into employee (id, name, email, birthday) values (40, 'Simone Shields', 'sshields13@bravesites.com', '4/30/1973');
insert into employee (id, name, email, birthday) values (41, 'Skip Hugin', null, '9/6/2004');
insert into employee (id, name, email, birthday) values (42, 'Loella Pohlke', 'lpohlke15@ehow.com', '2/21/2014');
insert into employee (id, name, email, birthday) values (43, 'Ali Heynen', null, '5/28/1940');
insert into employee (id, name, email, birthday) values (44, 'Shep Flinn', 'sflinn17@posterous.com', '2/6/2003');
insert into employee (id, name, email, birthday) values (45, 'Dorine Ivanitsa', 'divanitsa18@hao123.com', '10/21/2008');
insert into employee (id, name, email, birthday) values (46, 'Caria Cattanach', 'ccattanach19@chicagotribune.com', '4/14/1988');
insert into employee (id, name, email, birthday) values (47, 'Ilene Cray', 'icray1a@miibeian.gov.cn', '4/11/1954');
insert into employee (id, name, email, birthday) values (48, 'Melosa Londesborough', 'mlondesborough1b@wufoo.com', null);
insert into employee (id, name, email, birthday) values (49, 'Perry Pretty', 'ppretty1c@constantcontact.com', null);
insert into employee (id, name, email, birthday) values (50, 'Alvina Pashley', 'apashley1d@scientificamerican.com', '3/19/1906');

```



3-) Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım.

```

UPDATE employee       
SET name='Busra Kornes',
	email='busra@kornes.com',
	birthday='2000-07-29'      
WHERE id=10;

```
```

UPDATE employee       
SET birthday='2000-07-29'      
WHERE email='sboreland2@t-online.de';

```
```

UPDATE employee       
SET email='theressa@Mathis.com'      
WHERE id=1;

```
```

UPDATE employee       
SET email='dorine@dorine.com',
    birthday='2000-04-10'
WHERE id=45;

```

```

UPDATE employee       
SET birthday='2001-01-10'
WHERE name='Matt Bolgar';

```


4-)Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım.

```

DELETE FROM employee 
WHERE id=6
RETURNING *;
 
```

```

 DELETE FROM employee
WHERE name ='Alix Crowdson'
RETURNING *;

```

```

DELETE FROM employee
WHERE name = 'Phelia Hunt' AND email = 'phuntb@altervista.org';

```

```

DELETE FROM employee
WHERE email = 'flewcockx@mapy.cz';

```

```

DELETE FROM employee
WHERE id >45
RETURNING *;

```



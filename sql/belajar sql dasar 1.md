---
tags:
  - codding
  - programming
  - sql
  - database
author: aji
created: 19/08/26 23:08
---

## dbms
>-  dbms database management systems
	- aplikasi yang digunakkan untuk memanage data
	- dbms gampangnya adalah seperti shell linux yakni aplikasi yang menerjemahkan ketikan user menjadi perintah yang akan dieksekusi oleh komputer 
---
### relational database
- database yang memiliki relasi antar tabel sama seperti excel

---
### perlunya belajar sql
- digunakkan dan juga populer dikalangan web dev

---
### playground
#### sintaks

```sql
select * from belajar [ambil semua data dari tabel belajar];
show databases [tampilkan semua database];
create database name;

```
---
## tipe data
   - tiap tipe data terdapat di kolom yang ada type datanya
    # type data number/integer
     -  angka, double dan floating point
     - unsigned tidak menerima bilangan negative
     - decimal
     - number atribute
     - char dan varchar
     - penyimpanan pada char akan tetap sama misal char(4) dia akan disimpan jadi 4 byte
     - kalau varchar dia menyesuaikan karakter bisa besar dan kecil 
 ### enum
	 - enum adalah tipe data pilihan 
	 - misal enum(pria,wanita)
### tipe data date dan time
 -untuk mengetahui date (informasi yang disimpan adalah ) adalah dan time

| jenis data date dan time | format             | contoh              |
| ------------------------ | ------------------ | ------------------- |
| DATE                     | YYY-MM-DD          | 20-10-10            |
| DATETIME                 | YYY-MM-DD HH:MM:SS | 2020-10-10 10:10:10 |
| TIMESTAMP                | YYY-MM-DD HH:MM:SS | 2020-10-10 10:10:10 |
| TIME                     | HH:MM:SS           | 10:10:10            |
| YEAR                     | YYYY               | 2020                |
> KAPAN PAKE TIMESTAMP DAN DATE TIME 
>  TIMESTAMP UNTUK TAMBAHAN SEPERTI UPDATED AT DELETED AT

| TYPE DATA | penjelasan                |
| --------- | ------------------------- |
| boolean   | type data true atau false |
|           |                           |
|           |                           |
## tabel
- data disimpan di tabel
- tiap tabel biasanya menyimpan 1 jenis data
### storage engine
- berfungsi sebagai cara pengolahan data

| syntaks                               | penjelasan                                                                              |
| ------------------------------------- | --------------------------------------------------------------------------------------- |
| add column                            | tambah column                                                                           |
| drop column                           | hapus column                                                                            |
| rename colum nama to nama_baru        | ubah nama table                                                                         |
| modify nama varcgar(100) after jumlah | rubah tipe data column lalu after letakkan posisi column setelah jumlah atau table ke x |
| modify nama varchar(100) first        | sama aja tapi pertama                                                                   |
|                                       |                                                                                         |
### truncate
 - hapus semua data di table lalu id direset jadi 0
### drop table barang 
 - hapus semua table id tidak direset ke 0
### insert data
 - insert data insert into table insert into table (col1,col2) values (val1,val2);
### select 
 - untuk mengambil data di dalam table
 

| sintaks                 | keterangan                       |
| ----------------------- | -------------------------------- |
| *                       | semua data di table x            |
| select a,b,x from table | ambil beberapa column di table x |

### primary key 
- apa itu primary key
- table unique dan juga representasi dari id
- secara simple seperti ktp
### where clause
-  untuk memfilter data berdasar kriteria tertentu
- bisa untuk melakukan operator mtk lainnya

| operator   | keterangan                   |
| ---------- | ---------------------------- |
| =          | sama dengan                  |
| <> atau != | tidak sama dengan            |
| <          | kurang dari                  |
| <=         | kurang dari atau sama dengan |
| >          | lebih dari                   |
| >=         | lebih dari atau sama dengan  |

```sql
select * from products where quantity=100;
```
### update data
- update data dengan menggabungkan where clause
```sql 
update products set category="makanan" where id="p001";
update table set col=new val where id in (1,2,3) -- multiple data update
```
### delete data
- untuk delete data berdasarkan where clause
``` sql
delete from table where id=?;
```
### alias 
- untuk memberi alias pada colom maupun table
```sql 
select col1 as "data1" from table ; -- alias di colom 
select p.id,p.description from product as p -- alias di table
```
### and or operator 
- digunakkan untuk memfilter data
- dan juga untuk mengambil beberapa data
- untuk memproses data
### like operator
- digunakkan untuk cari data didalam table
- lambat karena memaksa sql melakukan full table scan , 
- sql terpakasa melakukan pencarian data satu persatu dari awal hingga bertemu data yang dicari oleh like operator

| like operator | hasil                  |
| ------------- | ---------------------- |
| like "b%"     | string dengan awalan b |
| like "%a"     | -\|\|- akhiran a       |
| like "%eko%"  | string berisi eko      |
| not like      | tidak like             |
```sql
select * from products where name like "%mie%"
```
### null operator

| simbol       | artinya                |
| ------------ | ---------------------- |
| is null      | ambil data yang null   |
| is not nulll | -\|\|- yang bukan null |
## between operator
- untuk menyederhanakan operator
```sql
select * from products where price between 10000 and 20000 
```

| sign        | mean               |
| ----------- | ------------------ |
| between     | diantara           |
| not between | tidak ada diantara |

### in operator
- mencari kolom dengan beberapa nilai 
- menggantikan or operator
```sql
select * from products where category in ("makanan","minuman")
```
### order by
- mengurutkan data berdasarkan colom
```sql
select id,category,price,name from products order by category asc,price desc;
```
### limit clause
- digunakkan untuk limit ,ada berapa data yang akan ditampilkan
- handle paging 
```sql
-- paginations
select * from products
where price>0
order by id 
limit 10,5 -- angka terakhir adalah limit dan yang pertama adalah skipnya
```
### select distinct
 - menghilangkan data duplicate
 ```sql
 select distinct category from products;
 ```
 ### numeric function 
 - untuk manipulasi data number
 ```sql
 select id,name,price div 1000 as "price in k" from products -- price in k
 ```


| name   | description                 |
| ------ | --------------------------- |
| %,mod  | sisa bagi                   |
| *      | kali                        |
| +      | tambah                      |
| -      | kurang                      |
| -/\d+/ | inverse negative or positif |
| /      | division operator           |
| div    | integer division            |
### matematical function
https://dev.mysql.com/doc/refman/8.0/en/mathematical-functions.html
https://docs.google.com/presentation/d/1v4HllRI-BNj4EdJFLh4_jISq_dcosHoAVo5-LME-ghY/edit?slide=id.gb0610ef87c_0_24#slide=id.gb0610ef87c_0_24

### auto increment
- data akan menambah dan jika dihapus maka akan diteruskan dari yang terakhir dihapus
```sql
select last_insert_id() -- untuk melihat inserted id yang terakhir
```
### string functions
- https://dev.mysql.com/doc/refman/8.0/en/string-functions.html
### year 
```sql
select id,created_at,
  year(created_at) as year,
  month(created_at) as month
from products;
```
### control flow
```sql
select id ,category, case category
      when 'makanan' then 'enak'
      when 'minuman' then 'segar'
      else 'apa itu?'
      end as 'kategory' from products;

select id,price,
  if(
    price <= 15000,'murah',
    if(price<=20000,'mahal','mahal banget')
  ) as "mahal?" 
  from products;

select id,name,ifnull(description ,'kosong') from products
```
### agregate functions
- melihat data paling mahal ditabel
- menghitung banyak baris data sekaligus dan menghasilkan 1 nilai ringkasan 
- untuk mem print agregate dengan colom table biasa maka gunakkan group by 
```sql
  select name,min(price) as harga_terendah from 
  products group by name order by 
  harga_terendah
```
### having clause
- untuk memfilter agregate functions
```sql 
  -- having clause
  -- untuk memfilter agregate functions
  select category,count(id) as total from products 
  group by category having total>3
```
### constraint
- untuk menjaga dan validasi di table kita
- -  unique constrain tidak menerima data duplikat jika sudah ada data di table maka akan error
-  -  check constraint untuk mengececk value sebelum data di insert ke table
- check constraint support di mysql **versi 8.0.16**.
### index
- mysql menyimpan datanya dalam disk
- menyebabkan mencari data jadi lambat
- karena full scan table/melakukan pencarian dari baris pertama sampai terakhir
- dalam index structure akan menyimpan data dalam struktur b-tree
- mempermudah kita saat melakukan pencarian dan pengurutan data
- ### cara kerja
	- mempercepat pencarian data 
	- tanpa index maka mysql akan melakukan full table scan sehingga proses pencarian data sangat lambat
	- (col 1,col2,col3)
	- ### efek samping
		-memperlambat manipulasi data tapi proses query cepet
	- tidak perlu index saat membuat primary key dan unique constraint
```sql
CREATE TABLE `sellers` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `name` varchar(100) NOT NULL,
  `name2` varchar(100) DEFAULT NULL,
  `name3` varchar(100) DEFAULT NULL,
  `email` varchar(100) NOT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `email_unique` (`email`),
  KEY `name_1_name2_name3` (`name`,`name2`,`name3`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1
```
### full text search
- mencari sebagian kata di colom dengan type data string 
- dan pencarian kata tidak hanya =(equals,sama dengan)
```sql
CREATE TABLE `products` (
  `id` varchar(10) NOT NULL,
  `name` varchar(100) NOT NULL,
  `category` enum('makanan','minuman','lain-lain') DEFAULT NULL,
  `description` text,
  `price` int(10) unsigned NOT NULL,
  `quantity` int(10) unsigned NOT NULL DEFAULT '0',
  `created_at` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`),
  FULLTEXT KEY `product_search` (`name`,`description`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1
```
---
mode full text search

| mode full text search | keterangan                      |
| --------------------- | ------------------------------- |
| natural language      |                                 |
| boolean               | -/tidak ada patern +/ada patern |

### gunakkan mode full text search dibandingkan dengan like query
```sql
 select * from products where match(name,description) 
                against('ayam' in natural language MODE)

  select * from products where match(name,description) 
                against('+ayam -bakso' in boolean MODE) --  ada ayam tapi bakso tidak ada
  
  select * from products where match(name,description) 
                against('ayam' with query expansion)
```
---
```sql
CREATE TABLE `products` (
  `id` varchar(10) NOT NULL,
  `name` varchar(100) NOT NULL,
  `description` text,
  `price` int unsigned NOT NULL,
  `quantity` int unsigned NOT NULL DEFAULT '0',
  `created_at` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP,
  `id_category` varchar(10) DEFAULT NULL,
  PRIMARY KEY (`id`),
  FULLTEXT KEY `product_search` (`name`,`description`),
  CONSTRAINT `price_check` CHECK ((`price` >= 1000))
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci
```
---
## studi kasus control flow comon and control flow+ full text search
```sql 
select name ,case 
              when name like '%bakso%' and name like '%ayam%' then 'ada ayam dan baksonya'
              when name like '%ayam%' then 'ada daging ayamnya'
              when name like '%bakso%' then 'ada baksonya'
              when name like '%es krim%' then 'es krim!!'
              when name like '%keripik%' or name like 'kerupuk' then 'keripik atau kerupuk'
              else 'pasti minuman' 
              end as komentar 
  from products;
```
---

	| name               || komentar              |				
	| mi ayam original   || ada daging ayamnya    |
	| mi ayam bakso tahu || ada ayam dan baksonya |
	| mi ayam ceker      || ada daging ayamnya    |
	| mi ayam spesial    || ada daging ayamnya    |
	| mi ayam yamin      || ada daging ayamnya    |
	| bakso rusuk        || ada baksonya          |
	| es jeruk           || pasti minuman         |
	| es campur          || pasti minuman         |
	| es teh manis       || pasti minuman         |
	| kerupuk            || keripik atau kerupuk  |
	| keripik udang      || keripik atau kerupuk  |
	| es krim            || es krim!!             |
	| mi ayam jamur      || ada daging ayamnya    |
	| bakso telur        || ada baksonya          |
	| bakso jando        || ada baksonya          |
	| mi ayam ceker      || ada daging ayamnya    |
	| ------------------ || ------------------ |				


---
### in boolean mode + mean logic and must containt '+ayam +keripik' (must containt keripik and ayam ) 'ayam aki' ayam or aki
#### full text search
```sql 
select name ,case 
  when match(name,description) 
  against('+ayam' '+bakso' in boolean mode) 
          then 'ada daging ayamnya dan bakso' 
  when match(name,description)
  against('+ayam') then 'ada daging ayamnya'
  when match(name,description)
    against("+bakso" in boolean mode) then 'pasti bakso'
  when match(name,description)
    against("keripik kerupuk" in boolean mode) then 'keripik atau kerupuk'
  when match(name,description)
    against("es krim" in boolean mode) then 'es krim!!'
  else "bukan makanan dan pasti minuman"
  end as komentar 
  from products
```
## result 

| name               | komentar                        |
| ------------------ | ------------------------------- |
| mi ayam original   | ada daging ayamnya              |
| mi ayam bakso tahu | ada daging ayamnya dan bakso    |
| mi ayam ceker      | ada daging ayamnya              |
| mi ayam spesial    | ada daging ayamnya              |
| mi ayam yamin      | ada daging ayamnya              |
| bakso rusuk        | pasti bakso                     |
| es jeruk           | bukan makanan dan pasti minuman |
| es campur          | bukan makanan dan pasti minuman |
| es teh manis       | bukan makanan dan pasti minuman |
| kerupuk            | keripik atau kerupuk            |
| keripik udang      | keripik atau kerupuk            |
| es krim            | es krim!!                       |
| mi ayam jamur      | ada daging ayamnya              |
| bakso telur        | pasti bakso                     |
| bakso jando        | pasti bakso                     |
| mi ayam ceker      | ada daging ayamnya              |

---
### table relationship
- table selalu berelasi guna mempermudah kita sebagai developer 
- dan ada foregn key untuk mengatur referensi ke table yang akan dihubungkan
- tabel yang berelasi saling membutuhkan data satu sama lain
### foreign key
- untuk referensi ke table lainnya
- contoh id_product di table penjualan adalah referensi ke table product
- memastikan data ada di table referencenya
- delete akan ditolak jika masih digunakkan di table lain jika pakai restrict
- jika cascade maka data ikut terhapus jika di table referensinya dihapus
### behavor foreign key

| behavior  | on delete              | on update             |
| --------- | ---------------------- | --------------------- |
| restrict  | ditolak                | ditolak               |
| cascade   | data akan ikut dihapus | data akan ikut diubah |
| no action | data dibiarkan         | data dibiarkan        |
| set null  | data jadi null         | data jadi null        |

## before
```sql
CREATE TABLE `whistlist` (
  `id` int NOT NULL AUTO_INCREMENT,
  `id_product` varchar(10) NOT NULL,
  `description` text,
  PRIMARY KEY (`id`),
  KEY `fk_whistlist_product` (`id_product`),
  CONSTRAINT `fk_whistlist_product` FOREIGN KEY (`id_product`) REFERENCES `products` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci
```
---
## after

```sql 
CREATE TABLE `whistlist` (
  `id` int NOT NULL AUTO_INCREMENT,
  `id_product` varchar(10) NOT NULL,
  `description` text,
  PRIMARY KEY (`id`),
  KEY `fk_whistlist_product` (`id_product`),
  CONSTRAINT `fk_whistlist_product` FOREIGN KEY (`id_product`) REFERENCES `products` (`id`) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=3 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci
```
## join
- untuk menggabungkan beberapa table dan terkait dengan foreign key yang memiliki reference ke table lain
- semakin banyak join maka makin berat querynya
- tidak harus ada foreign key
---
### jenis jenis relasi

## one to one
- tiap data hanya boleh berelasi ke 1 data di tabel lainnya
- contohnya seperti e-walet 1 customer dibolehkan hanya 1 wallet 1 walet dimiliki customer
- set kolom dengan unique key agar tidak terjadi duplikat data
- atau table di primary key sama dengan antara table customer dengan wallet customer.id =wallet.id
## one to many
- relasi antar table dimana 1 table bisa memiliki banyak data di table x dan banyak data di table x dimiliki oleh 1 data ditable y
- misal 1 user punya banyak post dan banyak post dimiliki oleh 1 user


| jenis relasi | arti                                                      | contoh                                                         |
| ------------ | --------------------------------------------------------- | -------------------------------------------------------------- |
| one to one   | tiap data dari 1 table hanya berelasi ke 1 table lainnya  | user have only 1 wallet 1 wallet is belongs to user            |
| one to many  | 1 table punya banyak data di table x                      | 1 user have many post many post belongs to 1 user              |
| many to many | banyak table punya banyak tabel di table x dan sebaliknya | many user can follow user and user can follow more than 2 user |

---
### contoh one to many relationship product can have more than 1 category many category belongs to product
---
```sql
 alter table products
    add constraint fk_product 
      foreign key(id_category) references categories(id)

-- result
CREATE TABLE `products` (
  `id` varchar(10) NOT NULL,
  `name` varchar(100) NOT NULL,
  `description` text,
  `price` int unsigned NOT NULL,
  `quantity` int unsigned NOT NULL DEFAULT '0',
  `created_at` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP,
  `id_category` varchar(10) DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `fk_product` (`id_category`),
  FULLTEXT KEY `product_search` (`name`,`description`),
  CONSTRAINT `fk_product` FOREIGN KEY (`id_category`) REFERENCES `categories` (`id`),
  CONSTRAINT `price_check` CHECK ((`price` >= 1000))
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci
```
---
### many to many relationship
- 1 order bisa dimiliki oleh banyak order detail 
- 1 product bisa dimiliki oleh banyak order detail
- many to many adalah gabungan 2 buah 1 to many
### composite key 
- bisa mencegah data terambil 1 kali dan menjaga agar data tetap unik
- misal 1 mahasiswa bisa ambil mata kuliah x tapi tidak bisa ambil 2 kali atau lebih 

| product 1    | order detail n                                                              | order 1             |
| ------------ | --------------------------------------------------------------------------- | ------------------- |
| id varchar   | id_product                                                                  | id int              |
| name varchar | id_order                                                                    | total int           |
| price int    | quantity                                                                    | order date datetime |
| quantity     | price (untuk mencegah update data price aka save price saat product dibeli) |                     |
```sql

create table orders_detail(
  id_product varchar(10) not null,
  id_order int not null,
  price int not null,
  quantity int not null,
  primary key(id_product,id_order)
)engine=innoDB


  alter table orders_detail
  add constraint fk_orders_detail_product
  foreign key(id_product) references products(id)

  alter table orders_detail
  add constraint fk_orders_detail_orders
  foreign key(id_order) references orders(id)
  -- results
CREATE TABLE `orders_detail` (
  `id_product` varchar(10) NOT NULL,
  `id_order` int NOT NULL,
  `price` int NOT NULL,
  `quantity` int NOT NULL,
  PRIMARY KEY (`id_product`,`id_order`),
  KEY `fk_orders_detail_orders` (`id_order`),
  CONSTRAINT `fk_orders_detail_orders` FOREIGN KEY (`id_order`) REFERENCES `orders` (`id`),
  CONSTRAINT `fk_orders_detail_product` FOREIGN KEY (`id_product`) REFERENCES `products` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci
```
---
### join mysql

| nama       |            | efek                                                                                                                             |
| ---------- | ---------- | -------------------------------------------------------------------------------------------------------------------------------- |
| inner join | by default | data akan ditampilkan khusus yang memiliki relasi                                                                                |
| left       |            | akan menampilkan semua table di kiri dan akan menghasilkan null di tabel kanan jika table kanan tidak punya relasi di table kiri |
| right join |            | mirip left join tapi ditable kanan akan ditampilkan semuanya                                                                     |
![696](https://dqlab.id/files/dqlab/file/data-web-1/data-user-5/postgroup/0f0327126cebe99dff31890ba2cd7777/41839aad6ea02bb0d763bef591035c1d.png)
![476](https://1.bp.blogspot.com/-xBmbZYvwan8/WlfgrC7nfUI/AAAAAAAABKc/ZCpBzJl07AsleVr9LvCwG-YNIiGQ3lr5ACLcBGAs/s1600/join-sql.jpg)

---
### set operator

| nama         | keterangan                                                                                                                                           |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| union        | operasi menggabungkan2 buah select query dan data duplikat dihapus mirip seperti new set di js namun lambat karena harus mengeliminasi data duplikat |
| union all    | menggabungkan 2 select atau lebih dan mengeluarkan semua data duplikat apa adanya sehingga performa lebih cepat ketimbang union                      |
| minus/except | query pertama akan dihilangkan oleh query kedua                                                                                                      |
![](https://i.ytimg.com/vi/HH5QEfGTSTQ/hq720.jpg?sqp=-oaymwEhCK4FEIIDSFryq4qpAxMIARUAAAAAGAElAADIQj0AgKJD&rs=AOn4CLDjSIvJrrAnZHeJwRF6_GEjnphXtw)

---

### transactions
- memungkinkan dbms menjalankan beberapa perintah jika gagal maka data akan dirollback
- commit akan dianggap berhasil 
- mencegah race condition 
- mencatat query di ram lalu saat commit maka akan di tulis secara permanen di harddisk
	- query dml insert update delete 

| perintah          | keterangan                                         |
| ----------------- | -------------------------------------------------- |
| start transaction | memulai proses transaksi                           |
| commit            | menyimpan secara permanen seluruh proses transaksi |
| rollback          | membatalkan secara permanen proses transaksi       |
 - tidak bisa menggunakkan ddl(merubah struktur table)
--- 
### masih di menit ke 05:46:00
![](https://www.youtube.com/watch?v=xYBclb-sYQ4&list=PL-CtdCApEFH_P2_2zR6pvDublvpD3fF6W)

---
https://www.geeksforgeeks.org/dbms/database-design-ultimate-guide/
https://dqlab.id/mengenal-left-join-sql-and-implementasi-pada-beberapa-tabel
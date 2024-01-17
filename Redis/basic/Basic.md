## Start Redis

Running redis with default config
```
redis-server
```

Sebaiknya menggunakan configurasi tambahan untuk memulai redis server, lihat configurasinya [disini](https://github.com/redis/redis/blob/7.2/redis.conf). Sesuaikan versi configurasinya pada branchnya, salin semua configurasinya dan buat file dengan .conf lalu kita bisa menambahkan beberapa konfigurasi nantinya disana.

start redis dengan configurasi
```
redis-server <path redis.conf>
```
contoh : 
```
redis-server config/redis.conf
```

Tampilan

<img src="/Redis/asset/basic/view-start.png" style="width:800px;height:400px;">

artinya database redis sudah bisa digunakan. untuk memulai koneksi di lokal buat tab terminal baru untuk melakukan koneksi ke redis.

## Connect Redis

```
redis-cli -h localhost
```
tambahkan `-p <port>` jika port berbeda.

Penamaan database di redis menggunakan angka mulai dari 0, kita bisa mengatur berapa banyak database pada config sebelumnya tambahkan `databases <jumlah database>` di confignya.

contoh :

`databases 20`, yang artinya jumlah seluruh databasenya ada 20.

Gunakan `select <database index>` untuk berpindah dari database satu ke lainnya. Secara default saat connect yang tampil adalah database index 0.

lihat :

![](/Redis/asset/basic/selectdb.png)


## Operasi String

- `set <key> "<value>"`, untuk menetapkan nilai untuk suatu key tertentu.<br/>
Contoh : `set name "Daniel"`

- `get <key>`, mendapatkan value dari key.<br/>
Contoh : `get name`

- `exists <key>`, untuk mengecek apakah key memiliki value.<br/>
Contoh : `exists name`

- `del <key> [key ...]`, menghapus key dari database juga bisa menghapus banyak key secara bersamaan.<br/>
Contoh : `del name` atau `del name1 name2 name3`

- `append <key> "<value>"`, menambahkan value ke key yang sudah ada.<br/>
Contoh : `append name " Jon"`

- `keys <pattern>`, menampilkan semua key yang ada di database, bisa menggunakan wildcard `*` untuk menampilkan semua key.<br/>
Contoh : `keys *`

demo : 

https://github.com/teranixbq/NoteConf/assets/66883583/08fc5c7c-a5ab-4074-aad3-329104ff2bec

## Operasi String Range
- `setrange <key> <offset> "<value>"`, mengganti value dari key pada posisi tertentu.<br/>
Contoh : `setrange name 7 "Jon"`

- `getrange <key> <start> <end>`, mengambil value dari key pada posisi tertentu.<br/>
Contoh : `getrange name 0 8` <br/>

demo : 

![](/Redis/asset/basic/stringrange.gif)

## Operasi Multiple Key

- `mset <key> "<value>" [key ...]`, menetapkan value untuk beberapa key.<br/>
Contoh : `mset name "Daniel" age 20`

- `mget <key> [key ...]`, mendapatkan value dari beberapa key.<br/>
Contoh : `mget name age`

demo : 

![](/Redis/asset/basic/multiplekey.gif)
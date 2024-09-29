# <h1 align="center">Laporan Praktikum Modul Dasar-Dasar Python untuk Sains Data</h1>
<p align="center">Arsita Wiwit Tiyaswening</p>

## Dasar Teori

Python adalah bahasa pemrograman yang berdaya dan mudah dipelajari. Python memiliki struktur data tingkat tinggi yang efisien dan pendekatan yang sederhana namun efektif untuk pemrograman berorientasi objek. Sintaksis Python yang elegan dan tipe dinamis, bersama dengan sifatnya yang diinterpretasikan, menjadikannya bahasa yang ideal untuk skrip dan pengembangan aplikasi yang cepat di banyak area di sebagian besar platform.
Python telah menjadi salah satu bahasa pemrograman yang paling populer di berbagai bidang karena sintaksisnya yang sederhana dan fleksibel

## Guided 

### 1. Control Flow

```python
value = 150
if value > 100:
    print("lebih dari 100")
else:
    print("100 atau kurang dari")
```
if value > 100:: Memeriksa apakah nilai variabel value lebih besar dari 100.
Jika benar (dalam hal ini value = 150, jadi benar), maka akan mencetak "lebih dari 100".
else:: Jika kondisi if salah (misalnya jika value bernilai 100 atau kurang), maka akan mencetak "100 atau kurang dari".

### 2. Fungsi Map

```python
numbers = [1, 2, 3, 4, 5]
squares = list(map(lambda x: x * x, numbers))
print(squares)
```
Fungsi map() adalah fungsi built-in Python yang digunakan untuk menerapkan suatu fungsi ke setiap item dalam sebuah iterable (seperti list).
Di sini, map() menerapkan fungsi lambda ke setiap elemen di list numbers. list(): Hasil map() perlu diubah kembali menjadi list, karena map() mengembalikan iterator. Fungsi list() digunakan untuk mengubah hasil tersebut menjadi list

### 3. perulangan bersarang (nested loops)
```python
for i in range(1, 11):
    for j in range(1, 11):
        print(f"{i} x {j} = {i * j}")
    print()
```
#### 1.for i in range(1, 11): Loop luar yang menjalankan i dari 1 hingga 10.
#### 2. for j in range(1, 11): Loop dalam yang menjalankan j dari 1 hingga 10 untuk setiap nilai i.
#### 3. print(f"{i} x {j} = {i * j}"): Menggunakan f-string untuk mencetak format perkalian antara i dan j. Misalnya, jika i = 1 dan j = 2, hasilnya adalah "1 x 2 = 2".
#### 4. print() (di luar loop dalam): Digunakan untuk mencetak baris kosong setelah satu set tabel perkalian selesai untuk setiap nilai i. Ini berguna untuk memberikan spasi antara tabel hasil perkalian untuk nilai i yang berbeda.

## Unguided 

### 1. [Soal]

```python
print("ini adalah file code guided praktikan")
```
#### Output:
![image](https://github.com/user-attachments/assets/fc05c081-b447-4e91-a2fc-24f481d8a593)


Kode di atas digunakan untuk mencetak teks "ini adalah file code guided praktikan" ke layar menggunakan function print untuk mengeksekusi nya.

## Kesimpulan
Ringkasan dan interpretasi pandangan kalia dari hasil praktikum dan pembelajaran yang didapat[1].

## Referensi
[1] I. Holm, Narrator, and J. Fullerton-Smith, Producer, How to Build a Human [DVD]. London: BBC; 2002.

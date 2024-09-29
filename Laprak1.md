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
 1.for i in range(1, 11): Loop luar yang menjalankan i dari 1 hingga 10.
 
 2. for j in range(1, 11): Loop dalam yang menjalankan j dari 1 hingga 10 untuk setiap nilai i.
    
 3. print(f"{i} x {j} = {i * j}"): Menggunakan f-string untuk mencetak format perkalian antara i dan j. Misalnya, jika i = 1 dan j = 2, hasilnya adalah "1 x 2 = 2".
    
 4. print() (di luar loop dalam): Digunakan untuk mencetak baris kosong setelah satu set tabel perkalian selesai untuk setiap nilai i. Ini berguna untuk memberikan spasi antara tabel hasil perkalian untuk nilai i yang berbeda.

 ### 4. Fungsi Rekursif
 ```python
def factorial(n):
    if n == 0:
        return 1
    else:
        return n * factorial(n-1)

print(factorial(5))
```
Fungsi rekursif adalah fungsi yang memanggil dirinya sendiri untuk menyelesaikan tugas. Setiap pemanggilan membutuhkan kondisi dasar (base case) untuk mencegah loop rekursif yang tidak pernah berhenti. Faktorial dari suatu bilangan bulat positif n (ditulis n!) adalah hasil perkalian semua bilangan bulat positif dari 1 hingga n. Secara matematis:

-n! = n * (n-1) * (n-2) * ... * 1

-Contoh: 5! = 5 * 4 * 3 * 2 * 1 = 120

### 5. Fungsi List
```python
numbers = [x for x in range(1, 11)]
print(numbers)
```
List comprehension: x for x in range(1, 11) adalah cara singkat untuk membuat list dari range(1, 11) tanpa harus menggunakan loop for yang panjang. List comprehension adalah cara yang lebih singkat dan mudah dibaca daripada menggunakan loop tradisional.

## Unguided 

### 1. Memecahkan Masalah Unik dengan Loop dan If-Else
**Soal**: Buatlah program yang dapat menghasilkan pola berbentuk angka seperti di bawah ini, dengan syarat angka yang ditampilkan adalah hasil dari penjumlahan bilangan prima sebelumnya:
```
1
2 3
5 7 11
13 17 19 23
...
```
Jumlah angka pada setiap baris bertambah 1, dan bilangan yang ditampilkan adalah bilangan prima.


```python
def apakah_prima(angka):
    if angka < 2:
        return False
    for i in range(2, int(angka ** 0.5) + 1):
        if angka % i == 0:
            return False
    return True

def buat_pola_prima(n):
    prima = []
    angka = 2
    jumlah_baris = 1
    
    # Mengumpulkan bilangan prima sebanyak total angka yang dibutuhkan
    while len(prima) < sum(range(1, n+1)):
        if apakah_prima(angka):
            prima.append(angka)
        angka += 1

    indeks = 0
    for baris in range(1, n+1):
        for kolom in range(baris):
            print(prima[indeks], end=" ")
            indeks += 1
        print()

buat_pola_prima(5)
```
#### Output:
![image](https://github.com/Arsitatw/Praktikum-Insfrastruktur/blob/master/praktikum%201/Screenshot%202024-09-29%20235305.png)

### 2. Soal 2: Membuat Fungsi dengan Syarat Spesifik
**Soal**: Buatlah sebuah fungsi yang menerima dua input berupa list angka. Fungsi ini harus mengembalikan sebuah list baru yang berisi elemen dari dua list input yang memiliki indeks ganjil. List baru tersebut juga harus diurutkan secara menurun berdasarkan nilai elemen

```python
def gabung_urut_indeks_ganjil(list1, list2):
    # Ambil elemen dari indeks ganjil di kedua list
    elemen_ganjil_list1 = [list1[i] for i in range(1, len(list1), 2)]
    elemen_ganjil_list2 = [list2[i] for i in range(1, len(list2), 2)]

    # Gabungkan kedua list
    gabungan = elemen_ganjil_list1 + elemen_ganjil_list2

    # Urutkan list secara menurun
    gabungan.sort(reverse=True)

    return gabungan

# Contoh penggunaan:
list1 = [10, 21, 34, 45, 56, 67]
list2 = [9, 18, 27, 36, 45, 54]

hasil = gabung_urut_indeks_ganjil(list1, list2)
print(hasil)
```

#### Output :
![image](https://github.com/Arsitatw/Praktikum-Insfrastruktur/blob/master/praktikum%201/Screenshot%202024-09-30%20000647.png)

### 3. Exception Handling dalam Konteks Nyata
**Soal**: Buat sebuah program untuk mensimulasikan transaksi ATM. Program harus:
1. Meminta pengguna memasukkan PIN (dibatasi 3 kali percobaan).
2. Setelah PIN benar, meminta jumlah penarikan.
3. Jika saldo kurang dari jumlah yang ditarik, munculkan pesan kesalahan.
4. Jika penarikan berhasil, tampilkan saldo akhir.

```python
def atm_simulasi():
    #variabel PIN dan saldo awal
    PIN_AKTUAL = "122333"
    saldo = 500000  #saldo
    
    #maksimum percobaan PIN
    percobaan = 3
    
    #dibatasi 3 kali percobaan
    for i in range(percobaan):
        pin = input("Masukkan PIN: ")
        
        if pin == PIN_AKTUAL:
            print("PIN benar.")
            
            #penarikan setelah PIN benar
            try:
                jumlah_tarik = int(input("Masukan Nominal penarikan: "))
                
                if jumlah_tarik > saldo:
                    print("Kesalahan: Saldo tidak cukup untuk penarikan ini.")
                else:
                    saldo -= jumlah_tarik
                    print(f"Penarikan berhasil! Saldo akhir Anda adalah: Rp {saldo}")
                
            except ValueError:
                print("Masukkan jumlah penarikan yang valid.")
            break
        else:
            print("PIN salah.")
            sisa_percobaan = percobaan - (i + 1)
            if sisa_percobaan > 0:
                print(f"PIN Salah! Anda hanya memiliki {sisa_percobaan} kesempatan lagi.")
            else:
                print("Akun Anda diblokir. Silakan hubungi layanan pelanggan.")
    
#fungsi simulasi ATM
atm_simulasi()
```
#### Output:
![image]

### 4. Studi Kasus Pengelolaan Data
**Soal**: Anda diberikan file CSV berisi data nilai ujian mahasiswa. Tugas Anda adalah menulis sebuah program yang:
1. Membaca file CSV dan menyimpan datanya ke dalam dictionary.
2. Menghitung rata-rata nilai tiap mahasiswa.
3. Menampilkan mahasiswa dengan nilai tertinggi dan terendah

```python
import pandas as pd

data = pd.read_csv('siswa_nilai.csv')
rata_rata = data['Nilai'].mean()
nilai_maksimum = data['Nilai'].max()
nilai_minimum = data['Nilai'].min()

print(f"Rata-rata nilai siswa: {rata_rata}")   
print(f"Nilai tertinggi dari data nilai siswa adalah: {nilai_maksimum}")
print(f"Nilai terendah dari data nilai siswa adalah: {nilai_minimum}")
```

#### Output:
![image]
### 5. Kombinasi Logika dan Kreativitas
**Soal**: Buatlah permainan sederhana menggunakan Python, di mana komputer akan memilih sebuah angka secara acak antara 1 hingga 100, dan pengguna harus menebak angka tersebut. Setiap tebakan yang salah akan memberikan petunjuk apakah angka yang ditebak lebih besar atau lebih kecil dari angka sebenarnya. Batasi jumlah percobaan menjadi 5 kali. Setelah permainan selesai, tampilkan apakah pemain menang atau kalah

```python
import random

# untuk ngerandom angka acak 1-100
angka_random = random.randint(1, 100)
jumlah_tebakan = 5

print("Selamat datang di permainan Tebak Angka!")
print("Anda memiliki 5 kesempatan untuk menebak angka tersebut.")

#ini untuk looping selama 5 kali percobaan
for percobaan in range(1, jumlah_tebakan + 1):
    tebakan = int(input(f"Percobaan {percobaan}: Masukkan tebakan Anda: "))

    if tebakan < angka_random:
        print("Tebakan Anda terlalu kecil.")
    elif tebakan > angka_random:
        print("Tebakan Anda terlalu besar.")
    else:
        print(f"Selamat! Anda berhasil menebak angka {angka_random} dalam {percobaan} percobaan!")
        break
else:
    print(f"Maaf, Anda telah kehabisan kesempatan. Angka yang benar adalah {angka_random}.")
```

#### Output:
![image]
### 6. Rekursi yang Tidak Biasa
**Soal**: Buat fungsi rekursif yang menerima input bilangan bulat `n` dan menghasilkan urutan bilangan seperti berikut ini:

Input: n = 4
Output: 1, 1, 2, 6, 24

Fungsi ini harus menggunakan konsep rekursi untuk menghitung faktorial setiap angka hingga `n`.

```python
def faktorial(n):
    if n == 0 or n == 1:
        return 1
    else:
        return n * faktorial(n - 1)

# Fungsi rekursif untuk menghasilkan urutan faktorial
def urutan_faktorial(n):
    if n == 0:
        return [1]  # Basis rekursi, faktorial 0 adalah 1
    else:
        # Rekursi, menghasilkan urutan faktorial sampai n-1 dan menambahkan faktorial n
        return urutan_faktorial(n - 1) + [faktorial(n)]

# Contoh penggunaan
n = 4
output = urutan_faktorial(n)
print(output)
```

#### Output:
![image]
### 7. Pemrograman dengan Algoritma Greedy
**Soal**: Buatlah program untuk memecahkan masalah "minimum coin change". Diberikan jumlah uang dan daftar nilai koin yang tersedia (misalnya, 1, 5, 10, 25), tentukan kombinasi minimum koin yang diperlukan untuk mencapai jumlah uang tersebut. Namun, program Anda harus bisa menangani koin-koin yang nilai dan jumlahnya ditentukan pengguna.
```python
def min_coin_change(total_amount, coins):
    # Inisialisasi tabel dp untuk menyimpan jumlah minimum koin untuk setiap jumlah
    dp = [float('inf')] * (total_amount + 1)
    dp[0] = 0  # Jumlah koin untuk mencapai jumlah 0 adalah 0

    # Iterasi untuk setiap jenis koin dan jumlahnya
    for coin_value, coin_count in coins:
        for amount in range(total_amount, -1, -1):
            for count in range(1, coin_count + 1):
                if amount >= count * coin_value:
                    dp[amount] = min(dp[amount], dp[amount - count * coin_value] + count)
                else:
                    break

    # Jika dp[total_amount] masih float('inf'), artinya tidak ada kombinasi yang mungkin
    if dp[total_amount] == float('inf'):
        return -1  # Tidak ada solusi
    else:
        return dp[total_amount]

# Input dari pengguna
total_amount = int(input("Masukkan jumlah uang: "))
n = int(input("Masukkan jumlah jenis koin: "))

coins = []
for _ in range(n):
    value = int(input("Masukkan nilai koin: "))
    count = int(input(f"Masukkan jumlah koin dengan nilai {value}: "))
    coins.append((value, count))

# Memanggil fungsi dan menampilkan hasil
result = min_coin_change(total_amount, coins)

if result == -1:
    print("Tidak mungkin mencapai jumlah dengan kombinasi koin yang tersedia.")
else:
    print(f"Kombinasi minimum koin yang diperlukan: {result}")
```

#### Output:
![image]

### 8. Kombinasi String dan Manipulasi List
**Soal**: Buat sebuah program yang menerima string dari pengguna dan mengonversi string tersebut menjadi sebuah list berisi kata-kata terbalik. Misalnya:

Input: "Saya suka Python"

Output: ["ayaS", "akus", "nohtyP"]

```python
input_string = input("Masukkan sebuah kalimat: ")

# Memecah string menjadi kata-kata dan membalik setiap kata
reversed_words = [word[::-1] for word in input_string.split()]

# Mencetak hasil
print(reversed_words)
```
#### Output:
![image]
### 9. Konsep Class dan Object-Oriented Programming
**Soal**: Buat class bernama `Buku` yang memiliki atribut `judul`, `penulis`, dan `tahun_terbit`. Buat method dalam class untuk menampilkan informasi buku, serta method untuk menghitung usia buku berdasarkan tahun saat ini. Buatlah 3 objek dari class `Buku` dan tampilkan informasi serta usia masing-masing buku.

```python
from datetime import datetime

class Buku:
    def __init__(self, judul, penulis, tahun_terbit):
        self.judul = judul
        self.penulis = penulis
        self.tahun_terbit = tahun_terbit

    # Method untuk menampilkan informasi buku
    def tampilkan_info(self):
        print(f"Judul: {self.judul}")
        print(f"Penulis: {self.penulis}")
        print(f"Tahun Terbit: {self.tahun_terbit}")
    
    # Method untuk menghitung usia buku
    def hitung_usia(self):
        tahun_sekarang = datetime.now().year
        return tahun_sekarang - self.tahun_terbit

# Membuat 3 objek dari class Buku
buku1 = Buku("Laskar Pelangi", "Andrea Hirata", 2005)
buku2 = Buku("Harry Potter and the Sorcerer's Stone", "J.K. Rowling", 1997)
buku3 = Buku("Negeri 5 Menara", "Ahmad Fuadi", 2009)

# Menampilkan informasi dan usia masing-masing buku
buku1.tampilkan_info()
print(f"Usia Buku: {buku1.hitung_usia()} tahun\n")

buku2.tampilkan_info()
print(f"Usia Buku: {buku2.hitung_usia()} tahun\n")

buku3.tampilkan_info()
print(f"Usia Buku: {buku3.hitung_usia()} tahun\n")
```

#### Output
![image](https://github.com/Arsitatw/Praktikum-Insfrastruktur/blob/master/praktikum%201/arsip-output/Screenshot%202024-09-30%20004452.png)

### 10. Algoritma dengan Persyaratan Logika Khusus
**Soal**: Buatlah program yang mengimplementasikan algoritma pencarian biner, namun dengan modifikasi: algoritma harus bisa mencari nilai di list yang hanya berisi angka genap, dan jika nilai yang dicari adalah angka ganjil, program harus menampilkan pesan bahwa nilai tersebut tidak bisa ditemukan.

```python
def binary_search_genap(arr, target):
    # Cek apakah target adalah angka ganjil
    if target % 2 != 0:
        print(f"Nilai {target} adalah angka ganjil dan tidak bisa ditemukan.")
        return False

    # Implementasi algoritma pencarian biner
    low = 0
    high = len(arr) - 1

    while low <= high:
        mid = (low + high) // 2

        # Cek apakah nilai target ditemukan di tengah
        if arr[mid] == target:
            return mid  # Kembalikan indeks dari target

        # Jika target lebih kecil, geser pencarian ke bagian kiri
        elif arr[mid] > target:
            high = mid - 1

        # Jika target lebih besar, geser pencarian ke bagian kanan
        else:
            low = mid + 1

    return -1  # Kembalikan -1 jika target tidak ditemukan

# Contoh list yang hanya berisi angka genap (harus dalam urutan naik untuk binary search)
arr = [2, 4, 6, 8, 10, 12, 14, 16, 18, 20]

# Input nilai yang dicari dari pengguna
target = int(input("Masukkan nilai yang ingin dicari: "))

# Panggil fungsi binary search dan tampilkan hasilnya
result = binary_search_genap(arr, target)

if result == -1:
    if target % 2 == 0:
        print(f"Nilai {target} tidak ditemukan di dalam list.")
else:
    print(f"Nilai {target} ditemukan di indeks {result}.")
```
#### Output:
![image](https://github.com/Arsitatw/Praktikum-Insfrastruktur/blob/master/praktikum%201/arsip-output/Screenshot%202024-09-30%20004516.png)

## Kesimpulan
Ringkasan dan interpretasi pandangan kalia dari hasil praktikum dan pembelajaran yang didapat[1].

## Referensi
[1] I. Holm, Narrator, and J. Fullerton-Smith, Producer, How to Build a Human [DVD]. London: BBC; 2002.

# Tugas Sistem Operasi – Linux Text Editor

![Linux](https://img.shields.io/badge/Linux-Operating%20System-FCC624?logo=linux&logoColor=black)
![Nano](https://img.shields.io/badge/Editor-Nano-4EAA25)
![Vi](https://img.shields.io/badge/Editor-Vi-019733)
![Vim](https://img.shields.io/badge/Editor-Vim-019733)
![Python](https://img.shields.io/badge/Language-Python-3776AB?logo=python&logoColor=white)

Repositori ini berisi dokumentasi praktikum Sistem Operasi mengenai penggunaan editor teks berbasis terminal pada Linux, meliputi **GNU Nano, Vi/Vim, opsi `-v`, serta pembuatan program kalkulator sederhana menggunakan Python**.

---

## Daftar Isi

1. [Nano Text Editor](#1-nano-text-editor)
2. [Opsi -v pada Perintah Linux](#2-opsi-v-pada-perintah-linux)
3. [Vi dan Vim Text Editor](#3-vi-dan-vim-text-editor)
4. [Kalkulator Python Menggunakan Nano](#4-kalkulator-python-menggunakan-nano)
5. [Kalkulator Python Menggunakan Vi](#5-kalkulator-python-menggunakan-vi)
6. [Kalkulator Python Menggunakan Vim](#6-kalkulator-python-menggunakan-vim)
7. [Kesimpulan](#kesimpulan)

---

## 1. Nano Text Editor

**GNU Nano** merupakan editor teks berbasis terminal yang mudah digunakan di Linux. Nano memiliki antarmuka sederhana dan menampilkan berbagai shortcut pada bagian bawah layar.

### Membuka file

```bash
nano nama_file.txt
```

### Tampilan antarmuka Nano

```text
GNU nano 6.2                    nama_file

Isi file ditampilkan di sini...

^G Get Help  ^O Write Out  ^W Where Is  ^K Cut Text
^X Exit      ^R Read File  ^\ Replace   ^U Paste Text
```

![Tampilan antarmuka Nano](https://github.com/telloze/TUGAS-SISTEM-OPERASI/blob/main/antarmuka.png)

*Catatan: Simbol `^` menunjukkan tombol Ctrl. Contohnya, `^X` berarti Ctrl + X.*

### Shortcut Nano

| Shortcut | Fungsi |
|---|---|
| `Ctrl + O` | Menyimpan file (Write Out) |
| `Ctrl + X` | Keluar dari Nano |
| `Ctrl + W` | Mencari teks |
| `Ctrl + K` | Memotong satu baris |
| `Ctrl + U` | Menempelkan teks |
| `Ctrl + G` | Membuka bantuan |
| `Ctrl + R` | Membaca atau memasukkan file |
| `Ctrl + T` | Membuka fitur pemeriksaan ejaan jika tersedia |

### Opsi-opsi Nano

| Opsi | Fungsi | Contoh |
|---|---|---|
| `-v` | Membuka file dalam mode view/read-only | `nano -v file.txt` |
| `-c` | Menampilkan posisi kursor | `nano -c file.txt` |
| `-i` | Mengaktifkan auto-indent | `nano -i file.txt` |
| `-m` | Mengaktifkan dukungan mouse | `nano -m file.txt` |
| `-l` | Menampilkan nomor baris | `nano -l file.txt` |
| `-V` | Menampilkan informasi versi Nano | `nano -V` |

---

## 2. Opsi -v pada Perintah Linux

Opsi `-v` tidak memiliki fungsi yang sama pada semua perintah Linux. Artinya bergantung pada program yang digunakan.

Berikut beberapa contohnya.

| Perintah | Fungsi |
|---|---|
| `nano -v file.txt` | Membuka file dalam mode view |
| `python -v` | Menampilkan informasi proses import modul Python |
| `python3 -v` | Menampilkan informasi import pada Python 3 |
| `ls -v` | Mengurutkan nama file secara natural |
| `grep -v "error" log.txt` | Menampilkan baris yang tidak cocok dengan pola |
| `cat -v file.txt` | Menampilkan karakter non-printable secara representatif |
| `cp -v file1.txt backup/` | Menampilkan informasi proses penyalinan |
| `chmod -v 755 file.txt` | Menampilkan informasi perubahan permission |

### Menampilkan versi Nano

Untuk melihat versi Nano, gunakan opsi `-V` dengan huruf kapital:

```bash
nano -V
```

**Perlu diperhatikan:** `-v` dan `-V` merupakan dua opsi yang berbeda. Penggunaan huruf kecil dan kapital dapat menghasilkan fungsi yang berbeda.

---

## 3. Vi dan Vim Text Editor

**Vi (Visual Editor)** merupakan editor teks berbasis terminal yang tersedia pada berbagai sistem Unix/Linux. Sementara itu, **Vim (Vi Improved)** merupakan pengembangan Vi dengan fitur tambahan.

### Membuka file

Menggunakan Vi:

```bash
vi nama_file.txt
```

Menggunakan Vim:

```bash
vim nama_file.txt
```

### Mode pada Vi/Vim

| Mode | Fungsi |
|---|---|
| Normal Mode | Menjalankan perintah navigasi dan pengeditan |
| Insert Mode | Memasukkan atau mengubah teks |
| Command-line Mode | Menjalankan perintah seperti menyimpan dan keluar |

### Perintah dasar Vi/Vim

| Perintah | Fungsi |
|---|---|
| `i` | Masuk ke Insert Mode |
| `Esc` | Kembali ke Normal Mode |
| `:w` | Menyimpan file |
| `:q` | Keluar dari editor |
| `:wq` | Menyimpan dan keluar |
| `:q!` | Keluar tanpa menyimpan |
| `dd` | Menghapus satu baris |
| `yy` | Menyalin satu baris |
| `p` | Menempelkan hasil salinan |

### Mode Read Only

Untuk membuka file dalam mode hanya-baca:

```bash
vi -R nama_file.txt
```

Mode ini membatasi pengeditan file. Jika ingin menyimpan perubahan, diperlukan izin tulis yang sesuai.

---

## 4. Kalkulator Python Menggunakan Nano

Pada bagian ini dibuat program kalkulator sederhana menggunakan bahasa Python melalui editor Nano.

### Membuat file

```bash
nano kalkulator.py
```

### Source Code

```python
# Kalkulator Sederhana dengan Python

def tambah(x, y):
    return x + y

def kurang(x, y):
    return x - y

def kali(x, y):
    return x * y

def bagi(x, y):
    if y != 0:
        return x / y
    else:
        return "Tidak bisa membagi dengan nol!"

print("Pilih operasi:")
print("1. Tambah")
print("2. Kurang")
print("3. Kali")
print("4. Bagi")

pilihan = input("Masukkan pilihan (1/2/3/4): ")

angka1 = float(input("Masukkan angka pertama: "))
angka2 = float(input("Masukkan angka kedua: "))

if pilihan == '1':
    print(f"{angka1} + {angka2} = {tambah(angka1, angka2)}")
elif pilihan == '2':
    print(f"{angka1} - {angka2} = {kurang(angka1, angka2)}")
elif pilihan == '3':
    print(f"{angka1} * {angka2} = {kali(angka1, angka2)}")
elif pilihan == '4':
    print(f"{angka1} / {angka2} = {bagi(angka1, angka2)}")
else:
    print("Pilihan tidak valid")
```

### Menyimpan dan keluar dari Nano

Tekan kombinasi tombol:

```text
Ctrl + X → Y → Enter
```

### Menjalankan program

```bash
python3 kalkulator.py
```

### Hasil Program

**Penjumlahan**

![Hasil Penjumlahan](https://github.com/telloze/TUGAS-SISTEM-OPERASI/blob/main/tambah.jpg)

**Pengurangan**

![Hasil Pengurangan](https://github.com/telloze/TUGAS-SISTEM-OPERASI/blob/main/kurang.jpg)

**Perkalian**

![Hasil Perkalian](https://github.com/telloze/TUGAS-SISTEM-OPERASI/blob/main/kali.jpg)

**Pembagian**

![Hasil Pembagian](https://github.com/telloze/TUGAS-SISTEM-OPERASI/blob/main/bagi.jpg)

---

## 5. Kalkulator Python Menggunakan Vi

Program kalkulator yang sama juga dapat dibuat menggunakan editor Vi.

### Membuat file

```bash
vi kalkulator.py
```

Masukkan source code kalkulator Python yang telah dijelaskan pada bagian sebelumnya.

### Menyimpan dan keluar

Tekan `Esc`, kemudian ketik:

```vim
:wq
```

### Menjalankan program

```bash
python3 kalkulator.py
```

---

## 6. Kalkulator Python Menggunakan Vim

Selain Nano dan Vi, program kalkulator juga dapat dibuat menggunakan Vim.

### Membuat file

```bash
vim kalkulator.py
```

Masukkan source code kalkulator Python yang sama.

### Menyimpan dan keluar

Tekan `Esc`, kemudian ketik:

```vim
:wq
```

### Menjalankan program

```bash
python3 kalkulator.py
```

---

## Kesimpulan

Berdasarkan praktikum yang telah dilakukan, dapat disimpulkan bahwa:

1. Nano merupakan editor teks berbasis terminal yang sederhana dan mudah digunakan.
2. Vi dan Vim menyediakan berbagai mode serta perintah untuk mengedit teks secara efisien.
3. Opsi `-v` memiliki fungsi yang berbeda bergantung pada perintah Linux yang digunakan.
4. Program Python dapat dibuat dan diedit menggunakan berbagai editor teks, seperti Nano, Vi, dan Vim.
5. Program kalkulator sederhana dapat memanfaatkan fungsi, percabangan, input pengguna, serta operasi aritmatika dalam Python.

Melalui praktikum ini, diperoleh pemahaman mengenai penggunaan editor teks Linux dan penerapannya dalam pembuatan program sederhana.

---

**Tugas Sistem Operasi – Linux**  
*Dokumentasi Praktikum Editor Teks dan Pemrograman Python*

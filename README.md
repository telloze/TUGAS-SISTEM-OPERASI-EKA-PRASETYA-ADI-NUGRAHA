# Tugas Sistem Operasi - Linux

## 📌 Deskripsi
Repository ini berisi penjelasan mengenai editor teks **Nano**, opsi `-v`, editor **Vi**, serta program kalkulator sederhana menggunakan **Nano** di Linux.

---

## 📝 1. Nano
**Nano** adalah editor teks berbasis terminal yang mudah digunakan di Linux.  
Untuk membuka file dengan Nano, gunakan perintah:
```bash
nano nama_file
```
Tampilan antarmuka nano
```bash
GNU nano 6.2                    nama_file                                
                                                                       
Isi file ditampilkan di sini...
                                                                       
^G Get Help  ^O Write Out  ^W Where Is  ^K Cut Text  ^J Justify        
^X Exit      ^R Read File  ^\ Replace   ^U Paste Text  ^T To Spell     
```
Tampilan nano

![Tampilan antarmuka nano](https://github.com/telloze/TUGAS-SISTEM-OPERASI/blob/main/antarmuka.png)
*Keterangan:  
^ berarti tombol Ctrl.  
Misalnya, ^X berarti tekan Ctrl + X untuk keluar.*  
  
**Shortcut**  
| Pintasan  | Fungsi                          |
|-----------|---------------------------------|
| Ctrl + O  | Simpan file (Write Out)        |
| Ctrl + X  | Keluar dari Nano               |
| Ctrl + W  | Mencari teks dalam file        |
| Ctrl + K  | Memotong (cut) baris teks      |
| Ctrl + U  | Menempelkan (paste) teks       |
| Ctrl + G  | Menampilkan bantuan (Help)     |
| Ctrl + R  | Membuka file lain dalam Nano   |
| Ctrl + T  | Mengecek ejaan dalam teks      |  

  **Opsi-opsi nano** 
    
  Mode read only  
  ```bash
nano -v nama_file.txt
```
Menampilkan nomor dan baris  
  ```bash
nano -c nama_file.txt
```
Auto-indent saat mengetik kode  
  ```bash
nano -i nama_file.txt
```
Mengaktifkan fitur mouse  
  ```bash
nano -m nama_file.txt
```
Highlight syntax  
  ```bash
nano -l nama_file.txt
```

---

 ## 📝 2. -V  
Opsi **-v** biasanya berarti *"verbose"* (menampilkan lebih banyak detail). Namun, maknanya bisa berbeda tergantung perintah yang digunakan.  

Menampilkan versi nano  
```bash
nano -V
```
Menampilkan versi python
```bash
python -v
```
atau
```bash
python3 -v
```
Menyortir file secara alami
```bash
ls -v
```
Menampilkan baris yang tidak cocok
```bash
grep -v "error" log.txt
```
menampilkan karakter tersembunyi
```bash
cat -v file.txt
```
Menampilkan perubahan izin file
```bash
chmod -v
```
Menampilkan detail copy file
```bash
cp -v file1.txt backup/
```

  ---
    
## 📝 3. Vi / Vim - Editor Teks yang Lebih Kompleks  
**Vi** (Visual Editor) adalah editor teks bawaan di Linux yang lebih canggih daripada Nano.
Versi yang lebih modern dan populer disebut **Vim** (Vi Improved).  
Membuka file dengan vi
```bash
vi nama_file.txt
```
atau
```bash
vim nama_file.txt
```

Perintah dasar vi
| Perintah | Fungsi |
|----------|--------|
| `i`      | Masuk ke mode Insert (untuk mengetik) |
| `Esc`    | Kembali ke Normal Mode |
| `:w`     | Simpan file |
| `:q`     | Keluar dari Vi |
| `:wq`    | Simpan dan keluar |
| `:q!`    | Keluar tanpa menyimpan |
| `dd`     | Hapus satu baris |
| `yy`     | Copy satu baris |
| `p`      | Paste hasil copy |

Vi mode read only
```bash
vi -R nama_file.txt
```
bisa di edit dengan
```bash
:wq!
```
 ---
## 📝 4. Kalkulator Sederhana

Membuat file py 
```bash
nano kalkulator.py
```
Kode python kalkulator sederhana
```bash
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

simpan dan keluar dari menu nano  
*ctrl+x -> y -> enter*

Menjalankan kode python
```bash
python3 kalkulator.py
```
Hasil  

    
  




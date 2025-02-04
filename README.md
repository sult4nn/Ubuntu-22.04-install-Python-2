# Cara Mengaktifkan Python 2 di Ubuntu 22.04

Python 2 sudah deprecated dan tidak lagi didukung secara resmi di Ubuntu 22.04. 
Namun, jika tetap ingin menggunakannya, ikuti langkah-langkah berikut:

## 1. Perbarui Repository
Jalankan perintah berikut untuk memastikan sistem diperbarui:
```bash
sudo apt update && sudo apt upgrade -y
```

## 2. Install Python 2
Karena Python 2 tidak lagi tersedia secara default, kita bisa menginstalnya dengan:
```bash
sudo apt install python2 -y
```

## 3. Verifikasi Instalasi
Setelah instalasi selesai, periksa apakah Python 2 telah terpasang:
```bash
python2 --version
```
Jika berhasil, akan muncul output seperti:
```
Python 2.7.X
```

## 4. Install pip untuk Python 2
Paket `python2-pip` sudah tidak tersedia, jadi kita harus menginstalnya secara manual:
```bash
curl https://bootstrap.pypa.io/pip/2.7/get-pip.py -o get-pip.py
python2 get-pip.py
```

## 5. Pastikan pip dapat digunakan
Setelah instalasi selesai, verifikasi dengan:
```bash
python2 -m pip --version
```
Jika berhasil, akan muncul:
```
pip 20.3.4 from /usr/local/lib/python2.7/site-packages/pip (python 2.7)
```

## 6. (Opsional) Tambahkan pip ke PATH
Jika `pip2` tidak dikenali, tambahkan ke PATH dengan:
``` bash  
export PATH=$HOME/.local/bin:$PATH
```
Untuk membuatnya permanen, tambahkan perintah di atas ke `~/.bashrc` atau `~/.bash_profile`.

## 7. Menggunakan Python 2 secara Default (Opsional)
Jika ingin menjalankan `python` langsung tanpa `python2`, gunakan alias:
```bash
alias python=python2
```
Untuk menjadikannya permanen:
```bash
echo "alias python=python2" >> ~/.bashrc
source ~/.bashrc
```

Dengan langkah-langkah ini, Python 2 bisa berjalan di Ubuntu 22.04 meskipun tidak lagi didukung secara resmi.

# Catatan:
- Python 2 sudah usang dan tidak disarankan untuk digunakan.
- Gunakan Python 3 jika memungkinkan, karena memiliki dukungan penuh.

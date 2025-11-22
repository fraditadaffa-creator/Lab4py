
# 🧾 **Penjelasan Program Input Data Mahasiswa**

Program ini merupakan aplikasi sederhana berbasis Python yang berfungsi untuk:

1. **Menerima input data mahasiswa**
2. **Menghitung nilai akhir**
3. **Menyimpan data dalam list**
4. **Menampilkan seluruh data dalam bentuk tabel**

Struktur program dibuat agar dapat menerima **data sebanyak yang diinginkan** oleh pengguna melalui perulangan.

---

# 🔍 **Penjelasan Bagian per Bagian**

## 1️⃣ **Inisialisasi List**

```python
data = []
```

List `data` digunakan untuk menyimpan seluruh data mahasiswa dalam bentuk list di dalam list.

---

## 2️⃣ **Perulangan Input (while True)**

```python
while True:
    print("\nMasukkan data mahasiswa:")
```

Bagian ini membuat program terus meminta input hingga pengguna memilih berhenti (`t`).

Dalam perulangan, program meminta:

```python
nama = input("Nama  : ")
nim  = input("NIM   : ")
tugas = float(input("Nilai Tugas : "))
uts   = float(input("Nilai UTS   : "))
uas   = float(input("Nilai UAS   : "))
```

Fungsi:

* `input()` untuk menerima data
* `float()` digunakan untuk memastikan nilai tugas/uts/uas bisa dihitung

---

## 3️⃣ **Perhitungan Nilai Akhir**

```python
akhir = (0.30 * tugas) + (0.35 * uts) + (0.35 * uas)
```

Rumus sesuai ketentuan:

* Tugas: 30%
* UTS: 35%
* UAS: 35%

---

## 4️⃣ **Menyimpan Data ke dalam List**

```python
data.append([nama, nim, tugas, uts, uas, akhir])
```

Format data yang disimpan dalam setiap baris:

```
[nama, nim, nilai_tugas, nilai_uts, nilai_uas, nilai_akhir]
```

---

## 5️⃣ **Pertanyaan untuk Menambah Data**

```python
lanjut = input("Tambah data(y/t)? ").lower()
if lanjut == 't':
    break
```

Jika pengguna menjawab:

* `y` → kembali ke awal perulangan
* `t` → perulangan berhenti

---

## 6️⃣ **Menampilkan Data dalam Bentuk Tabel**

Header tabel:

```python
print("\n" + "="*70)
print("| No |    Nama    |  NIM  | Tugas | UTS | UAS | Akhir |")
print("="*70)
```

Lalu seluruh data dicetak menggunakan looping:

```python
no = 1
for d in data:
    print(f"| {no:<2} | {d[0]:<10} | {d[1]:<5} | {d[2]:<5} | {d[3]:<3} | {d[4]:<3} | {d[5]:<5.2f} |")
    no += 1
```

Penjelasan format (`:<10`, `<5.2f`, dll.)

* Mengatur agar kolom tabel tetap rapi
* `<5.2f` menandakan nilai akhir dicetak dengan 2 angka di belakang koma

---

# 📌 **Kesimpulan**

Program ini:

* Menggunakan **perulangan** untuk menerima data sebanyak yang dibutuhkan
* Menggunakan **list** untuk menyimpan banyak data sekaligus
* Menerapkan konsep **perhitungan numerik** dengan persentase
* Menampilkan hasil dalam **format tabel yang rapi**
* Bersifat dinamis dan mudah dikembangkan (misalnya ditambah validasi, menu, dll.)

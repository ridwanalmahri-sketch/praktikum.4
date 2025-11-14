Program Input Data Mahasiswa

Program ini dibuat sebagai aplikasi sederhana berbasis Python yang berfungsi untuk mencatat dan menampilkan informasi mahasiswa. Melalui program ini, pengguna dapat memasukkan nama mahasiswa beserta nilai Tugas, UTS, dan UAS. Setiap nilai yang diinput akan diproses lebih lanjut untuk menghitung nilai akhir secara otomatis menggunakan pembobotan yang telah ditentukan, yaitu 30% untuk Tugas, 35% untuk UTS, dan 35% untuk UAS.

Program ini dirancang agar mudah digunakan, dilengkapi dengan validasi input untuk memastikan bahwa nilai yang dimasukkan benar-benar berupa angka. Setelah semua data berhasil dicatat, program akan menampilkan seluruh daftar mahasiswa lengkap dengan nilai akhir masing-masing. Jumlah total data yang berhasil dimasukkan juga akan ditampilkan di bagian akhir sebagai ringkasan.

 Cara Menjalankan Program

Untuk menggunakan aplikasi ini, pastikan Python sudah terinstal di perangkat Anda. Simpan file kode dalam format .py, lalu jalankan melalui terminal atau command prompt dengan perintah:

python nama_file.py


atau, pada lingkungan spesifik seperti contoh berikut:

& "C:/Users/Projek Muda/AppData/Local/Python/pythoncore-3.14-64/python.exe" "c:/Users/Projek Muda/Downloads/pytthon/6.py"


Proses selanjutnya akan menuntun Anda memasukkan data mahasiswa satu per satu.

 Gambaran Penggunaan

Setelah program dijalankan, pengguna akan dipandu untuk memasukkan nama serta nilai Tugas, UTS, dan UAS. Begitu data dimasukkan dengan benar, program akan menampilkan nilai akhir mahasiswa tersebut. Pengguna juga dapat memilih apakah ingin menambahkan data baru atau mengakhiri proses input.

Saat semua proses selesai, program akan menampilkan seluruh daftar mahasiswa yang telah dicatat, termasuk nilai masing-masing, dan menghitung total data yang berhasil disimpan.


def tambah_data():
    """Program untuk menambahkan data mahasiswa ke dalam list"""
    
    # List untuk menyimpan data mahasiswa
    data_mahasiswa = []
    
    print("=" * 50)
    print("PROGRAM INPUT DATA MAHASISWA")
    print("=" * 50)
    
    while True:
        # Input data mahasiswa
        print("\n--- Input Data Baru ---")
        nama = input("Ridwan: ")
        
        # Input nilai dengan validasi
        try:
            tugas = float(input("Nilai Tugas (0-100): "))
            uts = float(input("Nilai UTS (0-100): "))
            uas = float(input("Nilai UAS (0-100): "))
            
            # Hitung nilai akhir (tugas: 30%, uts: 35%, uas: 35%)
            nilai_akhir = (tugas * 0.30) + (uts * 0.35) + (uas * 0.35)
            
            # Simpan data ke list
            mahasiswa = {
                'nama': nama,
                'tugas': tugas,
                'uts': uts,
                'uas': uas,
                'nilai_akhir': nilai_akhir
            }
            data_mahasiswa.append(mahasiswa)
            
            print(f"\n✓ Data berhasil ditambahkan!")
            print(f"  Nilai Akhir: {nilai_akhir:.2f}")
            
        except ValueError:
            print("✗ Error: Masukkan nilai berupa angka!")
            continue
        
        # Tanya apakah ingin menambah data lagi
        tambah = input("\nTambah data lagi? (y/t): ").lower()
        if tambah != 'y':
            break
    
    # Tampilkan semua data
    print("\n" + "=" * 50)
    print("DAFTAR DATA MAHASISWA")
    print("=" * 50)
    
    if not data_mahasiswa:
        print("Tidak ada data.")
    else:
        for i, mhs in enumerate(data_mahasiswa, 1):
            print(f"\nData ke-{i}")
            print(f"  Nama        : {mhs['nama']}")
            print(f"  Nilai Tugas : {mhs['tugas']}")
            print(f"  Nilai UTS   : {mhs['uts']}")
            print(f"  Nilai UAS   : {mhs['uas']}")
            print(f"  Nilai Akhir : {mhs['nilai_akhir']:.2f}")
    
    print("\n" + "=" * 50)
    print(f"Total data: {len(data_mahasiswa)}")
    print("=" * 50)

# Jalankan program
if __name__ == "__main__":
    tambah_data()


==================================================
PROGRAM INPUT DATA MAHASISWA
==================================================

--- Input Data Baru ---
Ridwan: almahri
Nilai Tugas (0-100): 60
Nilai UTS (0-100): 70
Nilai UAS (0-100): 80

✓ Data berhasil ditambahkan!
  Nilai Akhir: 70.50

Tambah data lagi? (y/t): y

--- Input Data Baru ---
Ridwan: wannn
Nilai Tugas (0-100): 76
Nilai UTS (0-100): 67
Nilai UAS (0-100): 87

✓ Data berhasil ditambahkan!
  Nilai Akhir: 76.70

Tambah data lagi? (y/t): t

==================================================
DAFTAR DATA MAHASISWA
==================================================

Data ke-1
  Nama        : almahri
  Nilai Tugas : 60.0
  Nilai UTS   : 70.0
  Nilai UAS   : 80.0
  Nilai Akhir : 70.50

Data ke-2
  Nama        : wannn
  Nilai Tugas : 76.0
  Nilai UTS   : 67.0
  Nilai UAS   : 87.0
  Nilai Akhir : 76.70

==================================================
Total data: 2
==================================================
PS C:\Users\Projek Muda\Downloads\pytthon>

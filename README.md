NAMA    : M.RIDWAN ALMAHRI

NIM     : 312510157

Program Input Data Mahasiswa

Program ini merupakan aplikasi sederhana berbasis Python untuk menginput dan menampilkan data mahasiswa.
Data yang dimasukkan meliputi:

Nama

Nilai Tugas

Nilai UTS

Nilai UAS
Program juga secara otomatis menghitung nilai akhir dengan rumus:

Nilai Akhir = (Tugas × 30%) + (UTS × 35%) + (UAS × 35%)

Fitur Program

- Input data mahasiswa sebanyak yang diinginkan
- Validasi nilai agar berupa angka
- Perhitungan nilai akhir secara otomatis
- Menampilkan seluruh data yang telah dimasukka
- Menampilkan total jumlah data

Cara Menjalankan Program

Pastikan Python sudah terinstal di perangkat Anda.

Simpan file program dengan nama 6.py atau sesuai kebutuhan.

Jalankan melalui terminal atau command prompt:

python 6.py


atau di sistem Anda:

& "C:/Users/Projek Muda/AppData/Local/Python/pythoncore-3.14-64/python.exe" "c:/Users/Projek Muda/Downloads/pytthon/6.py"

 Contoh Penggunaan

Saat program dijalankan, Anda akan diminta mengisi data:

==================================================
PROGRAM INPUT DATA MAHASISWA
==================================================

--- Input Data Baru ---
Ridwan: almahri
Nilai Tugas (0-100): 60
Nilai UTS (0-100): 70
Nilai UAS (0-100): 80

- Data berhasil ditambahkan!
  Nilai Akhir: 70.50

Tambah data lagi? (y/t): y


Dan setelah selesai:

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

 Kode Program Lengkap
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

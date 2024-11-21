#praktikum

LATIHAN 1

soal
• Buat Dictionary daftar kontak
• Nama sebagai key, dan nomor sebagai value
• Tampilkan kontaknya Rara
• Tambah kontak baru dengan nama Rizki, nomor 089076543
• Ubah kontak Fitri dengan nomor baru 085647321
• Tampilkan semua Nama
• Tampilkan semua Nomor
• Tampilkan daftar Nama dan nomornya
• Hapus kontak Fitri.

kode python

    # 1. Buat Dictionary daftar kontak
     daftar_kontak = {
    "Rara": "08347782101",
    "Rizal": "08445511761",
    "Fitri": "08769003216"
     }

    # 2. Tampilkan kontaknya Rara
    print("Kontak Rara:", daftar_kontak.get("Rara"))

    # 3. Tambah kontak baru dengan nama Rizki, nomor 089076543
    daftar_kontak["Rizki"] = "089076543"
    print("Kontak Rizki telah ditambahkan.")

    # 4. Ubah kontak Fitri dengan nomor baru 085647321
    daftar_kontak["Fitri"] = "085647321"
    print("Kontak Fitri telah diubah.")

    # 5. Tampilkan semua Nama
    print("Semua Nama:", list(daftar_kontak.keys()))

    # 6. Tampilkan semua Nomor
    print("Semua Nomor:", list(daftar_kontak.values()))

    # 7. Tampilkan daftar Nama dan nomornya
    print("Daftar Nama dan Nomornya:")
    for nama, nomor in daftar_kontak.items():
    print(f"{nama}: {nomor}")

    # 8. Hapus kontak Fitri
    if "Fitri" in daftar_kontak:
    del daftar_kontak["Fitri"]
    print("Kontak Fitri telah dihapus.")
    else:
    print("Kontak Fitri tidak ditemukan.")

    penjelasan:
    1. Membuat Dictionary Daftar Kontak ( Di sini, sebuah dictionary bernama daftar_kontak dibuat.
    Kunci (key) dari dictionary ini adalah nama-nama kontak (Rara,Rizal,Fitrii), dan nilainya (value) adalah nomor telepon yang sesuai. )
    2. Menampilkan Kontak Rara ( Menggunakan metode get(), kode ini menampilkan nomor telepon yang terdaftar untuk kontak "Rara". 
    Jika "Rara" tidak ada dalam dictionary, get() akan mengembalikan None tanpa menghasilkan error. ) 
    3. Menambahkan Kontak Baru ( Di sini, kontak baru dengan nama "Rizki" dan nomor "089076543" ditambahkan ke dalam dictionary.
    Jika nama tersebut sudah ada, nilainya akan diperbarui. )
    Secara keseluruhan, kode ini menunjukkan bagaimana cara membuat, mengubah, menampilkan, dan menghapus data dalam sebuah dictionary yang digunakan untuk menyimpan daftar kontak.
    4.Mengubah Kontak Fitri ( Kontak "Fitri" diubah dengan nomor baru "085647321".
    Jika "Fitri" tidak ada, maka kontak baru akan ditambahkan. )
    5. Menampilkan Semua Nama (digunakan untuk mendapatkan semua kunci (nama) dari dictionary, yang kemudian diubah menjadi list untuk ditampilkan)
    6. Menampilkan Semua Nomor (digunakan untuk mendapatkan semua nilai (nomor telepon) dari dictionary, yang juga diubah menjadi list untuk ditampilkan.)
    7. Menampilkan Daftar Nama dan Nomornya (digunakan untuk mendapatkan pasangan kunci-nilai dari dictionary. Dalam loop, setiap nama dan nomor ditampilkan dalam format yang rapi.)
    8.Menghapus Kontak Fitri

    PRAKTIKUM 5

    soal
 Buat program sederhana yang akan menampilkan daftar nilai mahasiswa, dengan ketentuan : 
   1. Program dibuat dengan menggunakan Dictionary
   2. Tampilkan menu pilihan: (Tambah Data, Ubah Data, Hapus Data, Tampilkan Data, Cari Data)
   3. Nilai Akhir diambil dari perhitungan 3 komponen nilai (tugas: 30%, uts: 35%, uas: 35%)
   4. Buat flowchart dan penjelasan programnya
    
   kode python
   
    # Pastikan dictionary mahasiswa sudah didefinisikan
    mahasiswa = {}

    def tambah_data():
    print("\n=== TAMBAH DATA MAHASISWA ===")
    nama = input("Masukkan Nama: ")
    
    if nama in mahasiswa:  # Cek apakah nama sudah ada
        print("Data mahasiswa sudah ada!")
        return
    
     try:
        # Input nilai
        tugas = float(input("Nilai Tugas (0-100): "))
        uts = float(input("Nilai UTS (0-100): "))
        uas = float(input("Nilai UAS (0-100): "))
        
        # Validasi rentang nilai
        if not (0 <= tugas <= 100 and 0 <= uts <= 100 and 0 <= uas <= 100):
            print("Nilai harus berada dalam rentang 0-100!")
            return
        
        # Hitung nilai akhir
        nilai_akhir = (tugas * 0.3) + (uts * 0.35) + (uas * 0.35)
        
        # Simpan ke dictionary
        mahasiswa[nama] = {
            "tugas": tugas,
            "uts": uts,
            "uas": uas,
            "nilai_akhir": nilai_akhir
         }
        print("Data berhasil ditambahkan!")
    
       except ValueError:
        print("Input tidak valid! Pastikan untuk memasukkan angka.")

       # Contoh pemanggilan fungsi
       tambah_data() 

       penjelasan: 
1. Fungsi lihat_data():
        Menampilkan daftar nilai mahasiswa dalam format tabel.
        Jika tidak ada data, menampilkan pesan bahwa tidak ada data.
        Menghitung nilai akhir berdasarkan bobot: 30% untuk tugas, 35% untuk UTS, dan 35% untuk UAS.
        Menggunakan enumerate untuk menampilkan nomor urut mahasiswa.
2. Fungsi tambah_data():
        Meminta input dari pengguna untuk menambahkan data mahasiswa baru.
        Data yang dimasukkan (NIM, nama, nilai tugas, UTS, dan UAS) disimpan dalam dictionary dan ditambahkan ke list data_mahasiswa.
        Menampilkan pesan konfirmasi bahwa data berhasil ditambahkan.
3. Fungsi ubah_data():
        Menampilkan data yang ada dengan memanggil lihat_data().
        Meminta pengguna untuk memasukkan nomor data yang ingin diubah.
        Jika nomor valid, pengguna diminta untuk memasukkan data baru, yang kemudian menggantikan data lama di list.
        Menampilkan pesan konfirmasi bahwa data berhasil diubah.
4. Fungsi hapus_data():
        Menampilkan data yang ada dengan memanggil lihat_data().
        Meminta pengguna untuk memasukkan nomor data yang ingin dihapus.
        Jika nomor valid, data dihapus dari list menggunakan pop().
        Menampilkan pesan konfirmasi bahwa data berhasil dihapus.
5. Fungsi cari_data():
        Meminta pengguna untuk memasukkan NIM yang ingin dicari.
        Mencari data mahasiswa berdasarkan NIM dan menampilkan hasilnya dalam format tabel.
        Jika tidak ditemukan, menampilkan pesan bahwa data tidak ditemukan.
  
  
    

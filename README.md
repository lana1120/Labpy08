# Labpy08

**Tugas Pemrograman Pertuemuan11**

**Nama: Maulana Malik Ibrahim ( 312410185 )**

# FLOWCHART
# Python

  class Mahasiswa:
    def __init__ (self):
        self.daftar_mahasiswa = []

    def tambah(self, nama, nim, nilai):
        self.daftar_mahasiswa.append({'nama': nama, 'nim': nim, 'nilai': nilai})
        print(f"Data mahasiswa {nama} (NIM: {nim}) berhasil ditambahkan.")

    def tampilkan(self):
        if not self.daftar_mahasiswa:
            print("Daftar mahasiswa kosong.")
            return
        print("Daftar Mahasiswa:")
        for index, mahasiswa in enumerate(self.daftar_mahasiswa, start=1):
            print(f"{index}. Nama: {mahasiswa['nama']}, NIM: {mahasiswa['nim']}, Nilai: {mahasiswa['nilai']}")

    def hapus(self, nama):
        for mahasiswa in self.daftar_mahasiswa:
            if mahasiswa['nama'] == nama:
                self.daftar_mahasiswa.remove(mahasiswa)
                print(f"Data mahasiswa {nama} berhasil dihapus.")
                return
        print(f"Data mahasiswa {nama} tidak ditemukan.")

    def ubah(self, nama, nim_baru, nilai_baru):
        for mahasiswa in self.daftar_mahasiswa:
            if mahasiswa['nama'] == nama:
                mahasiswa['nim'] = nim_baru
                mahasiswa['nilai'] = nilai_baru
                print(f"Data mahasiswa {nama} berhasil diubah menjadi NIM {nim_baru} dan nilai {nilai_baru}.")
                return
        print(f"Data mahasiswa {nama} tidak ditemukan.")

# Contoh penggunaan
if __name__ == "__main__":
    mhs = Mahasiswa()
    
    while True:
        print("\nMenu:")
        print("1. Tambah Mahasiswa")
        print("2. Tampilkan Mahasiswa")
        print("3. Ubah Mahasiswa")
        print("4. Hapus Mahasiswa")
        print("5. Keluar")
        
        pilihan = input("Pilih menu (1-5): ")
        
        if pilihan == '1':
            nama = input("Masukkan nama mahasiswa: ")
            nim = int(input("Masukkan NIM mahasiswa (angka): "))
            nilai = int(input("Masukkan nilai mahasiswa (angka): "))
            mhs.tambah(nama, nim, nilai)
        
        elif pilihan == '2':
            mhs.tampilkan()
        
        elif pilihan == '3':
            nama = input("Masukkan nama mahasiswa yang ingin diubah: ")
            nim_baru = int(input("Masukkan NIM baru (angka): "))
            nilai_baru = int(input("Masukkan nilai baru (angka): "))
            mhs.ubah(nama, nim_baru, nilai_baru)
        
        elif pilihan == '4':
            nama = input("Masukkan nama mahasiswa yang ingin dihapus: ")
            mhs.hapus(nama)
        
        elif pilihan == '5':
            print("Keluar dari program.")
            break
        
        else:
            print("Pilihan tidak valid. Silakan coba lagi.")

# Penjelasan Python
Berikut adalah penjelasan dari kode program Python yang telah dibuat untuk mengelola data mahasiswa, termasuk penjelasan tentang setiap bagian dari kode tersebut:

**1. Import dan Definisi Kelas**

     def __init__(self):
           self.daftar_mahasiswa = []     
 - class Mahasiswa: Mendefinisikan kelas Mahasiswa yang akan digunakan untuk mengelola data mahasiswa.
 - init: Merupakan metode konstruktor yang dipanggil saat objek dari kelas ini dibuat. Di sini, kita menginisialisasi atribut daftar_mahasiswa sebagai list kosong yang akan 
   menyimpan data mahasiswa.

**2. Method `tambah`**

    self.daftar_mahasiswa.append({'nama': nama, 'nim': nim, 'nilai': nilai})
    print(f"Data mahasiswa {nama} (NIM: {nim}) berhasil ditambahkan.")
 - `tambah(self, nama, nim, nilai)`: Method ini digunakan untuk menambahkan data mahasiswa baru ke dalam daftar.
 - `self.daftar_mahasiswa.append(...)`: Menambahkan dictionary yang berisi nama, nim, dan nilai mahasiswa ke dalam list daftar_mahasiswa.
 - `print(...)`: Menampilkan pesan konfirmasi bahwa data mahasiswa telah berhasil ditambahkan.

**3. Method `tampilkan`**

    if not self.daftar_mahasiswa:
        print("Daftar mahasiswa kosong.")
        return
    print("Daftar Mahasiswa:")
    for index, mahasiswa in enumerate(self.daftar_mahasiswa, start=1):
        print(f"{index}. Nama: {mahasiswa['nama']}, NIM: {mahasiswa['nim']}, Nilai: {mahasiswa['nilai']}")
 - `tampilkan(self)`: Method ini digunakan untuk menampilkan semua data mahasiswa yang ada dalam daftar.
 - `if not self.daftar_mahasiswa:`: Memeriksa apakah daftar mahasiswa kosong. Jika kosong, program akan menampilkan pesan dan keluar dari method.
 - `enumerate(...)`: Menggunakan fungsi enumerate untuk mendapatkan indeks dan data mahasiswa saat iterasi. Indeks dimulai dari 1.
 - `print(...)`: Menampilkan informasi mahasiswa dalam format yang terstruktur.

**4. Method `hapus`**

    for mahasiswa in self.daftar_mahasiswa:
        if mahasiswa['nama'] == nama:
            self.daftar_mahasiswa.remove(mahasiswa)
            print(f"Data mahasiswa {nama} berhasil dihapus.")
            return
    print(f"Data mahasiswa {nama} tidak ditemukan.")
 - `hapus(self, nama)`: Method ini digunakan untuk menghapus data mahasiswa berdasarkan nama.
 - `for mahasiswa in self.daftar_mahasiswa:`: Melakukan iterasi melalui daftar mahasiswa.
 - `if mahasiswa['nama'] == nama`: Memeriksa apakah nama mahasiswa yang ingin dihapus ada dalam daftar.
 - `self.daftar_mahasiswa.remove(mahasiswa)`: Menghapus mahasiswa dari daftar jika ditemukan.
 - `print(...)`: Menampilkan pesan konfirmasi atau pesan bahwa mahasiswa tidak ditemukan.

**5. Method `ubah`**

    for mahasiswa in self.daftar_mahasiswa:
        if mahasiswa['nama'] == nama:
            mahasiswa['nim'] = nim_baru
            mahasiswa['nilai'] = nilai_baru
            print(f"Data mahasiswa {nama} berhasil diubah menjadi NIM {nim_baru} dan nilai {nilai_baru}.")
            return
    print(f"Data mahasiswa {nama} tidak ditemukan.")
 - `ubah(self, nama, nim_baru, nilai_baru)`: Method ini digunakan untuk mengubah data mahasiswa berdasarkan nama.
 - `if mahasiswa['nama'] == nama:`: Memeriksa apakah nama mahasiswa yang ingin diubah ada dalam daftar.
 - `mahasiswa['nim'] = nim_baru dan mahasiswa['nilai'] = nilai_baru`: Mengubah NIM dan nilai mahasiswa yang ditemukan.
 - `print(...)`: Menampilkan pesan konfirmasi atau pesan bahwa mahasiswa tidak ditemukan.

**6. Menu Interaktif**

    mhs = Mahasiswa()
    
    while True:
        print("\nMenu:")
        print("1. Tambah Mahasiswa")
        print("2. Tampilkan Mahasiswa")
        print("3. Ubah Mahasiswa")
        print("4. Hapus Mahasiswa")
        print("5. Keluar")
        
        pilihan = input("Pilih menu (1-5): ")
        
        if pilihan
 - Menu Interaktif :
   - Program menampilkan menu dengan pilihan untuk menambah, menampilkan, mengubah, menghapus siswa, atau keluar dari program.
   - Digunakan `while True` untuk terus menampilkan menu hingga pengguna memilih untuk keluar.
 - Input Pengguna :
   - Menggunakan `input()` untuk mendapatkan pilihan dari pengguna dan data siswa yang ingin ditambahkan, diubah, atau dihapus.
   - Berdasarkan pilihan yang dimasukkan, program akan memanggil metode yang sesuai dari kelas Mahasiswa.

# Tugas Praktikum { Pertemuan ke 13 } <img src=https://logos-download.com/wp-content/uploads/2016/05/MySQL_logo_logotype.png width="130px" >


|**Nama**|**NIM**|**Kelas**|**Matkul**|
|----|---|-----|------|
|NURUL AISYAH|312310476|TI.23.A5|Basis Data|

# Studi Kasus: ERD Karyawan

## Soal Latihan

Sebuah perusahaan ingin membuat sistem untuk pengeloalaan data karyawan pada perusahaan , dengan ketentuan sebagai berikut :

-  Perusahaan tersebut terdiri dari beberapa depatemen yang di pimpin oleh seorang manager (Manajer merupakan bagian dari karyawan).

-  Karyawan bekerja pada salah satu departemen.

-  Karyawan memiliki atasan langsung seorang supervisor.

-  Seorang supervisor dapat membawahi dapat karyawan.

-  Setiap karyawan dari lintas departemen dapat bekerja pada satu project yang sama dalam satu waktu.

-  Setiap karyawan dapat mengerjakan beberapa project yang berbeda.

Buatlah desain databasenya (ER-Diagram), beserta tabel datanya ?

# ERD
![image](https://github.com/nurulaisyah14/TugasPraktikum6/assets/148174512/eb31db05-5f2f-4ba3-8cde-aa3d3c412ce3)


# PENGOLAHAN DATA KARYAWAN
# Tabel Departement

# Di bawah ini merupakan perintah dan juga hasil yang di minta
````
CREATE TABLE Departemen ( IDDepartemen INT PRIMARY KEY, NamaDepartemen VARCHAR(255) );
````
![Screenshot 2024-06-09 205220](https://github.com/nurulaisyah14/TugasPraktikum6/assets/148174512/c396a77d-9218-4779-ac9b-64b4a05c1ce7)


## Tabel Karyawan
### Selanjutnya adalah table karyawan dengan menggunakan perintah seperti di bawah ini beserta hasil

````
CREATE TABLE Karyawan ( IDKaryawan INT PRIMARY KEY, NamaKaryawan VARCHAR(255), IDSupervisor INT, IDDepartemen INT, FOREIGN KEY (IDSupervisor) REFERENCES Karyawan(IDKaryawan), FOREIGN KEY (IDDepartemen) REFERENCES Departemen(IDDepartemen) );
````
![Screenshot 2024-06-09 212324](https://github.com/nurulaisyah14/TugasPraktikum6/assets/148174512/b4626a74-8ab4-4ba3-8f2e-2a5f192d60a2)


## Tabel Proyek
### Kemudian kita akan melanjutkan pada tabel proyek dengan menggunakan perintah sepert di bawah ini beserta hasilnya

````
CREATE TABLE Proyek ( IDProyek INT PRIMARY KEY, NamaProyek VARCHAR(255), TanggalMulai DATE, TanggalSelesai DATE );
````
![Screenshot 2024-06-09 212359](https://github.com/nurulaisyah14/TugasPraktikum6/assets/148174512/06159158-cf4a-4b03-973b-2c7026c1e806)


## Tabel Supervisor
### Kemudian kita akan melanjutkan pada tabel supervisor dengan menggunakan perintah sepert di bawah ini beserta hasilnya

````
CREATE TABLE Supervisor ( IDSupervisor INT, IDDepartemen INT, FOREIGN KEY (IDSupervisor) REFERENCES Karyawan(IDKaryawan), FOREIGN KEY (IDDepartemen) REFERENCES Departemen(IDDepartemen) );
````
![Screenshot 2024-06-09 212437](https://github.com/nurulaisyah14/TugasPraktikum6/assets/148174512/9e671fb1-8cc9-4b9f-9e72-c888cd0588e4)


## Table Partisipasi
### Kemudian kita akan melanjutkan pada tabel partisipasi dengan menggunakan perintah sepert di bawah ini beserta hasilnya

````
CREATE TABLE Partisipasi ( IDKaryawan INT, IDProyek INT, FOREIGN KEY (IDKaryawan) REFERENCES Karyawan(IDKaryawan), FOREIGN KEY (IDProyek) REFERENCES Proyek(IDProyek) );
````
![Screenshot 2024-06-09 212510](https://github.com/nurulaisyah14/TugasPraktikum6/assets/148174512/0a0a3350-80d6-49fc-aa62-ed01ffeeba50)



# UASPBO
Nama Kelompok :

Rendy Fitra Adi Pratama - 1917051041 <br>
Abia Bagas Tufari - 2017051081 <br>
Putri Santika Mayangsari - 2057051011 <br>

Pembagian tugas : <br>
Rendy : membuat FXML Sistem Koperasi Simpan Pinjam <br>
Abia : mengoneksi ke database <br>
Putri : membuat class <br>

Class Diagram :

```mermaid 
classDiagram
    Nasabah <-- Perusahaan
    Nasabah <-- Individu
    Nasabah "1" o--> "1..*" Rekening
    class Nasabah{
      -String nama
      -String alamat
      -ArrayList<Rekening> rekening
      +Nasabah(nama,alamat,rekening)
      +tambahRekening(Rekening rek)
      +print() : void
      <<abstract>>
    }
 
    class Rekening{
      -int noRekening
      -double saldo
      +Rekening(noRekening, saldo)
      +tambahSaldo(double jumlah) : void
      +tarikTunai(double jumlah) :void
    }

    class Perusahaan{
      -String nib
      -int rekeningid
      +Perusahaan(rekeningid,nama,alamat,nib,rekening)
      +print()
    }

    class Individu{
        -Long nik
        -Long npwp
        -int rekeningid
        +Individu(rekeningid,nama,alamat,nik,npwp,rekening)
        +print()
    }
 ```
  
  ER Diagram :
    
  ```mermaid  
  erDiagram
          Nasabah ||--|| Perusahaan : is
          Nasabah ||--|| Individu : is
          Nasabah ||--|{ Rekening : have
          ```

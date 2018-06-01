# LIL MVC (Z-FRAMEWORK)

LIL MVC adalah sebuah konsep MVC menggunakan bahasa pemrograman PHP yang dapat di integrasikan dengan database MySQL


# Installation

git clone https://github.com/hamzahfauzy/lil-mvc

# Path Setting
setting path pada config/path.php
ubah file path sesuai dengan directory lil-mvc diinstall
contoh : di dalam folder htdocs/website
menjadi : define("URL","http://".$_SERVER['SERVER_NAME']."/website");

ubah sitename sesuai dengan kebutuhan


# Database
# Koneksi
untuk mengkoneksikan mvc ke database, buka file config/db-config.php
ubah konfigurasi sesuai dengan koneksi database seperti biasa, dan jangan lupa untuk membuat database MySQL terlebih dahulu

# membuat table dan field
untuk membuat table dan field, buka file database/table.json
format pembuatan table adalah
{
  "table" : [
    {
      "table_name" : "nama_tabel",
      "table_field" : [
        {
          "field_name":"nama_field",
          "field_datatype":"mysql_datatype | "int,varchar,char,text,date,datetime,etc",
          "field_length":field_lentgh | int,
          "field_primary":false | true,
          "field_ai":false | true,
          "field_timestamp":false | true
        },
      ]
    },
  ]
}

catatan : 
1. untuk banyak field, silahkan ulangi konfigurasi berikut
      {
        "field_name":"nama_field",
        "field_datatype":"mysql_datatype | "int,varchar,char,text,date,datetime,etc",
        "field_length":field_lentgh | int,
        "field_primary":false | true,
        "field_ai":false | true,
        "field_timestamp":false | true
      },

2. untuk banyak table silahkan ulangi konfigurasi berikut

    {
      "table_name" : "nama_tabel",
      "table_field" : [
        {
          "field_name":"nama_field",
          "field_datatype":"mysql_datatype | "int,varchar,char,text,date,datetime,etc",
          "field_length":field_lentgh | int,
          "field_primary":false | true,
          "field_ai":false | true,
          "field_timestamp":false | true
        },
      ]
    },
    
# Migration
setelah table dan field dibuat, dapat dilakukan migrasi agar konfigurasi database melakukan pembuatan table dan field pada server MySQL.
untuk melakukan migration dapat dilakukan dengan mengakses http://localhost/{nama_website}/migration

catatan :
1. jika melakukan penambahan atau pengurangan field pada konfigurasi, dan ingin melakukan migration ulang dengan cara mengakses http://localhost/{nama_website}/migration/index?fresh=1


# Generate
generate adalah fitur untuk membuat proses CRUD berdasarkan table dan controller yang di pilih
caranya dengan mengakses http://localhost/{nama_website}/generate
lalu pilih database dan isikan nama controller nya
lalu klik generate

jika berhasil, lihat pada folder controller terdapat controller dengan nama yang di inputkan tadi
pastikan folder set permission ke 0777

Pertanyaan : 
    Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step (bukan hanya sekadar mengikuti tutorial).
1.Membuat projek django:
    Sebelum project django dibuat kita harus menciptakan virtual environment pada folder project yang akan kita gunakan. Hal ini dilakukan untuk mengatur dependencies dan memisahkan default package device kita.
    Untuk menciptakan virtual env langkah-langkahnya sebagai berikut:
    1. buat folder project baru
    2. jalankan python -m venv env (untuk membuat virtualenv baru)
    3. aktifkan virtual env menggunakan command env\Scripts\activate
    3. buat file requirenment.txt yang berisi dependencies yang harus diinstall
    4. lakukan command pip install requirenment untuk menginstall seluruh dependencies yang ada pada file requirenment
    5. jalankan command python manage.py startproject "nama projek" untuk membuat projek baru
2.Membuat aplikasi main pada proyek tersebut
    Pembuatan aplikasi main dapat dilakukan dengan menjalankan 
    1. python manage.py startapp "nama app". Untuk meciptakan app baru
3.Melakukan routing pada proyek agar dapat menjalankan aplikasi main.
    1. daftarkan "nama app" pada INSTALLED_APPS project tersebut
4.Membuat model pada aplikasi main dengan nama Product dan memiliki atribut wajib sebagai berikut.
name
price
description
    untuk menambahkan data dalam model, kita dapat mendefinisikan datafield yang digunakan serta tipe data yang digunakan. contoh 
    name = models.CharField(max_length=255)
    Data dalam model tersebut nantinya akan bisa digunakan dalam template html sehingga data yang ditampilkan sesuai dengan data dalam model. Penambahan dapat dilakukan dengan syntax {{" name "}}
    3. Jika kita menambahkan data baru dalam model, maka perlu dilakukan migrasi sehingga perubahan data yang kita tambahkan dapat teregistrasi.
    command yang dilakukan adalah :
    - python manage.py makemigrations (command ini digunakan untuk meregistrasikan perubahan yang terjadi)
    - python manage.py migrate (command ini digunakan untuk melakukan perubahan yang telah diregistrasi)
5.Membuat sebuah fungsi pada views.py untuk dikembalikan ke dalam sebuah template HTML yang menampilkan nama aplikasi serta nama dan kelas kamu.
    1. Routing dilakukan dengan meninclude path pada views.py yang merender template dari main.html. Hal ini dilakukan dengan menambahkan command
    path('', show_main, name='show_main') pada url pattern app.
6.Membuat sebuah routing pada urls.py aplikasi main untuk memetakan fungsi yang telah dibuat pada views.py.
    1. agar url app kita teregistrasi dalam url projek dan views.py dapat ditampilkan, maka url pada app perlu di include kedalam url project dengan menambahkan command path('', include('main.urls')) dalam url pattern projek
7.Melakukan deployment ke PWS terhadap aplikasi yang sudah dibuat sehingga nantinya dapat diakses oleh teman-temanmu melalui Internet.
    Agar web yang kita buat dapat diakses dapat dilihat oleh orang lain dan tidak hanya berada dalam local host saja, maka kita perlu melakukan deployment pada server. Hal ini ini dilakukan dengan mengubah ALLOWED_HOST menjadi url deployment pws.
    ALLOWED_HOSTS = ["localhost", "127.0.0.1", "url deployment pws"]
8.Jelaskan fungsi git dalam pengembangan perangkat lunak!
    Git merupaka sistem kontrol versi yang bermanfaat untuk melakukan kolaborasi dalam proses pengembangan perangkat lunak. Beberapa manfaatnya adalah sebagai berikut
    1. Melacak perubahan kode (riwayat perubahaan kode)
    2. Kolaborasi (git memungkinkan developer untuk bekerja secara bersamaan)
    3. manajemen konflik (git membantu mengelola konflik yang terjadi saat 2 developer melakukan perubahan)
    4. Penyimpanan (git menyimpan repositori kita secara lengkap beserta riwayatnya)
9.Menurut Anda, dari semua framework yang ada, mengapa framework Django dijadikan permulaan pembelajaran pengembangan perangkat lunak?
    Framework django telah memiliki resource pembelajaran yang banyak di internet. Django juga memudahkan developer dalam membuat web karena menyediakan automasi sesuai dengan prinsipnya D.R.Y (Don't Repeat Yourself).
10.Mengapa model pada Django disebut sebagai ORM?
    Model Django disebut sebagai ORM karena django mengimplementasikan teknik Object-Relational Mapping, yang menghubungkan objek Python dengan tabel basis data relasional. Django juga menyediakan API untuk melakukan operasi basis data. Dengan ORM, developer dapat fokus pada logika aplikasi tanpa harus memikirkan detail SQL.
# MENGAKSES COMMAND LINE

## INTRODUCTION TO THE BASH SHELL

Baris perintah adalah antarmuka berbasis teks yang dapat digunakan untuk memasukkan instruksi ke sistem komputer. Baris perintah Linux disediakan oleh program yang disebut shell. Berbagai pilihan untuk program shell telah dikembangkan selama bertahun-tahun, dan pengguna yang berbeda dapat dikonfigurasi untuk menggunakan shell yang berbeda. Namun, sebagian besar pengguna tetap menggunakan default saat ini.

Shell default untuk pengguna di Red Hat Enterprise Linux adalah GNU Bourne-Again Shell (bash) . Bash adalah versi perbaikan dari salah satu shell paling sukses yang digunakan pada sistem mirip UNIX, Bourne Shell (sh).

Ketika shell digunakan secara interaktif, shell akan menampilkan string ketika menunggu perintah dari pengguna. Ini disebut prompt shell. Ketika pengguna biasa memulai shell, prompt default diakhiri dengan $karakter, seperti yang ditunjukkan di bawah ini.

<pre>[user@host ~]$</pre>
Karakter $diganti dengan #karakter jika shell berjalan sebagai superuser, root. Ini membuatnya lebih jelas bahwa itu adalah cangkang superuser, yang membantu menghindari kecelakaan dan kesalahan yang dapat memengaruhi keseluruhan sistem. Prompt shell superuser ditunjukkan di bawah ini.

<pre>[root@host ~]#</pre>
Menggunakan bashuntuk menjalankan perintah bisa sangat kuat. Shell bashmenyediakan bahasa skrip yang dapat mendukung otomatisasi tugas. Shell memiliki kemampuan tambahan yang dapat menyederhanakan atau memungkinkan operasi yang sulit dilakukan secara efisien dengan alat grafis.

### CATATAN

Shell bashmemiliki konsep yang mirip dengan interpreter baris perintah yang ditemukan di versi terbaru Microsoft Windows, cmd.exe, meskipun bashmemiliki bahasa skrip yang lebih canggih. Ini juga mirip dengan Windows PowerShell di Windows 7 dan Windows Server 2008 R2 dan yang lebih baru. Administrator yang menggunakan Apple Mac yang menggunakan Terminalutilitas mungkin senang untuk mencatat bahwa itu bashadalah shell default di macOS.

## SHELL BASICS
Perintah yang dimasukkan pada prompt shell memiliki tiga bagian dasar:

<li>Perintah untuk menjalankan</li>
<li>Opsi untuk menyesuaikan perilaku perintah</li>
<li>Argumen, yang biasanya menjadi target perintah</li>

Perintah adalah nama program yang akan dijalankan. Ini mungkin diikuti oleh satu atau lebih opsi, yang menyesuaikan perilaku perintah atau apa yang akan dilakukannya. Opsi biasanya dimulai dengan satu atau dua tanda hubung ( ```-a ```atau ```--all```, misalnya) untuk membedakannya dari argumen. Perintah juga dapat diikuti oleh satu atau lebih argumen, yang sering menunjukkan target yang harus dijalankan oleh perintah tersebut. Misalnya, perintah usermod ```-L``` user01memiliki perintah ```( usermod)```, opsi ```( -L)```, dan argumen ```( user01)```. Efek dari perintah ini adalah mengunci kata sandi user01 akun pengguna.

## LOGGING IN TO A LOCAL COMPUTER
Untuk menjalankan shell, Anda harus masuk ke komputer di terminal. Terminal adalah antarmuka berbasis teks yang digunakan untuk memasukkan perintah ke dalam dan mencetak keluaran dari sistem komputer. Ada beberapa cara untuk melakukan ini.

Komputer mungkin memiliki keyboard dan layar perangkat keras untuk input dan output yang terhubung langsung dengannya. Ini adalah konsol fisik mesin Linux. Konsol fisik mendukung beberapa konsol virtual, yang dapat menjalankan terminal terpisah. Setiap konsol virtual mendukung sesi login independen. Anda dapat beralih di antara mereka dengan menekan ```Ctrl+Alt``` dan tombol fungsi ( ```F1```melalui ```F6```) secara bersamaan. Sebagian besar konsol virtual ini menjalankan terminal yang menyediakan prompt login teks, dan jika Anda memasukkan nama pengguna dan kata sandi dengan benar, Anda akan masuk dan mendapatkan prompt shell.

Komputer mungkin menyediakan prompt login grafis di salah satu konsol virtual. Anda dapat menggunakan ini untuk masuk ke lingkungan grafis. Lingkungan grafis juga berjalan pada konsol virtual. Untuk mendapatkan prompt shell Anda harus memulai program terminal di lingkungan grafis. Prompt shell disediakan di jendela aplikasi program terminal grafis Anda.

### CATATAN

Banyak administrator sistem memilih untuk tidak menjalankan lingkungan grafis di server mereka. Hal ini memungkinkan sumber daya yang akan digunakan oleh lingkungan grafis untuk digunakan oleh layanan server sebagai gantinya.

Di Red Hat Enterprise Linux 8, jika lingkungan grafis tersedia, layar login akan berjalan di konsol virtual pertama, yang disebut tty1. Lima petunjuk masuk teks tambahan tersedia di konsol virtual dua sampai enam.

Jika Anda masuk menggunakan layar masuk grafis, lingkungan grafis Anda akan dimulai pada konsol virtual pertama yang saat ini tidak digunakan oleh sesi masuk. Biasanya, sesi grafis Anda akan menggantikan prompt login di konsol virtual kedua ( tty2). Namun, jika konsol tersebut digunakan oleh sesi login teks aktif (bukan hanya prompt login), konsol virtual gratis berikutnya digunakan sebagai gantinya.

Layar login grafis terus berjalan pada konsol virtual pertama (```tty1```). Jika Anda sudah masuk ke sesi grafis, dan masuk sebagai pengguna lain di layar masuk grafis atau menggunakan ```Switch User``` item menu untuk mengalihkan pengguna di lingkungan grafis tanpa keluar, lingkungan grafis lain akan dimulai untuk pengguna itu di hari berikutnya. konsol virtual gratis. Ketika Anda keluar dari lingkungan grafis, itu akan keluar dan konsol fisik akan secara otomatis beralih kembali ke layar login grafis pada konsol virtual pertama.

### CATATAN

Di Red Hat Enterprise Linux 6 dan 7, layar login grafis berjalan di konsol virtual pertama, tetapi ketika Anda masuk ke lingkungan grafis awal Anda menggantikan layar login di konsol virtual pertama, bukan memulai di konsol virtual baru.

Di Red Hat Enterprise Linux 5 dan sebelumnya, enam konsol virtual pertama selalu menyediakan perintah login teks. Jika lingkungan grafis berjalan, itu ada di konsol virtual tujuh (diakses melalui ```Ctrl+Alt+F7```).

Server tanpa kepala tidak memiliki keyboard dan layar yang terhubung secara permanen. Pusat data dapat diisi dengan banyak rak server tanpa kepala, dan tidak menyediakan masing-masing dengan keyboard dan tampilan akan menghemat ruang dan biaya. Untuk mengizinkan administrator masuk, server tanpa kepala mungkin memiliki prompt masuk yang disediakan oleh konsol serialnya, berjalan pada port serial yang terhubung ke server konsol jaringan untuk akses jarak jauh ke konsol serial.

Konsol serial biasanya digunakan untuk memperbaiki server jika kartu jaringannya salah dikonfigurasi dan masuk melalui koneksi jaringannya sendiri menjadi tidak mungkin. Namun, sebagian besar waktu, server tanpa kepala diakses dengan cara lain melalui jaringan.

## LOGGING IN OVER THE NETWORK
Pengguna dan administrator Linux sering kali perlu mendapatkan akses shell ke sistem jarak jauh dengan menghubungkannya melalui jaringan. Dalam lingkungan komputasi modern, banyak server tanpa kepala sebenarnya adalah mesin virtual atau dijalankan sebagai instance cloud publik atau pribadi. Sistem ini tidak fisik dan tidak memiliki konsol perangkat keras nyata. Mereka bahkan mungkin tidak menyediakan akses ke konsol fisik (simulasi) atau konsol serial mereka.

Di Linux, cara paling umum untuk mendapatkan prompt shell pada sistem jarak jauh adalah dengan menggunakan Secure Shell (```SSH```). Sebagian besar sistem Linux (termasuk Red Hat Enterprise Linux) dan macOS menyediakan OpenSSHprogram baris perintah sshuntuk tujuan ini.

Dalam contoh ini, pengguna dengan prompt shell di host mesin digunakan sshuntuk masuk ke sistem Linux jarak jauh ```remotehost``` sebagai pengguna ```remoteuser```:

<pre>[user@host ~]$ ssh remoteuser@remotehost
remoteuser@remotehost's password: password
[remoteuser@remotehost ~]$</pre>

Perintah ```ssh``` mengenkripsi koneksi untuk mengamankan komunikasi terhadap penyadapan atau pembajakan kata sandi dan konten.

Beberapa sistem (seperti instans cloud baru) tidak mengizinkan pengguna menggunakan kata sandi untuk masuk sshdemi keamanan yang lebih ketat. Cara alternatif untuk mengautentikasi ke mesin jarak jauh tanpa memasukkan kata sandi adalah melalui autentikasi kunci publik.

Dengan metode otentikasi ini, pengguna memiliki file identitas khusus yang berisi kunci pribadi, yang setara dengan kata sandi, dan yang mereka rahasiakan. Akun mereka di server dikonfigurasi dengan kunci publik yang cocok, yang tidak harus dirahasiakan. Saat masuk, pengguna dapat mengonfigurasi sshuntuk memberikan kunci pribadi dan jika kunci publik yang cocok dipasang di akun itu di server jarak jauh, itu akan membuat mereka masuk tanpa meminta kata sandi.

Pada contoh berikutnya, pengguna dengan prompt shell di host mesin masuk remotehost sebagai remoteuserusing ssh, menggunakan otentikasi kunci publik. Opsi -iini digunakan untuk menentukan file kunci pribadi pengguna, yaitu ```mylab.pem```. Kunci publik yang cocok sudah disiapkan sebagai kunci resmi di akun pengguna jarak jauh.

<pre>[user@host ~]$ ssh -i mylab.pem remoteuser@remotehost
[remoteuser@remotehost ~]$</pre>

Agar ini berfungsi, file kunci pribadi harus hanya dapat dibaca oleh pengguna yang memiliki file tersebut. Dalam contoh sebelumnya, di mana kunci pribadi berada dalam ```mylab.pem``` file, perintah ```chmod 600 mylab.pem``` dapat digunakan untuk memastikan hal ini. Cara mengatur hak akses file dibahas secara lebih rinci di bab selanjutnya.

Pengguna mungkin juga memiliki kunci pribadi yang dikonfigurasi yang dicoba secara otomatis, tetapi diskusi itu berada di luar cakupan bagian ini. Referensi di akhir bagian ini berisi tautan ke informasi lebih lanjut tentang topik ini.

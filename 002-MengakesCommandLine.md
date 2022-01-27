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

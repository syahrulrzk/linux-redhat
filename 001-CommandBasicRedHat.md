
subscription terlebih dahulu

<pre>subscription-manager register</pre>

Daftar dan otomatis berlangganan dalam satu langkah
Gunakan perintah berikut untuk mendaftarkan sistem, lalu secara otomatis mengaitkan langganan apa pun yang tersedia yang cocok dengan sistem itu:

Mentah
<pre># subscription-manager register --username <username> --password <password> --auto-attach</pre>

cara menampil alamat ip
<pre> nmcli d show</pre>

cara melihat daftar <b>subscripton-manager</b>
<pre>subscription-manager list --available</pre>

melakukan attach atau subscription ke pada repositori
<pre>subscription-manager attach --auto</pre>

melihat daftar subscription yang telah kita daftarkan
<pre>subscription-manager list --consumed</pre>

klo perintah diatas sudah dijalankan, sekarang kita akan melihat updatenya terdahulu.
<pre>yum check-update</pre>

sekarang kita tinggal update
<pre>yum update</pre>

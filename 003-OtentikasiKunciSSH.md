# MENGONFIGURASI Otentikasi BERBASIS KUNCI SSH
## SSH KEY-BASED AUTHENTICATION
Anda dapat mengonfigurasi server SSH untuk memungkinkan Anda mengautentikasi tanpa kata sandi dengan menggunakan autentikasi berbasis kunci. Ini didasarkan pada skema kunci privat-publik. Untuk melakukannya, Anda membuat sepasang file kunci kriptografi yang cocok. Salah satunya adalah kunci pribadi, yang lain cocok dengan kunci publik. File kunci pribadi digunakan sebagai kredensial otentikasi dan, seperti kata sandi, harus dirahasiakan dan aman.

Kunci publik disalin ke sistem yang ingin disambungkan pengguna, dan digunakan untuk memverifikasi kunci pribadi. Kunci publik tidak perlu dirahasiakan. Anda meletakkan salinan kunci publik di akun Anda di server. Saat Anda mencoba masuk, server SSH dapat menggunakan kunci publik untuk mengeluarkan tantangan yang hanya dapat dijawab dengan benar menggunakan kunci pribadi.

Akibatnya, klien ssh Anda dapat secara otomatis mengotentikasi login Anda ke server dengan salinan unik kunci pribadi Anda. Ini memungkinkan Anda untuk mengakses sistem dengan aman dengan cara yang tidak mengharuskan Anda memasukkan kata sandi secara interaktif setiap saat.

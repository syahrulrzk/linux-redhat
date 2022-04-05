Redhat OpenStack Platform 16.2

Rilis Red Hat OpenStack Platform ini didasarkan pada rilis OpenStack "Train". Ini mencakup fitur tambahan, masalah yang diketahui, dan masalah yang diselesaikan khusus untuk Red Hat OpenStack Platform.

RHOSP adalah platform komputasi awan yang memvirtualisasikan sumber daya dari perangkat keras standar industri, mengatur sumber daya tersebut ke dalam cloud, dan mengelolanya sehingga pengguna dapat mengakses apa yang mereka butuhkan—saat mereka membutuhkannya.

1. INTRODUCTION TO DIRECTOR
Direktur Red Hat OpenStack Platform (RHOSP) adalah perangkat untuk menginstal dan mengelola lingkungan RHOSP yang lengkap.  Direktur didasarkan terutama pada proyek OpenStack TripleO. Dengan direktur, Anda dapat menginstal lingkungan RHOSP yang beroperasi penuh, ramping, dan kuat yang dapat menyediakan dan mengontrol sistem bare metal untuk digunakan sebagai node OpenStack.
Direkturmenggunakan dua konsep utama: undercloud dan overcloud. Pertama Anda menginstal undercloud, dan kemudian menggunakan undercloud sebagai alat untuk menginstal dan mengkonfigurasi overcloud.

1.1 UnderCLoud

Undercloud adalah node manajemen utama yang berisi toolset direktur Red Hat OpenStack Platform. Ini adalah instalasi OpenStack sistem tunggal yang mencakup komponen untuk menyediakan dan mengelola node OpenStack yang membentuk lingkungan OpenStack Anda (overcloud). Komponen yang membentuk undercloud memiliki beberapa fungsi:

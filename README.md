### [Commit Pertama]

Proyek yang saya kerjakan terkait dengan implementasi sederhana dari penggunaan TcpListener dan penanganan koneksi TCP dalam bahasa pemrograman Rust./n Pada code pertama, saya membuat sebuah TcpListener yang akan mendengarkan koneksi di alamat 127.0.0.1:7878. Setiap kali ada koneksi masuk, pesan "Connection established!" akan ditampilkan di konsol. Code ini merupakan langkah awal dalam membangun aplikasi server yang dapat menerima koneksi TCP.

Selanjutnya, pada code kedua, Saya menambahkan fungsi handle_connection untuk menangani koneksi yang masuk ke server TCP saya. Di dalam fungsi ini, Saya menggunakan BufReader untuk membaca data dari koneksi TCP dan mengumpulkan permintaan HTTP yang masuk. Permintaan HTTP tersebut kemudian dicetak ke konsol untuk dianalisis. Dengan menambahkan fungsi penanganan koneksi seperti ini, proyek saya menjadi lebih lengkap dengan kemampuan untuk memproses data yang diterima dari klien secara lebih terstruktur.







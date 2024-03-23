### [Commit Pertama]

Proyek yang saya kerjakan terkait dengan implementasi sederhana dari penggunaan TcpListener dan penanganan koneksi TCP dalam bahasa pemrograman Rust./n Pada code pertama, saya membuat sebuah TcpListener yang akan mendengarkan koneksi di alamat 127.0.0.1:7878. Setiap kali ada koneksi masuk, pesan "Connection established!" akan ditampilkan di konsol. Code ini merupakan langkah awal dalam membangun aplikasi server yang dapat menerima koneksi TCP.

Selanjutnya, pada code kedua, Saya menambahkan fungsi handle_connection untuk menangani koneksi yang masuk ke server TCP saya. Di dalam fungsi ini, Saya menggunakan BufReader untuk membaca data dari koneksi TCP dan mengumpulkan permintaan HTTP yang masuk. Permintaan HTTP tersebut kemudian dicetak ke konsol untuk dianalisis. Dengan menambahkan fungsi penanganan koneksi seperti ini, proyek saya menjadi lebih lengkap dengan kemampuan untuk memproses data yang diterima dari klien secara lebih terstruktur.


### [Commit Kedua]
<img width="960" alt="image" src="https://github.com/failasuf123/advprog-modul6/assets/97381822/f868f5f5-7a66-406a-9351-e04f231dbafc">

- Penanganan Request HTTP:
Saya menambahkan logika untuk menangani permintaan HTTP yang masuk dengan cara yang lebih terstruktur. Pada kode sebelumnya, tidak terlihat adanya pengolahan dari request yang masuk, sedangkan pada kode yang baru, Saya menggunakan BufReader untuk membaca request line by line dan mengumpulkan request tersebut ke dalam Vec<_>.

- Pengiriman Respons HTTP:
Saya telah menambahkan logika untuk mengirim respons HTTP yang valid kepada klien. Dalam kode sebelumnya, hanya mencetak pesan "Connection established!" di konsol tanpa mengirim respons apa pun. Pada kode yang baru, Saya menggunakan fs::read_to_string untuk membaca konten dari file "hello.html" dan kemudian membangun respons HTTP yang terdiri dari header status "HTTP/1.1 200 OK", header "Content-Length" yang sesuai dengan panjang konten HTML, dan konten HTML dari file "hello.html".

- Penanganan Stream:
Saya menggunakan stream.write_all(response.as_bytes()) untuk mengirimkan respons HTTP ke klien. Pada kode sebelumnya, tidak terlihat bagaimana respons dikirimkan kembali ke klien setelah request ditangani.


### [Commit Ketiga]
<img width="927" alt="image" src="https://github.com/failasuf123/advprog-modul6/assets/97381822/32010875-65be-42d3-b476-49444d0373c7">

- Pemisahan Penanganan Respons:
  
 Pada implementasi awal, kode untuk menangani koneksi TCP dan menghasilkan respons HTTP digabungkan dalam satu fungsi (handle_connection). Pendekatan ini berfungsi dengan baik untuk 
 contoh dasar namun dapat menjadi sulit dipelihara ketika kode berkembang. Oleh karena itu, saya memutuskan untuk memisahkan logika penanganan respons ke dalam fungsi tersendiri.
 Dengan memisahkan kode penanganan respons ke dalam fungsi terpisah (generate_response), saya mencapai organisasi kode yang lebih baik dan meningkatkan keterbacaan. Sekarang, fungsi 
 handle_connection fokus hanya pada mengelola aliran TCP dan routing permintaan, sementara fungsi generate_response menangani pembuatan respons HTTP berdasarkan permintaan yang masuk.

- Alasan Refaktorisasi:
  
 Alasan utama untuk melakukan refaktorisasi adalah untuk mematuhi Prinsip Tanggung Jawab Tunggal (Single Responsibility Principle/SRP) dalam desain perangkat lunak. SRP menyarankan bahwa 
 sebuah fungsi atau modul seharusnya hanya memiliki satu alasan untuk berubah, yang menghasilkan basis kode yang lebih mudah dipelihara dan ditingkatkan. Dengan memisahkan logika 
 penanganan respons, saya mengisolasi tanggung jawab masing-masing fungsi, membuatnya lebih mudah dipahami, diuji, dan dimodifikasi secara independen.
 Selain itu, refaktorisasi memungkinkan saya untuk meningkatkan struktur keseluruhan kode dan menghilangkan blok kode yang redundan atau tidak diperlukan. Hal ini tidak hanya meningkatkan 
 keterpeliharaan kode tetapi juga mendorong penggunaan kode yang lebih baik dan modularitas, yang sangat penting untuk pengembangan proyek jangka panjang.



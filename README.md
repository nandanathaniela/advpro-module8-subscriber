# Module 8 Subscriber

#### Nanda Nathaniela Meizari - 2206824136

### *what is amqp?*
AMQP adalah singkatan dari Advanced Message Queuing Protocol, sebuah open standard application layer protocol untuk message-oriented middleware. Tujuan AMQP adalah untuk komunikasi yang aman serta operasi asinkron antara software components yang berbeda.

Di dalam konteks kode, AMQP berfungsi sebagai penghubung antar aplikasi dengan sistem yang diawasi oleh CrosstownBus. Aplikasi ini mampu mengirim dan menerima pesan melalui antrian yang terkoneksi dengan broke AMQP, yang dioperasikan lokal pada port 5672

### *What does guest:guest@localhost:5672 mean? what is the first guest, and what is the second guest, and what is localhost:5672 is for?*
`guest:guest@localhost:5672` mengindikasikan URI koneksi yang menggunakan format `<pengguna>:<kata sandi>@<host>:<port>`:

1. `guest` pertama menunjukkan nama pengguna yang digunakan untuk autentikasi pada server RabbitMQ, dan `guest` seringkali merupakan nama pengguna bawaan
2. `guest` kedua mewakili kata sandi pengguna. Pada RabbitMQ, kata sandi standar juga umumnya adalah `guest`
3. `localhost:5672` adalah nama host dan nomor port yang digunakan oleh broker AMQP. Di sini, `localhost` berarti broker AMQP dijalankan di mesin yang sama dengan kode, dan `5672` adalah port bawaan yang digunakan untuk komunikasi AMQP

## Simulation slow subscriber
![Simulation slow subscriber](assets/images/Simulation%20slow%20subscriber.jpg)
Gambar tersebut menunjukkan bahwa Subscriber mengalami keterlambatan dalam menerima data dari message broker, dengan setiap proses mengalami delay selama satu detik. Pesan-pesan yang di-queue pada message broker akan terus bertambah seiring dengan peningkatan delay, karena Publisher akan lebih cepat daripada Subscriber dalam menerima data. Jumlah total pesan yang di-queue pada komputer saya adalah 16 setelah menjalankan 5 kali perintah cargo run di Publisher
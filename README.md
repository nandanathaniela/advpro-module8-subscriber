*what is amqp?*
AMQP adalah singkatan dari Advanced Message Queuing Protocol, sebuah open standard application layer protocol untuk message-oriented middleware. Tujuan AMQP adalah untuk komunikasi yang aman serta operasi asinkron antara software components yang berbeda.

Di dalam konteks kode, AMQP berfungsi sebagai penghubung antar aplikasi dengan sistem yang diawasi oleh CrosstownBus. Aplikasi ini mampu mengirim dan menerima pesan melalui antrian yang terkoneksi dengan broke AMQP, yang dioperasikan lokal pada port 5672

*What does guest:guest@localhost:5672 mean? what is the first guest, and what is the second guest, and what is localhost:5672 is for?*
`guest:guest@localhost:5672` mengindikasikan URI koneksi yang menggunakan format `<pengguna>:<kata sandi>@<host>:<port>`:

1. `guest` pertama menunjukkan nama pengguna yang digunakan untuk autentikasi pada server RabbitMQ, dan `guest` seringkali merupakan nama pengguna bawaan
2. `guest` kedua mewakili kata sandi pengguna. Pada RabbitMQ, kata sandi standar juga umumnya adalah `guest`
3. `localhost:5672` adalah nama host dan nomor port yang digunakan oleh broker AMQP. Di sini, `localhost` berarti broker AMQP dijalankan di mesin yang sama dengan kode, dan `5672` adalah port bawaan yang digunakan untuk komunikasi AMQP
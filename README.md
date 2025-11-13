# Praktikum8

Project Modul 8 - Navigasi & Mengirim Data (Arguments)

📖 Deskripsi

Project ini adalah kelanjutan dari Modul 7 (Navigasi). Fokus utama modul ini adalah mempelajari cara mengirim data dari halaman pertama ke halaman kedua saat navigasi terjadi.

Anda akan belajar cara membungkus data (misalnya, judul dan pesan) ke dalam sebuah class (disebut ScreenArguments), mengirim class tersebut sebagai arguments saat memanggil Navigator.pushNamed(), dan kemudian menerima serta menampilkan data tersebut di halaman tujuan.

🎯 Tujuan Utama Project

Membuat Model Data: Mampu membuat class sederhana (ScreenArguments) untuk membungkus data yang ingin dikirim.

Mengirim Data: Mampu mengirimkan data (objek ScreenArguments) menggunakan properti arguments pada Navigator.pushNamed().

Menerima Data: Mampu mengambil dan mem-parsing data yang dikirim di halaman tujuan menggunakan ModalRoute.of(context)!.settings.arguments.

Menampilkan Data: Menampilkan data yang telah diterima ke dalam UI (misalnya, di AppBar dan body halaman tujuan).

✅ Daftar Tugas (To-Do List)

Berikut adalah hal-hal yang harus Anda kerjakan berdasarkan modul:

Buat Project Baru:

[ ] Buat "New Flutter Project" dengan nama demo_navigasi_namedroute.

Buat Struktur File:

[ ] Buat 3 file baru di dalam lib/:

home.dart (untuk halaman utama)

tujuan.dart (untuk halaman tujuan)

screen_arguments.dart (untuk class model data)

Buat Class ScreenArguments (screen_arguments.dart):

[ ] Buat sebuah class bernama ScreenArguments.

[ ] Tambahkan dua properti final String di dalamnya: title dan message.

[ ] Buat constructor untuk class ini: ScreenArguments(this.title, this.message);

Konfigurasi main.dart (File Utama):

[ ] import ketiga file yang baru Anda buat.

[ ] Di dalam MaterialApp, atur initialRoute ke /.

[ ] Definisikan routes:

routes: {
  '/': (context) => HalamanUtama(),
  '/tujuan': (context) => HalamanTujuan(),
},


Kode Halaman Utama (home.dart):

[ ] Buat StatelessWidget bernama HalamanUtama.

[ ] Buat sebuah tombol (misal: ElevatedButton) dengan teks "Pindah & Kirim Data".

[ ] Di dalam onPressed tombol, panggil Navigator.pushNamed() sambil mengirimkan data:

Navigator.pushNamed(
  context,
  '/tujuan',
  arguments: ScreenArguments(
    'Ini Judul dari Home',
    'Ini Pesan yang dikirim dari Home.',
  ),
);


Kode Halaman Tujuan (tujuan.dart):

[ ] Buat StatelessWidget bernama HalamanTujuan.

[ ] Di dalam method build, ambil data arguments terlebih dahulu:

final args = ModalRoute.of(context)!.settings.arguments as ScreenArguments;


[ ] Di dalam Scaffold, gunakan data args yang sudah diambil:

AppBar: Gunakan args.title sebagai title AppBar.

body: Tampilkan args.message di tengah layar menggunakan Center dan Text.

[ ] Tambahkan juga sebuah tombol "Kembali" yang memanggil Navigator.pop(context).

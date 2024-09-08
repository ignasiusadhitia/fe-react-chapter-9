# Fetch Eksternal Data Menggunakan JavaScript DOM

Proyek ini menjelaskan cara menggunakan **Fetch API** untuk mengambil data dari sumber eksternal (API) dan menampilkannya di halaman web menggunakan JavaScript DOM. Ini adalah teknik yang umum digunakan untuk mendapatkan data secara dinamis dari server dan menampilkannya secara real-time.

## Pengenalan dengan API

**Application Programming Interface (API)** adalah mekanisme yang memungkinkan dua aplikasi atau sistem untuk saling berkomunikasi dan bertukar data. Contohnya, saat menggunakan aplikasi cuaca di ponsel, aplikasi tersebut mengambil data cuaca dari server melalui API.

### REST API

**REST API** adalah salah satu jenis API yang mengikuti prinsip **Representational State Transfer (REST)**. API ini menggunakan metode HTTP seperti:

- **GET**: Untuk mengambil data dari server.
- **POST**: Untuk mengirim data baru ke server.
- **PUT**: Untuk memperbarui data yang ada di server.
- **DELETE**: Untuk menghapus data dari server.

REST API biasanya beroperasi dengan sumber daya (resources) yang diidentifikasi oleh URL. Misalnya, URL untuk mendapatkan data pengguna mungkin berupa `https://example.com/users`.

## Fetch API

**Fetch API** adalah antarmuka modern yang digunakan di JavaScript untuk melakukan permintaan HTTP ke server, seperti mengambil data (GET) atau mengirim data (POST). `fetch()` mengembalikan **Promise** yang memungkinkan kita untuk menangani operasi asinkron.

### Contoh Penggunaan Fetch API

Pada contoh ini, kita menggunakan **Fetch API** untuk mengambil data dari URL `https://jsonplaceholder.typicode.com/posts`. Hasil dari permintaan ini kemudian ditampilkan di halaman sebagai daftar:

```javascript
fetch("https://jsonplaceholder.typicode.com/posts")
  .then((response) => response.json()) // Mengubah respons menjadi JSON
  .then((data) => {
    const dataList = document.getElementById("dataList");
    data.forEach((item) => {
      const listItem = document.createElement("li");
      listItem.textContent = `ID: ${item.id} Title: ${item.title}`;
      dataList.appendChild(listItem);
    });
  })
  .catch((err) => console.error("Error:", err));
```

### Penjelasan Kode

- `fetch()`: Memulai permintaan HTTP ke URL API eksternal.
- `response.json()`: Mengubah respons yang didapat menjadi format JSON.
- `then()`: Fungsi ini akan dijalankan jika permintaan berhasil. Data yang didapatkan kemudian ditampilkan di halaman menggunakan DOM.
- `catch()`: Menangani kesalahan (error) jika permintaan gagal, dan menampilkannya di konsol.

## Status HTTP

Saat menggunakan Fetch API, penting untuk memahami kode status HTTP yang mengindikasikan hasil dari permintaan. Berikut beberapa kode status yang umum:

- `200 OK`: Permintaan berhasil, dan data dikembalikan.
- `400 Bad Request`: Permintaan tidak valid atau salah format.
- `401 Unauthorized`: Pengguna tidak memiliki izin untuk mengakses sumber daya.
- `404 Not Found`: Sumber daya tidak ditemukan di server.
- `500 Internal Server Error`: Terjadi kesalahan di sisi server.

## Validasi Form di Frontend

Selain Fetch API, penting juga untuk memvalidasi input pengguna sebelum mengirim permintaan ke server. Contoh atribut HTML yang digunakan untuk validasi:

- `required`: Menandakan bahwa input wajib diisi.
- `type="email"`: Memastikan input berisi alamat email yang valid.
- `minlength/maxlength`: Menetapkan panjang minimal atau maksimal input teks.

## Kesimpulan

Dengan **Fetch API**, JavaScript memudahkan pengambilan data dari server secara asinkron tanpa perlu memuat ulang halaman. Teknik ini sangat penting dalam membangun aplikasi web modern yang dinamis dan responsif.

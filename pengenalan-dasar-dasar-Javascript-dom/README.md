# Pengenalan & Dasar-dasar JavaScript DOM

Proyek ini memperkenalkan konsep dasar **Document Object Model (DOM)** dalam JavaScript, yang memungkinkan Anda untuk memanipulasi konten, struktur, dan gaya dari elemen-elemen dalam halaman web. Berikut adalah penjelasan mengenai kode yang digunakan dalam proyek ini.

## Apa Itu DOM?

**Document Object Model (DOM)** adalah representasi objek dari dokumen HTML. DOM memungkinkan JavaScript untuk mengakses dan memanipulasi elemen-elemen dalam halaman web, sehingga memungkinkan kita untuk membuat halaman web lebih interaktif.

## Mengakses Elemen DOM

Ada beberapa cara untuk mengakses elemen-elemen dalam DOM:

1. **getElementById()**: Mengakses elemen berdasarkan ID.
   ```javascript
   const title = document.getElementById("title");
   console.log(title.textContent); // Output: "Selamat Datang di Lumoshive Academy!"
   ```
2. **getElementsByClassName()**: Mengakses elemen berdasarkan class.
   ```javascript
   const paragraphs = document.getElementsByClassName("content");
   console.log(paragraphs[0].textContent); // Output: "Ini adalah paragraf pertama."
   ```
3. **querySelector()**`: Mengakses elemen pertama yang cocok dengan selector CSS.
   ```javascript
   const firstParagraph = document.querySelector(".content");
   console.log(firstParagraph.textContent); // Output: "Ini adalah paragraf pertama."
   ```
4. **querySelectorAll()**: Mengakses semua elemen yang cocok dengan selector CSS.
   ```javascript
   const allParagraphs = document.querySelectorAll(".content");
   console.log(allParagraphs[1].textContent); // Output: "Ini adalah paragraf kedua."
   ```

## Memanipulasi Elemen DOM

Setelah elemen DOM diakses, kita dapat memanipulasinya dengan berbagai cara:

1. **Mengubah konten elemen:**:
   ```javascript
   title.textContent = "Hello Lumoshive!";
   ```
2. **Mengubah atribut elemen:**
   ```javascript
   title.setAttribute("style", "color: red;");
   title.setAttribute("class", "font-weight-bold");
   ```
3. **Mengubah gaya elemen secara langsung:**
   ```javascript
   title.style.fontSize = "24px";
   ```

## Menambahkan dan Menghapus Elemen dari DOM

Kita juga bisa menambahkan atau menghapus elemen dari halaman web secara dinamis:

1. **Menambahkan elemen baru:**
   ```javascript
   const newTitle = document.createElement("h2");
   newTitle.textContent = "Selamat Belajar DOM!";
   document.body.appendChild(newTitle);
   ```
2. **Menghapus elemen dari DOM:**
   ```javascript
   document.body.removeChild(newTitle);
   ```

## Event Listener

DOM juga memungkinkan kita untuk menangani event, seperti klik tombol. Dalam contoh ini, ketika tombol diklik, teks pada elemen dengan ID "title" akan diubah:

```javascript
const changeTextButton = document.getElementById("changeTextButton");
changeTextButton.addEventListener("click", function () {
  title.textContent = "Teks telah diubah!";
});
```

## Kesimpulan

JavaScript DOM memungkinkan kita untuk mengakses dan memanipulasi elemen-elemen di halaman web secara dinamis. Dengan memahami cara mengakses elemen dan memodifikasi konten serta gaya elemen-elemen tersebut, Anda dapat membuat halaman web yang lebih interaktif dan dinamis.

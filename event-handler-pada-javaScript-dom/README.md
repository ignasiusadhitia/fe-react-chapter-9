# Event Handler pada JavaScript DOM

Proyek ini menjelaskan cara kerja **event handler** pada JavaScript DOM. Dengan event handler, kita dapat menangkap berbagai peristiwa (events) seperti klik tombol, pergerakan mouse, atau input dari pengguna, dan meresponsnya dengan fungsi JavaScript.

## Penggunaan Event Handler

### 1. Event click

Event `click` terjadi ketika sebuah elemen diklik oleh pengguna. Dalam contoh ini, ketika tombol diklik, JavaScript akan menampilkan pesan pop-up dengan `alert()`.

```javascript
const button = document.querySelector(".btn");
button.addEventListener("click", () => {
  alert("Hello World");
});
```

### 2. Event mouseover

Event `mouseover` terjadi ketika kursor mouse berada di atas elemen. Pada contoh ini, ketika kursor berada di atas tombol, pesan akan dicetak di konsol.

```javascript
button.addEventListener("mouseover", () => {
  console.log("Mouse berada di atas tombol");
});
```

### 3. Event mouseout

Event `mouseout` terjadi ketika kursor mouse meninggalkan elemen. Pada contoh ini, ketika kursor keluar dari tombol, pesan lain akan dicetak di konsol.

```javascript
button.addEventListener("mouseout", () => {
  console.log("Mouse keluar dari tombol");
});
```

### 4. Event keydown

Event `keydown` terjadi ketika pengguna menekan salah satu tombol pada keyboard. Fungsi ini mencatat tombol yang ditekan dan menampilkannya di konsol.

```javascript
document.addEventListener("keydown", (e) => {
  console.log(`Tombol ${e.key} ditekan`);
});
```

### 5. Event input

Event `input` terjadi ketika nilai dari elemen input, textarea, atau select berubah. Pada contoh ini, ketika pengguna mengetik sesuatu di input field, nilai input akan dicetak di konsol.

```javascript
const input = document.getElementById("input");
input.addEventListener("input", (event) => {
  console.log(`Nilai input: ${event.target.value}`);
});
```

## Menghapus Event Listener

Kita juga bisa menghapus event listener yang sudah ditambahkan menggunakan `removeEventListener()`. Pada contoh ini, event listener akan dihapus setelah 5 detik.

```javascript
const myFunc = () => {
  alert("Event listener akan dihapus setelah 5 detik");
};
button.addEventListener("click", myFunc);

setTimeout(() => {
  button.removeEventListener("click", myFunc);
}, 5000);
```

## Inline Event Listener vs addEventListener

### Inline Event Listener:

- Didefinisikan langsung dalam atribut HTML elemen.
- Sederhana dan cocok untuk prototipe atau skenario yang sangat sederhana.
- **contoh:**

```html
<button onclick="myFunc()">Klik Saya</button>
<script>
  function myFunc() {
    alert("Hello World");
  }
</script>
```

### addEventListener:

- Lebih fleksibel dan cocok untuk aplikasi yang lebih kompleks.
- Memungkinkan pemisahan antara kode JavaScript dan HTML, sehingga memudahkan pemeliharaan.
- Disarankan untuk digunakan dalam proyek pengembangan yang lebih besar.

## Kesimpulan

Event handler adalah cara yang sangat kuat untuk membuat halaman web lebih interaktif. Dengan memahami cara menangkap dan merespons berbagai event seperti `click, mouseover, keydown, dan input`, kita bisa mengembangkan aplikasi yang lebih dinamis dan menarik.

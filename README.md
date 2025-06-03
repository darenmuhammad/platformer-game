# 📘 JavaScript Canvas & Core Concepts Reference

Dokumentasi ini merangkum konsep penting terkait penggunaan elemen `<canvas>` di HTML5 dan fitur JavaScript umum yang sering digunakan dalam pembuatan grafik dan animasi.

---

## 🎨 1. `canvas`

Elemen HTML5 yang digunakan untuk menggambar grafik secara dinamis melalui JavaScript.

### Contoh:

```html
<canvas id="myCanvas" width="500" height="500"></canvas>
```


## 🧱 2. `getContext()`

Method untuk mendapatkan konteks menggambar dari elemen `<canvas>`. Konteks paling umum adalah `'2d'`.

### Contoh:

```javascript
const canvas = document.getElementById('myCanvas');
const ctx = canvas.getContext('2d');
```


## 📏 3. `canvas.width` dan `canvas.height`

Digunakan untuk mengatur ukuran sebenarnya dari canvas (bukan ukuran tampilan visual/CSS).

### Contoh:

```javascript
canvas.width = window.innerWidth;
canvas.height = window.innerHeight;
```


## 🚫 4. `canvas.innerWidth` (Tidak Ada)

`innerWidth` adalah properti milik `window`, bukan `canvas`. Biasanya digunakan untuk mengatur ukuran canvas secara responsif.

### Contoh benar:

```javascript
canvas.width = window.innerWidth;
```


## ⚙️ 5. `proportionalSize()` (Custom Function)

Bukan method bawaan JavaScript. Ini adalah fungsi buatan yang biasa digunakan untuk mengatur ukuran elemen berdasarkan ukuran canvas atau layar.
Fungsi seperti `proportionalSize()` bukanlah bagian dari API JavaScript standar, namun bisa dibuat sesuai kebutuhan dalam proyek.

### Contoh:

```javascript
function proportionalSize(value) {
  return value * (canvas.width / 800); // menyesuaikan terhadap lebar standar 800
}
```


## 🎨 6. `fillStyle`

Properti dari konteks canvas (`ctx`) yang menentukan warna isi dari bentuk yang digambar.

### Contoh:

```javascript
ctx.fillStyle = 'blue';
ctx.fillRect(10, 10, 100, 100); // menggambar kotak biru
```


## 🎞️ 7. `requestAnimationFrame()`

Method untuk membuat animasi yang efisien. Memanggil fungsi sebelum frame berikutnya dirender oleh browser.

### Contoh:

```javascript
function animate() {
  ctx.clearRect(0, 0, canvas.width, canvas.height);
  // ... gambar sesuatu
  requestAnimationFrame(animate);
}

animate();
```


## 🧹 8. `clearRect()`

Digunakan untuk menghapus area tertentu pada canvas.

### Contoh:

```javascript
ctx.clearRect(0, 0, canvas.width, canvas.height);
```


## ✨ 9. Shorthand Property Name

Sintaks singkat saat membuat objek di mana nama properti dan variabel sama.

### Contoh:

```javascript
const x = 5, y = 10;
const point = { x, y }; // sama dengan { x: x, y: y }
```


## 🧠 10. Boolean Expression dalam Array

Ekspresi boolean dapat dimasukkan ke dalam array. Hasilnya bisa difilter untuk menghapus nilai falsy.

### Contoh:

```javascript
const isLoggedIn = true;
const menuItems = ["Home", isLoggedIn && "Logout"].filter(Boolean);
console.log(menuItems); // ["Home", "Logout"]
```


## ♾️ 11. `Infinity`

Nilai khusus di JavaScript yang menunjukkan angka tak hingga, seperti hasil pembagian dengan nol.

### Contoh:

```javascript
console.log(1 / 0);    // Infinity
console.log(-1 / 0);   // -Infinity
```

### Mengecek apakah nilai terbatas:

```javascript
console.log(Number.isFinite(Infinity)); // false
```

# Class 06 - CSS part 2

# Object Fit & Aspect Ratio

CSS menyediakan berbagai properti untuk mengontrol bagaimana gambar atau elemen media lainnya seperti video disesuaikan dalam container mereka. Dua properti penting yang sering digunakan untuk tujuan ini adalah `object-fit` dan `aspect-ratio`.

### 1. **Object Fit**

Properti `object-fit` digunakan untuk menentukan bagaimana konten dari elemen seperti `<img>` atau `<video>` harus disesuaikan dengan ukuran container-nya.

**Nilai yang umum digunakan:**

- `fill` (default): Konten akan mengisi seluruh area container, tanpa mempertahankan rasio aspek aslinya.
- `contain`: Konten akan diskalakan untuk muat di dalam container, mempertahankan rasio aspek aslinya.
- `cover`: Konten akan diskalakan untuk menutupi seluruh area container, mempertahankan rasio aspek aslinya. Bagian dari konten mungkin terpotong.
- `none`: Konten tidak akan diskalakan.
- `scale-down`: Konten akan diskalakan seolah-olah `none` atau `contain`, mana yang menghasilkan ukuran lebih kecil.

**Contoh:**

**HTML:**

```html
<img src="https://example.com/image.jpg" class="object-fit-example">
```

**CSS:**

```css
.object-fit-example {
  width: 300px;
  height: 200px;
  object-fit: cover;
}
```

### 2. **Aspect Ratio**

Properti `aspect-ratio` digunakan untuk mengatur rasio aspek dari elemen, memastikan elemen mempertahankan rasio aspek tertentu saat diubah ukurannya.

**Format:**

- Rasio aspek dinyatakan dalam bentuk lebar / tinggi, misalnya `1 / 1` untuk rasio aspek persegi, `16 / 9` untuk rasio aspek layar lebar.

**Contoh:**

**HTML:**

```html
<div class="aspect-ratio-example">
  <img src="https://example.com/image.jpg">
</div>
```

**CSS:**

```css
.aspect-ratio-example {
  aspect-ratio: 16 / 9;
  width: 100%;
}

.aspect-ratio-example img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
```

### 3. **Menggunakan Bersama-sama: Object Fit dan Aspect Ratio**

Anda bisa menggunakan kedua properti ini bersama-sama untuk membuat elemen media yang responsif dan estetis.

**Contoh:**

**HTML:**

```html
<div class="media-container">
  <img src="https://example.com/image.jpg" class="responsive-media">
</div>
```

**CSS:**

```css
.media-container {
  width: 100%;
  max-width: 600px;
  aspect-ratio: 16 / 9;
  border: 2px solid #ccc;
  overflow: hidden;
}

.responsive-media {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
```

### 4. **Menggunakan Object Position**

Selain `object-fit`, properti `object-position` juga digunakan untuk mengontrol posisi dari elemen media di dalam container-nya. Ini berguna terutama saat menggunakan `object-fit: cover`.

**Contoh:**

**HTML:**

```html
<img src="https://example.com/image.jpg" class="object-position-example">
```

**CSS:**

```css
.object-position-example {
  width: 300px;
  height: 200px;
  object-fit: cover;
  object-position: top right;
}
```

### Ringkasan Properti

- **`object-fit`**: Mengontrol bagaimana konten dari elemen media disesuaikan dengan container-nya.
    - `fill`, `contain`, `cover`, `none`, `scale-down`
- **`aspect-ratio`**: Mengatur rasio aspek dari elemen.
    - Misal: `aspect-ratio: 16 / 9;`
- **`object-position`**: Mengontrol posisi konten dalam container.
    - Nilai seperti `center`, `top`, `bottom`, `left`, `right`, atau kombinasi seperti `top right`.

## Contoh lain:

### Contoh 1: Tanpa `object-fit`

Tanpa `object-fit`, gambar akan diubah ukurannya untuk memenuhi container, seringkali merusak rasio aspeknya.

**HTML:**

```html
<div class="container">
  <img src="https://via.placeholder.com/600x400" class="no-object-fit">
</div>
```

**CSS:**

```css
.container {
  width: 300px;
  height: 200px;
  border: 1px solid #000;
  overflow: hidden; /* Untuk memastikan elemen anak tidak keluar dari container */
}

.no-object-fit {
  width: 100%;
  height: 100%;
}
```

### Contoh 2: `object-fit: fill`

Gambar akan mengisi seluruh area container, tanpa mempertahankan rasio aspek aslinya.

**HTML:**

```html
<div class="container">
  <img src="https://via.placeholder.com/600x400" class="object-fit-fill">
</div>
```

**CSS:**

```css
.container {
  width: 300px;
  height: 200px;
  border: 1px solid #000;
  overflow: hidden;
}

.object-fit-fill {
  width: 100%;
  height: 100%;
  object-fit: fill;
}
```

### Contoh 3: `object-fit: contain`

Gambar akan diskalakan untuk muat di dalam container, mempertahankan rasio aspek aslinya.

**HTML:**

```html
<div class="container">
  <img src="https://via.placeholder.com/600x400" class="object-fit-contain">
</div>
```

**CSS:**

```css
.container {
  width: 300px;
  height: 200px;
  border: 1px solid #000;
  overflow: hidden;
}

.object-fit-contain {
  width: 100%;
  height: 100%;
  object-fit: contain;
}
```

### Contoh 4: `object-fit: cover`

Gambar akan diskalakan untuk menutupi seluruh area container, mempertahankan rasio aspek aslinya. Bagian dari gambar mungkin terpotong.

**HTML:**

```html
<div class="container">
  <img src="https://via.placeholder.com/600x400" class="object-fit-cover">
</div>
```

**CSS:**

```css
.container {
  width: 300px;
  height: 200px;
  border: 1px solid #000;
  overflow: hidden;
}

.object-fit-cover {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
```

### Contoh 5: `object-fit: none`

Gambar tidak akan diskalakan, sehingga mungkin hanya sebagian gambar yang terlihat jika ukuran gambar lebih besar dari container.

**HTML:**

```html
<div class="container">
  <img src="https://via.placeholder.com/600x400" class="object-fit-none">
</div>
```

**CSS:**

```css
.container {
  width: 300px;
  height: 200px;
  border: 1px solid #000;
  overflow: hidden;
}

.object-fit-none {
  width: 100%;
  height: 100%;
  object-fit: none;
}
```

### Contoh 6: `object-fit: scale-down`

Gambar akan diskalakan seolah-olah menggunakan `none` atau `contain`, mana yang menghasilkan ukuran lebih kecil.

**HTML:**

```html
<div class="container">
  <img src="https://via.placeholder.com/600x400" class="object-fit-scale-down">
</div>
```

**CSS:**

```css
.container {
  width: 300px;
  height: 200px;
  border: 1px solid #000;
  overflow: hidden;
}

.object-fit-scale-down {
  width: 100%;
  height: 100%;
  object-fit: scale-down;
}
```

### Kesimpulan

Dengan contoh-contoh ini, Anda dapat melihat perbedaan efek dari berbagai nilai `object-fit`. Properti `object-fit` sangat berguna ketika Anda ingin memastikan gambar atau video Anda tampil dengan cara tertentu di dalam container mereka, tanpa mengubah rasio aspek aslinya atau memastikan mereka mengisi seluruh container.

# CSS Reset & Normalize

### Apa itu CSS Reset?

CSS Reset adalah serangkaian aturan CSS yang dirancang untuk menghapus semua style default yang diterapkan oleh browser pada elemen HTML. Setiap browser memiliki style default yang berbeda untuk elemen HTML seperti margin, padding, ukuran font, dan lainnya. CSS Reset digunakan untuk memastikan bahwa semua elemen memiliki style yang konsisten di semua browser, sehingga memudahkan pengembang untuk mulai dengan dasar yang bersih dan menerapkan style mereka sendiri tanpa dipengaruhi oleh style default browser.

### Mengapa Menggunakan CSS Reset?

1. **Konsistensi Antar Browser**: Browser yang berbeda menerapkan style default yang berbeda-beda. Dengan menggunakan CSS Reset, Anda dapat memastikan bahwa elemen HTML terlihat sama di semua browser.
2. **Menghilangkan Ketidakpastian**: CSS Reset membantu menghilangkan ketidakpastian mengenai style default, sehingga memudahkan developer untuk mengontrol penampilan elemen secara konsisten.
3. **Memulai dari Nol**: CSS Reset memberikan kanvas kosong bagi developer yang memberikan kemudahan dalam menerapkan style.

### Contoh CSS Reset

Berikut adalah beberapa contoh CSS Reset yang umum digunakan:

### Eric Meyer's CSS Reset

Eric Meyer adalah salah satu yang paling dikenal dalam hal CSS Reset. Berikut adalah contohnya:

```css
/* http://meyerweb.com/eric/tools/css/reset/ 
   v2.0 | 20110126
   License: none (public domain)
*/

html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed, 
figure, figcaption, footer, header, hgroup, 
menu, nav, output, ruby, section, summary,
time, mark, audio, video {
	margin: 0;
	padding: 0;
	border: 0;
	font-size: 100%;
	font: inherit;
	vertical-align: baseline;
}
/* HTML5 display-role reset for older browsers */
article, aside, details, figcaption, figure, 
footer, header, hgroup, menu, nav, section {
	display: block;
}
body {
	line-height: 1;
}
ol, ul {
	list-style: none;
}
blockquote, q {
	quotes: none;
}
blockquote:before, blockquote:after,
q:before, q:after {
	content: '';
	content: none;
}
table {
	border-collapse: collapse;
	border-spacing: 0;
}
```

### Normalize.css

Normalize.css bertujuan untuk membuat style default browser lebih konsisten. Berikut contoh penggunaannya:

```css
*,
*:before,
*:after {
  box-sizing: border-box;
}

button,
[type='button'],
[type='reset'],
[type='submit'] {
  appearance: button;
  -webkit-appearance: button;
  background: none;
  border: 0;
  cursor: pointer;
}

button[disabled],
[type='button'][disabled],
[type='reset'][disabled],
[type='submit'][disabled] {
  cursor: default;
}

[type='search'] {
  appearance: textfield;
  -webkit-appearance: textfield;
}

main {
  display: block;
}

a {
  background-color: transparent;
  text-decoration: none;
}

[type='checkbox'],
[type='radio'] {
  padding: 0;
}
```

### Cara menerapkan reset & normalize:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>How to Reset & Normalize</title>
  <link rel="stylesheet" href="css/reset.css" /> <!-- harus urutan pertama -->
  <link rel="stylesheet" href="css/normalize.css" />
  <link rel="stylesheet" href="css/style.css" />
</head>
<body>
</body>
</html>
```

Ingat, selalu gunakan reset di paling awal sebelum normalize dan juga sebelum style.

---

# Flexbox

### Pengertian Flexbox

Flexbox (Flexible Box Layout) adalah model layout CSS yang dirancang untuk membuat tata letak satu dimensi lebih mudah dan lebih efisien. Flexbox sangat berguna untuk mengatur tata letak elemen dalam baris (row) atau kolom (column) serta mengatur elemen-elemen agar dapat merespons ukuran kontainer.

**Flexbox mempunyai dua elemen utama:**

1. **Flex Container**: Parent element (elemen induk) yang menerapkan `display: flex` atau `display: inline-flex`.
2. **Flex Items**: Elemen anak dari flex container yang diatur tata letaknya oleh flexbox.

### Flex Container

Properti yang digunakan pada flex container adalah sebagai berikut:

1. **display**
    - Mengubah elemen menjadi flex container.
    - Nilai yang dapat digunakan: `flex`, `inline-flex`.
    - Contoh:
        
        ```css
        .container {
          display: flex;
        }
        
        .inline-container {
          display: inline-flex;
        }
        ```
        
    
    Lihat detail mengenai flex vs inline-flex disini: 
    
    [Flex vs inline-flex](https://www.notion.so/Flex-vs-inline-flex-a5f2c54ea2fc4fd994a586c8e3c4db8b?pvs=21)
    
2. **flex-direction**
    - Menentukan arah utama di mana flex items akan diatur.
    - Nilai yang dapat digunakan: `row`, `row-reverse`, `column`, `column-reverse`.
    - Contoh:
        
        ```css
        .container-row {
          flex-direction: row; /* Default */
        }
        
        .container-column {
          flex-direction: column;
        }
        ```
        
3. **flex-wrap**
    - Mengatur apakah flex items akan dibungkus (wrap) jika tidak muat dalam satu baris atau kolom.
    - Nilai yang dapat digunakan: `nowrap`, `wrap`, `wrap-reverse`.
    - Contoh:
        
        ```css
        .container-nowrap {
          flex-wrap: nowrap; /* Default */
        }
        
        .container-wrap {
          flex-wrap: wrap;
        }
        ```
        
4. **justify-content**
    - Mengatur bagaimana flex items didistribusikan sepanjang main axis (sumbu utama).
    - Nilai yang dapat digunakan: `flex-start`, `flex-end`, `center`, `space-between`, `space-around`, `space-evenly`.
    - Contoh:
        
        ```css
        .container-justify {
          justify-content: center;
        }
        ```
        
5. **align-items**
    - Mengatur bagaimana flex items disejajarkan sepanjang cross axis (sumbu silang).
    - Nilai yang dapat digunakan: `stretch`, `flex-start`, `flex-end`, `center`, `baseline`.
    - Contoh:
        
        ```css
        .container-align {
          align-items: center;
        }
        ```
        
6. **align-content**
    - Mengatur bagaimana baris flex items disejajarkan ketika terdapat ruang kosong di cross axis.
    - Nilai yang dapat digunakan: `stretch`, `flex-start`, `flex-end`, `center`, `space-between`, `space-around`.
    - Catatan: Hanya berfungsi jika flex-wrap diatur ke `wrap` atau `wrap-reverse`.
    - Contoh:
        
        ```css
        .container-align-content {
          align-content: space-between;
        }
        ```
        

### Flex Items

Properti yang digunakan pada flex items adalah sebagai berikut:

1. **order**
    - Menentukan urutan tampilan flex items.
    - Nilai default adalah `0`.
    - Contoh:
        
        ```css
        .item-order {
          order: 2;
        }
        ```
        
2. **flex-grow**
    - Menentukan kemampuan flex items untuk tumbuh jika diperlukan.
    - Nilai default adalah `0`.
    - Contoh:
        
        ```css
        .item-grow {
          flex-grow: 1;
        }
        ```
        
3. **flex-shrink**
    - Menentukan kemampuan flex items untuk menyusut jika diperlukan.
    - Nilai default adalah `1`.
    - Contoh:
        
        ```css
        .item-shrink {
          flex-shrink: 0;
        }
        ```
        
4. **flex-basis**
    - Menentukan ukuran default dari flex items sebelum ruang tambahan didistribusikan.
    - Nilai default adalah `auto`.
    - Contoh:
        
        ```css
        .item-basis {
          flex-basis: 100px;
        }
        ```
        
5. **flex**
    - Properti singkat untuk menetapkan `flex-grow`, `flex-shrink`, dan `flex-basis`.
    - Nilai default adalah `0 1 auto`.
    - Contoh:
        
        ```css
        .item-flex {
          flex: 1 0 100px;
        }
        ```
        
6. **align-self**
    - Menentukan perataan flex items pada cross axis, mengesampingkan properti `align-items` dari container.
    - Nilai yang dapat digunakan: `auto`, `flex-start`, `flex-end`, `center`, `baseline`, `stretch`.
    - Contoh:
        
        ```css
        .item-align {
          align-self: flex-end;
        }
        ```
        

### Contoh Penggunaan Flexbox

Berikut adalah contoh penggunaan flexbox dalam HTML dan CSS:

```css
.container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-around;
  align-items: center;
  height: 300px;
}

.item {
  flex: 1 1 100px; /* flex-grow: 1; flex-shrink: 1; flex-basis: 100px; */
  margin: 10px;
  padding: 20px;
  background-color: lightblue;
  text-align: center;
}
```

```html
<div class="container">
  <div class="item">Item 1</div>
  <div class="item">Item 2</div>
  <div class="item">Item 3</div>
  <div class="item">Item 4</div>
</div>
```

### Penjelasan Mendalam tentang `flex-grow`, `flex-shrink`, dan `flex-basis`

1. **flex-grow**
    - `flex-grow` mengatur seberapa banyak elemen dapat tumbuh relatif terhadap elemen lain di dalam flex container ketika ada ruang ekstra yang tersedia.
    - Jika semua elemen memiliki `flex-grow: 1`, ruang ekstra akan didistribusikan secara merata.
    - Jika satu elemen memiliki `flex-grow: 2`, elemen tersebut akan menerima dua kali lebih banyak ruang ekstra dibandingkan elemen dengan `flex-grow: 1`.
2. **flex-shrink**
    - `flex-shrink` mengatur seberapa banyak elemen dapat menyusut relatif terhadap elemen lain di dalam flex container ketika ruang kurang dari yang diperlukan.
    - Jika semua elemen memiliki `flex-shrink: 1`, ruang yang kurang akan diambil dari elemen (dikurangi ukurannya berdasarkan keperluan)
    - Jika satu elemen memiliki `flex-shrink: 0`, elemen tersebut tidak akan menyusut ketika ada kekurangan ruang.
3. **flex-basis**
    - `flex-basis` menetapkan ukuran dasar dari elemen sebelum ruang tambahan dibagikan.
    - Nilai default adalah `auto`, yang berarti elemen akan menggunakan konten yang ada untuk menentukan ukuran dasar.
    - Menetapkan `flex-basis: 0%` memastikan bahwa ukuran dasar elemen adalah nol, yang memungkinkan `flex-grow` bekerja dari awal nol.
    
    **Contoh:**
    
    ```css
    .container {
      display: flex;
    }
    
    .item {
      flex-grow: 1;
      flex-basis: 0%; /* Menjamin flex-grow diaktifkan dari 0 */
    }
    ```
    
    Pada contoh di atas, elemen-elemen akan tumbuh secara proporsional dari ukuran dasar nol. Tanpa `flex-basis: 0%`, elemen-elemen akan memiliki ukuran dasar sesuai dengan kontennya dan `flex-grow` akan menambah ukuran setelah konten diberikan.
    

### Flexbox Responsif

Flexbox juga sangat efektif untuk desain responsif karena elemen-elemen dalam flex container dapat menyesuaikan diri dengan ukuran layar yang berbeda.

**Contoh:**

```css
.container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}

.item {
  flex: 1 1 calc(33.333% - 10px); /* Membuat tiga kolom dengan jarak */
  margin: 5px;
}
```

```html
<div class="container">
  <div class="item">Item 1</div>
  <div class="item">Item 2</div>
  <div class="item">Item 3</div>
  <div class="item">Item 4</div>
  <div class="item">Item 5</div>
  <div class="item">Item 6</div>
</div>
```

Dalam contoh ini, `flex: 1 1 calc(33.333% - 10px);` memastikan bahwa setiap elemen mengambil sepertiga dari lebar kontainer, dikurangi jarak antar elemen.

### Tips dan Trik Flexbox

1. **Centring secara Horizontal dan Vertikal**:
    
    ```css
    .container {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    ```
    
2. **Mengubah Urutan Elemen**:
    - Gunakan properti `order` untuk mengubah urutan tampilan elemen.
    - Contoh:
        
        ```css
        .first {
          order: 1;
        }
        
        .second {
          order: 2;
        }
        
        .third {
          order: 3;
        }
        ```
        
3. **Menggunakan `flex-grow` untuk Menyesuaikan Elemen**:
    - Gunakan `flex-grow` untuk membuat elemen menyesuaikan diri dalam kontainer.
    - Contoh:
        
        ```css
        .container {
          display: flex;
        }
        
        .item {
          flex-grow: 1;
        }
        ```
        

Dengan memahami konsep dan properti flexbox secara mendalam, kalian dapat membuat layout (tata letak) yang fleksibel dan responsif untuk project web kalian. Flexbox memungkinkan kalian mengatur elemen dengan cara yang lebih mudah dan efisien dibandingkan dengan model layout tradisional.

---

# Centering Element

Menempatkan elemen di tengah adalah salah satu tugas umum dalam desain web. Ada beberapa metode untuk melakukan ini, termasuk menggunakan margin otomatis, Flexbox, dan properti `text-align` untuk teks. Berikut adalah penjelasan dan contoh untuk masing-masing metode.

### 1. **Centering Elemen Menggunakan Margin Auto**

Metode ini paling umum digunakan untuk elemen blok yang memiliki lebar tetap.

**HTML:**

```html
<div class="box">Centered Box</div>
```

**CSS:**

```css
.box {
  width: 300px;
  margin: 0 auto; /* Mengatur margin kiri dan kanan otomatis */
  background-color: lightblue;
  text-align: center; /* Untuk centering teks di dalam elemen */
  padding: 20px;
}
```

### 2. **Centering Elemen Menggunakan Flexbox**

Flexbox menyediakan cara yang sangat fleksibel untuk menempatkan elemen di tengah, baik secara horizontal maupun vertikal.

**HTML:**

```html
<div class="container">
  <div class="box">Centered Box</div>
</div>
```

**CSS:**

```css
.container {
  display: flex;
  justify-content: center; /* Mengatur centering horizontal */
  align-items: center; /* Mengatur centering vertikal */
  height: 100vh; /* Mengisi tinggi viewport untuk melihat efek vertikal centering */
  background-color: lightgray;
}

.box {
  background-color: lightblue;
  padding: 20px;
}
```

### 3. **Centering Text Menggunakan `text-align`**

Properti `text-align` digunakan untuk menempatkan teks di tengah dalam elemen blok.

**HTML:**

```html
<div class="text-container">
  <p>This text is centered.</p>
</div>
```

**CSS:**

```css
.text-container {
  text-align: center; /* Mengatur centering teks */
  background-color: lightyellow;
  padding: 20px;
}
```

---

Cara tercepat untuk belajar adalah dengan berlatih dan eksperimen sesuai dengan materi yang sudah dijelaskan. Jika menemui kendala, jangan ragu untuk bertanya, seperti biasa di channel `#dev-questions` pada Slack supaya jawaban yang diberikan bisa membantu teman-teman yang lainnya juga.

# Grid Layout

CSS Grid Layout adalah teknik layout dua dimensi yang memungkinkan Anda mengatur elemen dalam baris dan kolom. Ini membuat pengaturan layout yang kompleks menjadi lebih mudah dan intuitif.

## Container

Container digunakan untuk mengatur grid container dan mendefinisikan grid structure, tentunya anda bebas menggunakan nama class apapun. Contohnya `grid-container` .

### 1. **display: grid**

- Mengubah elemen menjadi grid container.
- Contoh:
    
    ```css
    .container {
      display: grid;
    }
    ```
    

### 2. **grid-template-columns**

- Mendefinisikan kolom dalam grid. Anda bisa menggunakan panjang absolut, persentase, fraksi (`fr`), atau fungsi seperti `repeat()`.
- Contoh:
    
    ```css
    .container {
      display: grid;
      grid-template-columns: 100px 200px 100px; /* Tiga kolom dengan lebar 100px, 200px, dan 100px */
    }
    
    .container {
      display: grid;
      grid-template-columns: repeat(3, 1fr); /* Tiga kolom dengan lebar yang sama */
    }
    ```
    

### 3. **grid-template-rows**

- Mendefinisikan baris dalam grid. Anda bisa menggunakan panjang absolut, persentase, fraksi (`fr`), atau fungsi seperti `repeat()`.
- Contoh:
    
    ```css
    .container {
      display: grid;
      grid-template-rows: 50px 100px; /* Dua baris dengan tinggi 50px dan 100px */
    }
    
    .container {
      display: grid;
      grid-template-rows: repeat(2, 1fr); /* Dua baris dengan tinggi yang sama */
    }
    ```
    

### 4. **gap**

- Mendefinisikan jarak antara baris dan kolom dalam grid.
- Contoh:
    
    ```css
    .container {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      grid-template-rows: repeat(2, 1fr);
      gap: 10px; /* Jarak antara baris dan kolom adalah 10px */
    }
    ```
    

### 5. **grid-template-areas**

- Mendefinisikan layout grid menggunakan nama area.
- Contoh:
    
    ```css
    .container {
      display: grid;
      grid-template-areas:
        'header header header'
        'sidebar content content'
        'footer footer footer';
    }
    
    .header {
      grid-area: header;
    }
    
    .sidebar {
      grid-area: sidebar;
    }
    
    .content {
      grid-area: content;
    }
    
    .footer {
      grid-area: footer;
    }
    ```
    

## Item Properties

Item properties digunakan untuk mengatur elemen-elemen dalam grid.

### 1. **grid-column**

- Menentukan kolom tempat elemen dimulai dan berakhir.
- Contoh:
    
    ```css
    .item {
      grid-column: 1 / 3; /* Elemen ini akan mulai dari kolom 1 dan berakhir di kolom 3 */
    }
    ```
    

### 2. **grid-row**

- Menentukan baris tempat elemen dimulai dan berakhir.
- Contoh:
    
    ```css
    .item {
      grid-row: 1 / 2; /* Elemen ini akan mulai dari baris 1 dan berakhir di baris 2 */
    }
    ```
    

### 3. **grid-area**

- Menentukan area grid tempat elemen ditempatkan, sesuai dengan nama area yang ditentukan di `grid-template-areas`.
- Contoh:
    
    ```css
    .item {
      grid-area: header; /* Elemen ini akan ditempatkan di area 'header' */
    }
    ```
    

### Contoh Grid Layout Tanpa Menggunakan Grid Area Names

Dalam contoh ini, kita akan membuat layout grid tanpa menggunakan `grid-template-areas`. Sebaliknya, kita akan menggunakan properti `grid-column` dan `grid-row` untuk menentukan posisi elemen-elemen dalam grid.

### CSS:

```css
.container {
  display: grid;
  grid-template-columns: 1fr 2fr 1fr;
  grid-template-rows: 100px 200px 100px;
  gap: 10px;
}

.item1 {
  grid-column: 1 / 4; /* Mulai dari kolom 1 sampai kolom 4 */
  grid-row: 1 / 2; /* Mulai dari baris 1 sampai baris 2 */
  background-color: lightblue;
}

.item2 {
  grid-column: 1 / 2; /* Mulai dari kolom 1 sampai kolom 2 */
  grid-row: 2 / 3; /* Mulai dari baris 2 sampai baris 3 */
  background-color: lightgreen;
}

.item3 {
  grid-column: 2 / 4; /* Mulai dari kolom 2 sampai kolom 4 */
  grid-row: 2 / 3; /* Mulai dari baris 2 sampai baris 3 */
  background-color: lightcoral;
}

.item4 {
  grid-column: 1 / 4; /* Mulai dari kolom 1 sampai kolom 4 */
  grid-row: 3 / 4; /* Mulai dari baris 3 sampai baris 4 */
  background-color: lightgray;
}
```

### HTML:

```html
<div class="container">
  <div class="item1">Item 1</div>
  <div class="item2">Item 2</div>
  <div class="item3">Item 3</div>
  <div class="item4">Item 4</div>
</div>
```

### Penjelasan:

- **Grid Container:** `.container` diatur sebagai grid dengan 3 kolom dan 3 baris.
    - `grid-template-columns: 1fr 2fr 1fr;` - Mendefinisikan kolom dengan fraksi.
    - `grid-template-rows: 100px 200px 100px;` - Mendefinisikan baris dengan panjang absolut.
    - `gap: 10px;` - Menambahkan jarak 10px antara baris dan kolom.
- **Grid Items:**
    - `.item1` menggunakan `grid-column: 1 / 4;` untuk mencakup semua tiga kolom dan `grid-row: 1 / 2;` untuk berada di baris pertama.
    - `.item2` menggunakan `grid-column: 1 / 2;` untuk mencakup kolom pertama dan `grid-row: 2 / 3;` untuk berada di baris kedua.
    - `.item3` menggunakan `grid-column: 2 / 4;` untuk mencakup kolom kedua dan ketiga serta `grid-row: 2 / 3;` untuk berada di baris kedua.
    - `.item4` menggunakan `grid-column: 1 / 4;` untuk mencakup semua tiga kolom dan `grid-row: 3 / 4;` untuk berada di baris ketiga.

**Lihat demo disini:**

https://codepen.io/Edwin-Anderson/pen/GRbJezv

### Contoh Grid Layout Dengan Menggunakan Grid Area Names:

### CSS:

```css
.container {
  display: grid;
  grid-template-columns: 1fr 2fr 1fr;
  grid-template-rows: 100px 200px;
  gap: 10px;
  grid-template-areas:
    'header header header'
    'sidebar content content'
    'footer footer footer';
}

.item1 {
  grid-area: header;
  background-color: lightblue;
}

.item2 {
  grid-area: sidebar;
  background-color: lightgreen;
}

.item3 {
  grid-area: content;
  background-color: lightcoral;
}

.item4 {
  grid-area: footer;
  background-color: lightgray;
}
```

### HTML:

```html
<div class="container">
  <div class="item1">Item 1</div>
  <div class="item2">Item 2</div>
  <div class="item3">Item 3</div>
  <div class="item4">Item 4</div>
</div>
```

### Penjelasan:

- **Grid Container:** `.container` diatur sebagai grid dengan 3 kolom dan 2 baris.
    - `grid-template-columns: 1fr 2fr 1fr;` - Mendefinisikan kolom dengan fraksi.
    - `grid-template-rows: 100px 200px;` - Mendefinisikan baris dengan panjang absolut.
    - `gap: 10px;` - Menambahkan jarak 10px antara baris dan kolom.
    - `grid-template-areas:` - Mendefinisikan area layout dengan nama area seperti 'header', 'sidebar', 'content', dan 'footer'.
- **Grid Items:**
    - `.header` ditempatkan di area 'header'.
    - `.sidebar` ditempatkan di area 'sidebar'.
    - `.content` ditempatkan di area 'content'.
    - `.footer` ditempatkan di area 'footer'.

**Lihat demo disini:**

https://codepen.io/Edwin-Anderson/pen/OJeVqdz

**Note:**

Grid area names (grid-template-areas), akan lebih jarang untuk digunakan untuk real project yang menggunakan dynamic grid (total items depend on the data given by the endpoint). Nanti akan dijelaskan saat kalian sudah masuk ke materi React. So kesimpulannya adalah, **grid layout tanpa menggunakan grid area names** akan lebih sering digunakan.

---

# CSS Gradient

Gradient dalam CSS adalah transisi warna yang halus antara dua atau lebih warna, gradient dalam CSS dianggap sebagai image(gambar). Properti `background-image` digunakan untuk menetapkan gradient sebagai gambar latar belakang dari suatu elemen. Tiga jenis gradien utama dalam CSS adalah linear gradient, radial gradient, dan conic gradient.

### 1. **Linear Gradient**

Linear gradient menciptakan transisi warna sepanjang garis lurus. Anda dapat menentukan arah, warna awal, warna akhir, dan titik persentase untuk warna transisi.

**Sintaks Dasar:**

```css
background-image: linear-gradient(direction, color-stop1, color-stop2, ...);
```

**Contoh:**

**HTML:**

```html
<div class="linear-gradient-example">Linear Gradient</div>
```

**CSS:**

```css
.linear-gradient-example {
  width: 300px;
  height: 200px;
  background-image: linear-gradient(to right, red, yellow); /* dari kiri ke kanan */
}
```

### 2. **Radial Gradient**

Radial gradient memancarkan warna dari titik pusat, menciptakan efek melingkar. Anda dapat menentukan posisi pusat, bentuk, ukuran, dan warna transisi.

**Sintaks Dasar:**

```css
background-image: radial-gradient(shape size at position, color-stop1, color-stop2, ...);
```

**Contoh:**

**HTML:**

```html
<div class="radial-gradient-example">Radial Gradient</div>
```

**CSS:**

```css
.radial-gradient-example {
  width: 300px;
  height: 200px;
  background-image: radial-gradient(circle at center, blue, lightblue);
}
```

### 3. **Conic Gradient**

Conic gradient memancarkan warna dari satu titik, menciptakan transisi warna yang mengelilingi titik tersebut. Ini mirip dengan radial gradient tetapi dengan transisi warna yang bergerak secara radial.

**Sintaks Dasar:**

```css
background-image: conic-gradient(from angle, color-stop1, color-stop2, ...);
```

**Contoh:**

**HTML:**

```html
<div class="conic-gradient-example">Conic Gradient</div>
```

**CSS:**

```css
.conic-gradient-example {
  width: 300px;
  height: 200px;
  background-image: conic-gradient(from 0deg, red, yellow, green, blue, red);
}
```

### 4. **Advanced Gradient Features**

- **Color Stops**: Anda dapat menentukan lebih dari dua warna untuk menciptakan transisi yang lebih kompleks. Setiap warna juga dapat memiliki nilai persentase atau posisi untuk menentukan di mana transisi terjadi.
    
    **Contoh:**
    
    ```css
    background-image: linear-gradient(to right, red 0%, orange 30%, yellow 60%, green 90%);
    ```
    
- **Transparency**: Anda dapat menggunakan warna dengan alpha (RGBA) untuk menciptakan gradien dengan efek transparansi.
    
    **Contoh:**
    
    ```css
    background-image: linear-gradient(to bottom, rgba(255, 0, 0, 0.5), rgba(0, 0, 255, 0.5));
    ```
    
- **Repeating Gradients**: CSS juga mendukung gradien berulang dengan menggunakan `repeating-linear-gradient`, `repeating-radial-gradient`, dan `repeating-conic-gradient`.
    
    **Contoh:**
    
    ```css
    background-image: repeating-linear-gradient(45deg, yellow, yellow 10px, orange 10px, orange 20px);
    ```
    

### Kesimpulan

Gradient dalam CSS, meskipun tidak berbentuk gambar fisik, dianggap sebagai gambar latar belakang (background image). Properti `background-image` digunakan untuk mengaplikasikan gradien ini. Dengan menguasai penggunaan berbagai jenis gradien, Anda dapat membuat desain web yang lebih menarik dan dinamis.

- **Linear Gradient**: Transisi warna sepanjang garis lurus.
- **Radial Gradient**: Transisi warna memancar dari titik pusat.
- **Conic Gradient**: Transisi warna mengelilingi titik pusat.

---

# Pseudo-Elements and Pseudo-Classes

### Pseudo-Elements

Pseudo-elements digunakan untuk menambahkan elemen yang tidak ada di dalam HTML secara langsung. Pseudo-elements dimulai dengan `::` dan biasanya digunakan untuk menambahkan konten atau style tertentu pada elemen HTML.

1. **::before**
    - Digunakan untuk menambahkan konten sebelum konten elemen yang ada.
    - Contoh:
        
        ```css
        .example::before {
          content: "Before: ";
          color: red;
        }
        ```
        
2. **::after**
    - Digunakan untuk menambahkan konten setelah konten elemen yang ada.
    - Contoh:
        
        ```css
        .example::after {
          content: " After";
          color: blue;
        }
        ```
        

### Pseudo-Classes

Pseudo-classes digunakan untuk menargetkan elemen berdasarkan kondisi atau keadaan tertentu, seperti saat elemen diklik, saat elemen dalam keadaan aktif, atau saat elemen dipilih.

1. **:hover**
    - Digunakan untuk menargetkan elemen saat kursor mouse berada di atasnya.
    - Contoh:
        
        ```css
        a:hover {
          color: green;
        }
        ```
        
2. **:focus**
    - Digunakan untuk menargetkan elemen saat elemen tersebut berada dalam keadaan fokus (misalnya input field yang sedang diketik).
    - Contoh:
        
        ```css
        input:focus {
          border-color: blue;
        }
        ```
        
3. **(n)**
    - Digunakan untuk menargetkan elemen berdasarkan posisi urutan dalam parent element.
    - Contoh:
        
        ```css
        ul li:nth-child(2) {
          color: purple;
        }
        ```
        
4. **(selector)**
    - Digunakan untuk menargetkan elemen yang tidak cocok dengan selector tertentu.
    - Contoh:
        
        ```css
        input:not([type="text"]) {
          border-color: red;
        }
        ```
        

### Perbedaan antara `::` dan `:`

- **:: (Double Colon)**
    - Digunakan untuk pseudo-elements.
    - Contoh: `::before`, `::after`, `::first-line`, `::first-letter`.
    - Pseudo-elements menambahkan elemen ke dalam DOM tanpa perlu menulis elemen tambahan dalam HTML.
    - Contoh:
        
        ```css
        p::first-line {
          font-weight: bold;
        }
        ```
        
- **: (Single Colon)**
    - Digunakan untuk pseudo-classes.
    - Contoh: `:hover`, `:focus`, `:nth-child`, `:not`.
    - Pseudo-classes menargetkan elemen berdasarkan keadaan atau kondisi tertentu.
    - Contoh:
        
        ```css
        button:hover {
          background-color: yellow;
        }
        ```
        

### Contoh Penerapan Pseudo-Elements dan Pseudo-Classes

### CSS

```css
.example::before {
  content: "Before: ";
  color: red;
}

.example::after {
  content: " After";
  color: blue;
}

a:hover {
  color: green;
}

input:focus {
  border-color: blue;
}

ul li:nth-child(2) {
  color: purple;
}

input:not([type="text"]) {
  border-color: red;
}

p::first-line {
  font-weight: bold;
}

button:hover {
  background-color: yellow;
}

```

### HTML

```html
<div class="example">This is an example.</div>
<a href="#">Hover over me</a>
<input type="text" placeholder="Focus on me">
<input type="password" placeholder="Password input">
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
<p>This is an example paragraph. The first line will be bold.</p>
<button>Hover over me</button>
```

**Lihat disini:**

https://codepen.io/Edwin-Anderson/pen/LYKVqQX

---

# Pembahasan CSS `calc()`

Fungsi `calc()` di CSS adalah alat yang sangat berguna untuk melakukan perhitungan sederhana secara langsung dalam CSS. Fungsi ini memungkinkan Anda mengkombinasikan berbagai unit pengukuran seperti pixel (px), em, rem, persentase (%), dan lainnya dalam satu ekspresi matematika untuk menghasilkan nilai dinamis.

### **Sintaks Dasar `calc()`**

Sintaks dasar dari `calc()` adalah:

```css
property: calc(expression);
```

Di mana `expression` adalah perhitungan matematika yang valid, yang bisa mencakup operasi penjumlahan (+), pengurangan (-), perkalian (*), dan pembagian (/).

### **Contoh Penggunaan `calc()`**

1. **Mengatur Lebar Elemen dengan Pengurangan**

Menggunakan `calc()` untuk mengurangi nilai tetap dari persentase lebar elemen, berguna untuk menciptakan layout yang responsif.

**HTML:**

```html
<div class="calc-width-example">Content</div>
```

**CSS:**

```css
.calc-width-example {
  width: calc(100% - 50px); /* Lebar elemen adalah 100% lebar kontainer dikurangi 50px */
  background-color: lightblue;
  padding: 20px;
}
```

Dalam contoh ini, lebar elemen `.calc-width-example` disesuaikan dengan lebar kontainer, dikurangi 50px. Ini memastikan bahwa elemen tetap berada di dalam batas kontainer, dengan mempertimbangkan margin atau padding lainnya.

1. **Mengatur Margin dan Padding**

Anda dapat menggunakan `calc()` untuk menghitung margin atau padding berdasarkan persentase dari kontainer atau unit lainnya.

**HTML:**

```html
<div class="calc-padding-example">Content</div>
```

**CSS:**

```css
.calc-padding-example {
  padding: calc(10px + 2%); /* Padding adalah 10px ditambah 2% dari lebar kontainer */
  background-color: lightgreen;
}
```

Dalam contoh ini, padding elemen adalah kombinasi dari nilai tetap (10px) dan nilai dinamis (2% dari lebar kontainer), memungkinkan desain yang lebih fleksibel.

1. **Mengatur Tinggi Elemen**

`calc()` juga berguna untuk mengatur tinggi elemen, terutama dalam konteks layout yang responsif atau dinamis.

**HTML:**

```html
<div class="calc-height-example">Content</div>
```

**CSS:**

```css
.calc-height-example {
  height: calc(100vh - 100px); /* Tinggi elemen adalah 100% tinggi viewport dikurangi 100px */
  background-color: lightcoral;
}
```

Contoh ini menunjukkan penggunaan `calc()` untuk menetapkan tinggi elemen berdasarkan tinggi viewport (`100vh`), dikurangi nilai tetap 100px. Ini berguna ketika Anda ingin menjaga elemen agar selalu terlihat di layar, mengurangi ruang untuk elemen tetap seperti header atau footer.

1. **Mengkombinasikan Berbagai Unit**

`calc()` memungkinkan penggabungan berbagai unit dalam satu perhitungan, seperti px, %, vw, vh, dll.

**HTML:**

```html
<div class="calc-mixed-units-example">Content</div>
```

**CSS:**

```css
.calc-mixed-units-example {
  width: calc(50% + 100px); /* Lebar elemen adalah 50% dari kontainer ditambah 100px */
  background-color: lightyellow;
}
```

### **Catatan Penting**

1. **Spasi di Sekitar Operator**: Pastikan untuk menggunakan spasi di sekitar operator matematika (+, -, *, /) dalam `calc()`. Misalnya, `calc(100% - 50px)` adalah benar, sedangkan `calc(100%-50px)` adalah salah.
2. **Kompatibilitas Browser**: `calc()` didukung oleh semua browser modern, tetapi sebaiknya selalu memeriksa kompatibilitas jika Anda perlu mendukung versi browser yang lebih lama.
3. **Penggunaan yang Berlebihan**: Meskipun `calc()` sangat berguna, gunakan dengan bijak dan hanya ketika diperlukan, karena perhitungan dinamis dapat mempengaruhi kinerja rendering halaman.

### Kesimpulan

Fungsi `calc()` adalah alat yang kuat dalam CSS yang memungkinkan fleksibilitas dan kontrol yang lebih besar atas layout dan styling. Dengan `calc()`, Anda dapat membuat layout yang lebih dinamis dan responsif, menggabungkan berbagai unit pengukuran dan nilai dalam perhitungan yang sama.

---

# CSS Transform

Properti `transform` di CSS digunakan untuk memanipulasi elemen HTML dalam ruang 2D atau 3D. Dengan `transform`, Anda dapat menggeser, memutar, menskalakan, atau memiringkan elemen tanpa mempengaruhi elemen lain di sekitarnya. Properti ini sangat berguna untuk menciptakan efek visual dinamis dan interaktif.

### **Fungsi Transformasi Utama**

1. **`translate()`**: Menggeser elemen dari posisi asalnya.
2. **`scale()`**: Mengubah ukuran elemen.
3. **`rotate()`**: Memutar elemen di sekitar titik asal.
4. **`skew()`**: Miringkan elemen di sepanjang sumbu X atau Y.
5. **`matrix()`**: Kombinasi dari transformasi di atas dalam satu fungsi.

### 1. **`translate()`**

Fungsi `translate()` digunakan untuk menggeser elemen dari posisi asalnya. Anda dapat menggeser elemen di sepanjang sumbu X, Y, atau keduanya.

**Sintaks Dasar:**

```css
transform: translate(x, y);
```

**Contoh:**

**HTML:**

```html
<div class="translate-example">Translate</div>
```

**CSS:**

```css
.translate-example {
  width: 100px;
  height: 100px;
  background-color: lightblue;
  transform: translate(50px, 100px); /* Geser 50px ke kanan dan 100px ke bawah */
}
```

### 2. **`scale()`**

Fungsi `scale()` digunakan untuk mengubah ukuran elemen. Anda dapat memperbesar atau memperkecil elemen di sepanjang sumbu X, Y, atau keduanya.

**Sintaks Dasar:**

```css
transform: scale(x, y);
```

**Contoh:**

**HTML:**

```html
<div class="scale-example">Scale</div>
```

**CSS:**

```css
.scale-example {
  width: 100px;
  height: 100px;
  background-color: lightgreen;
  transform: scale(1.5); /* Memperbesar elemen 1.5 kali di kedua sumbu */
}
```

Dalam contoh ini, elemen diperbesar sebesar 1.5 kali ukuran aslinya.

### 3. **`rotate()`**

Fungsi `rotate()` digunakan untuk memutar elemen di sekitar titik asal. Sudut rotasi ditentukan dalam derajat (deg).

**Sintaks Dasar:**

```css
transform: rotate(angle);
```

**Contoh:**

**HTML:**

```html
<div class="rotate-example">Rotate</div>
```

**CSS:**

```css
.rotate-example {
  width: 100px;
  height: 100px;
  background-color: lightcoral;
  transform: rotate(45deg); /* Memutar elemen 45 derajat searah jarum jam */
}
```

### 4. **`skew()`**

Fungsi `skew()` digunakan untuk memiringkan elemen di sepanjang sumbu X atau Y. Anda dapat menggunakan `skewX()` dan `skewY()` untuk memiringkan di sepanjang sumbu tertentu.

**Sintaks Dasar:**

```css
transform: skew(x-angle, y-angle);
```

**Contoh:**

**HTML:**

```html
<div class="skew-example">Skew</div>
```

**CSS:**

```css
.skew-example {
  width: 100px;
  height: 100px;
  background-color: lightyellow;
  transform: skew(20deg, 10deg); /* Miringkan elemen 20 derajat di X dan 10 derajat di Y */
}
```

### Kesimpulan

CSS `transform` adalah cara untuk memanipulasi elemen secara visual di halaman web. Dengan menggunakan transformasi seperti `translate`, `scale`, `rotate`, `skew`, Anda dapat menciptakan efek dinamis dan interaktif yang menarik jika digabungkan dengan transition yang dijelaskan di bawah.

---

# CSS Transition

CSS Transition adalah fitur yang memungkinkan perubahan properti CSS terjadi secara bertahap selama periode waktu tertentu, bukan langsung. Ini memberikan cara yang halus untuk memperlihatkan perubahan visual, seperti perubahan warna, ukuran, posisi, dan transparansi. Dengan `transition`, Anda dapat menentukan properti apa yang harus diubah, durasi perubahan, dan fungsi waktu untuk kontrol lebih lanjut.

### **Properti `transition` Utama**

1. **`transition-property`**: Menentukan properti CSS mana yang akan diubah.
2. **`transition-duration`**: Menentukan durasi dari transisi.
3. **`transition-timing-function`**: Menentukan kecepatan kurva transisi.
4. **`transition-delay`**: Menentukan berapa lama waktu sebelum transisi dimulai.

### **Menggunakan Shorthand `transition`**

Anda dapat menggunakan properti `transition` sebagai shorthand untuk mendefinisikan semua properti transisi dalam satu deklarasi.

**Sintaks Dasar:**

```css
transition: property duration timing-function delay;
```

**Contoh:**

```css
transition: all 0.3s ease-in-out 0s;
```

### **Contoh Penggunaan**

1. **Transition Sederhana pada Hover**

**HTML:**

```html
<div class="box">Hover over me!</div>
```

**CSS:**

```css
.box {
  width: 100px;
  height: 100px;
  background-color: lightblue;
  transition: background-color 0.5s ease; /* Transisi perubahan warna selama 0.5s */
}

.box:hover {
  background-color: lightcoral; /* Warna berubah saat hover */
}
```

Dalam contoh ini, ketika pengguna mengarahkan kursor ke atas elemen `.box`, warna latar belakangnya akan berubah dari biru muda menjadi koral muda dengan transisi yang halus selama 0.5 detik.

1. **Transition dengan Banyak Properti**

Anda dapat menentukan transisi untuk beberapa properti dengan menggunakan koma untuk memisahkan setiap deklarasi.

**HTML:**

```html
<div class="multi-box">Hover over me!</div>
```

**CSS:**

```css
.multi-box {
  width: 100px;
  height: 100px;
  background-color: lightgreen;
  border-radius: 0;
  transition: width 0.3s ease, background-color 0.3s ease, border-radius 0.3s ease;
}

.multi-box:hover {
  width: 150px; /* Perubahan lebar */
  background-color: lightpink; /* Perubahan warna */
  border-radius: 50%; /* Perubahan border-radius */
}
```

Dalam contoh ini, ketika elemen `.multi-box` di-hover, lebar elemen akan meningkat, warna latar belakang akan berubah, dan sudut-sudutnya akan menjadi bulat secara bersamaan dalam durasi 0.3 detik.

1. **Transition dengan Delay**

Anda juga dapat menambahkan delay untuk menunda dimulainya transisi.

**HTML:**

```html
<div class="delay-box">Hover over me!</div>
```

**CSS:**

```css
.delay-box {
  width: 100px;
  height: 100px;
  background-color: lightyellow;
  transition: background-color 1s ease 0.5s; /* Delay 0.5s sebelum transisi */
}

.delay-box:hover {
  background-color: lightblue;
}
```

Dalam contoh ini, ada penundaan selama 0.5 detik sebelum transisi warna latar belakang dimulai saat elemen `.delay-box` di-hover. Setelah itu, transisi berlangsung selama 1 detik.

1. **Transition Timing Function**

Fungsi waktu (`timing function`) mengontrol percepatan perubahan selama durasi transisi. Fungsi ini dapat mempengaruhi bagaimana perubahan terjadi sepanjang waktu.

**Nilai yang umum digunakan:**

- `linear`: Perubahan dengan kecepatan konstan.
- `ease`: Transisi mulai lambat, dipercepat, dan kemudian melambat lagi.
- `ease-in`: Transisi mulai lambat, kemudian dipercepat.
- `ease-out`: Transisi mulai cepat, kemudian melambat.
- `ease-in-out`: Kombinasi dari `ease-in` dan `ease-out`.

**Contoh:**

```css
.transition-example {
  width: 100px;
  height: 100px;
  background-color: lightgreen;
  transition: width 0.5s ease-in-out;
}

.transition-example:hover {
  width: 200px;
}
```

Dalam contoh ini, `ease-in-out` digunakan untuk memulai transisi dengan lambat, kemudian dipercepat di tengah, dan melambat kembali pada akhir.

### Kesimpulan

CSS `transition` adalah alat yang berguna untuk menciptakan perubahan visual yang halus pada elemen-elemen di halaman web. Dengan memanfaatkan properti-properti seperti `transition-property`, `transition-duration`, `transition-timing-function`, dan `transition-delay`, Anda dapat mengontrol bagaimana dan kapan perubahan tersebut terjadi.

---

# CSS Keyframes

CSS Keyframes digunakan untuk mendefinisikan aturan untuk animasi kompleks yang melibatkan perubahan nilai properti CSS pada berbagai tahap dalam durasi animasi. Dengan menggunakan keyframes, Anda dapat menentukan serangkaian "frame" yang menggambarkan kondisi elemen pada waktu tertentu, memungkinkan Anda untuk membuat animasi yang halus dan terperinci.

### **Dasar-dasar Keyframes**

Keyframes didefinisikan menggunakan aturan `@keyframes`, diikuti oleh nama animasi dan blok yang berisi deskripsi dari setiap langkah animasi. Setiap langkah ditentukan dengan menggunakan persentase atau kata kunci (`from` dan `to`), yang masing-masing mewakili titik awal dan akhir dari animasi.

### **Sintaks Dasar `@keyframes`**

```css
@keyframes animation-name {
  from {
    /* Properti awal */
  }
  to {
    /* Properti akhir */
  }
}
```

Atau menggunakan persentase untuk mendefinisikan langkah-langkah lebih detail:

```css
@keyframes animation-name {
  0% {
    /* Properti awal */
  }
  50% {
    /* Properti di tengah */
  }
  100% {
    /* Properti akhir */
  }
}
```

### **Contoh Penggunaan Keyframes**

1. **Animasi Sederhana dengan `from` dan `to`**

**HTML:**

```html
<div class="simple-animation">Simple Animation</div>
```

**CSS:**

```css
.simple-animation {
  width: 100px;
  height: 100px;
  background-color: lightblue;
  animation: simpleMove 2s infinite;
}

@keyframes simpleMove {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(200px);
  }
}
```

Dalam contoh ini, animasi `simpleMove` menggerakkan elemen `.simple-animation` dari posisi awal ke kanan sejauh 200px selama 2 detik dan mengulanginya terus-menerus (`infinite`).

1. **Animasi dengan Beberapa Langkah Menggunakan Persentase**

**HTML:**

```html
<div class="complex-animation">Complex Animation</div>
```

**CSS:**

```css
.complex-animation {
  width: 100px;
  height: 100px;
  background-color: lightgreen;
  animation: complexMove 3s infinite;
}

@keyframes complexMove {
  0% {
    transform: translateX(0);
    background-color: lightgreen;
  }
  50% {
    transform: translateX(100px);
    background-color: yellow;
  }
  100% {
    transform: translateX(0);
    background-color: lightgreen;
  }
}
```

Dalam contoh ini, animasi `complexMove` menggerakkan elemen `.complex-animation` ke kanan sejauh 100px pada 50% dari durasi animasi, mengubah warna latar belakang menjadi kuning, kemudian kembali ke posisi awal dan warna awal pada akhir animasi.

### **Properti Animasi yang Terkait**

Selain mendefinisikan keyframes, Anda juga perlu menetapkan animasi ke elemen yang akan dianimasikan dengan menggunakan beberapa properti CSS:

- **`animation-name`**: Nama animasi yang ditentukan oleh `@keyframes`.
- **`animation-duration`**: Durasi dari animasi dalam detik atau milidetik.
- **`animation-timing-function`**: Fungsi waktu untuk menentukan bagaimana langkah animasi dilakukan. Nilai yang umum digunakan termasuk `ease`, `linear`, `ease-in`, `ease-out`, dan `ease-in-out`.
- **`animation-delay`**: Waktu tunda sebelum animasi dimulai.
- **`animation-iteration-count`**: Jumlah berapa kali animasi harus diputar. Nilai `infinite` digunakan untuk animasi yang terus berjalan.
- **`animation-direction`**: Menentukan apakah animasi harus berjalan maju (`normal`), mundur (`reverse`), atau bergantian (`alternate`, `alternate-reverse`).
- **`animation-fill-mode`**: Menentukan apakah animasi harus menerapkan gaya yang ditentukan oleh animasi sebelum atau setelah animasi diputar. Nilai yang umum digunakan termasuk `none`, `forwards`, `backwards`, dan `both`.

**Contoh Penggunaan Properti Animasi:**

```css
.animated-element {
  animation-name: myAnimation;
  animation-duration: 4s;
  animation-timing-function: ease-in-out;
  animation-delay: 1s;
  animation-iteration-count: infinite;
  animation-direction: alternate;
  animation-fill-mode: forwards;
}
```

### **Kesimpulan**

CSS Keyframes memungkinkan Anda untuk menciptakan animasi yang kompleks dan halus dengan mendefinisikan serangkaian kondisi elemen pada waktu tertentu. Dengan menggunakan keyframes dan properti animasi terkait, Anda dapat menciptakan berbagai efek visual yang dinamis dan interaktif pada halaman web Anda.

---

# Responsive Design

Responsive design adalah pendekatan dalam desain web yang bertujuan untuk membuat halaman web terlihat baik di berbagai perangkat dan ukuran layar. Ini melibatkan penggunaan berbagai teknik seperti media queries dan mobile-first design.

### Media Queries

Media queries adalah fitur CSS3 yang memungkinkan Anda untuk menerapkan gaya CSS berdasarkan karakteristik perangkat seperti lebar layar, tinggi layar, orientasi, dan resolusi. Dengan media queries, Anda dapat membuat layout yang responsif dan adaptif.

### Contoh Media Queries:

1. **Basic Media Query:**
    - Mengubah style berdasarkan lebar layar.
    
    ```css
    @media (max-width: 600px) {
      body {
        background-color: lightblue;
      }
    }
    ```
    
    Pada contoh di atas, background color dari body akan berubah menjadi lightblue ketika lebar layar maksimum adalah 600px atau lebih kecil.
    
2. **Multiple Conditions:**
    - Menggunakan `and` untuk menggabungkan beberapa kondisi.
    
    ```css
    @media (min-width: 600px) and (max-width: 1200px) {
      body {
        background-color: lightgreen;
      }
    }
    ```
    
    Pada contoh di atas, background color dari body akan berubah menjadi lightgreen ketika lebar layar antara 600px dan 1200px.
    

### Mobile-First Design

Mobile-first design adalah pendekatan dalam desain web di mana Anda memulai desain dengan mempertimbangkan perangkat mobile terlebih dahulu, kemudian memperluas gaya untuk perangkat dengan ukuran layar yang lebih besar menggunakan media queries.

### Contoh Mobile-First Design:

1. **Default Styles for Mobile:**
    - Gaya dasar yang diterapkan untuk perangkat mobile.
    
    ```css
    body {
      font-size: 14px;
      padding: 10px;
    }
    ```
    
2. **Media Queries for Larger Devices:**
    - Menggunakan media queries untuk memperluas gaya untuk perangkat dengan ukuran layar yang lebih besar.
    
    ```css
    @media (min-width: 600px) {
      body {
        font-size: 16px;
        padding: 20px;
      }
    }
    
    @media (min-width: 1200px) {
      body {
        font-size: 18px;
        padding: 30px;
      }
    }
    ```
    
    Pada contoh di atas, ukuran font dan padding akan disesuaikan berdasarkan lebar layar perangkat:
    
    - Untuk layar yang lebih kecil dari 600px, ukuran font adalah 14px dan padding adalah 10px.
    - Untuk layar yang lebih besar dari 600px tetapi lebih kecil dari 1200px, ukuran font adalah 16px dan padding adalah 20px.
    - Untuk layar yang lebih besar dari 1200px, ukuran font adalah 18px dan padding adalah 30px.

### Contoh Responsive Design

### CSS:

```css
body {
  font-family: Arial, sans-serif;
  font-size: 14px; /* Default untuk perangkat mobile */
  padding: 10px;
  background-color: white;
  color: black;
}

/* Tablet */
@media (min-width: 600px) {
  body {
    font-size: 16px;
    padding: 20px;
    background-color: lightyellow;
  }
}

/* Desktop */
@media (min-width: 1200px) {
  body {
    font-size: 18px;
    padding: 30px;
    background-color: lightgray;
  }
}
```

### HTML:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive Design Example</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <h1>Responsive Design</h1>
  <p>This is an example of responsive design using media queries and mobile-first design.</p>
</body>
</html>
```

### Penjelasan:

- **Default Styles:** Style default diterapkan untuk perangkat mobile dengan font-size 14px dan padding 10px.
- **Tablet Styles:** Ketika lebar layar mencapai 600px atau lebih besar, font-size meningkat menjadi 16px dan padding menjadi 20px, dengan background-color lightyellow.
- **Desktop Styles:** Ketika lebar layar mencapai 1200px atau lebih besar, font-size meningkat menjadi 18px dan padding menjadi 30px, dengan background-color lightgray.

**Lihat demo disini:**

https://codepen.io/Edwin-Anderson/pen/jOjPJpp

Dengan menggunakan media queries dan mobile-first design, kalian dapat membuat halaman web yang responsif dan adaptif, memastikan pengalaman pengguna yang optimal di berbagai perangkat dan ukuran layar.

**Note:**

Seperti yang sudah dijelaskan sebelumnya, jangan terlalu banyak ketergantungan dengan media query. Website by default sudah responsive. Contoh hal yang paling fatal adalah menggunakan static width untuk sesuatu yang tidak perlu.

Kalian tidak perlu mengganti `flex-direction` ke column pada mobile dan row pada desktop. Gunakan wrap yang dikombinasikan dengan `flex-grow`, `flex-shrink`, `flex-basis` untuk menghindari media query yang tidak perlu.

**Contohnya seperti ini:**

```css
display: flex;
flex-wrap: wrap;
flex: 1 0 fit-content;
```

Dengan ini kita tidak memerlukan media query untuk mengatur tata letak elemen karena properti `flex-wrap: wrap;` dan `flex: 1 0 fit-content;` akan secara otomatis menyesuaikan ukuran dan posisi elemen-elemen dalam kontainer fleksibel berdasarkan ruang yang tersedia.

---

# CSS Variables

CSS Variables, juga dikenal sebagai Custom Properties, adalah cara untuk menyimpan nilai yang dapat digunakan kembali di seluruh dokumen CSS Anda. Ini memungkinkan Anda untuk membuat CSS lebih modular, mudah dibaca, dan lebih mudah untuk dikelola.

### 1. Defining Variables

Variabel CSS didefinisikan menggunakan sintaks `--variablename` dan biasanya didefinisikan di dalam selektor `:root` untuk membuatnya tersedia di seluruh dokumen.

**Contoh:**

```css
:root {
  --main-bg-color: lightblue;
  --main-text-color: darkblue;
  --main-padding: 10px;
}
```

Pada contoh di atas, kita mendefinisikan tiga variabel: `--main-bg-color`, `--main-text-color`, dan `--main-padding`.

### 2. Using Variables

Untuk menggunakan variabel CSS, kita menggunakan fungsi `var(--variablename)`.

**Contoh:**

```css
body {
  background-color: var(--main-bg-color);
  color: var(--main-text-color);
  padding: var(--main-padding);
}
```

Pada contoh di atas, kita menggunakan variabel yang telah didefinisikan sebelumnya untuk menetapkan `background-color`, `color`, dan `padding` pada elemen `<body>`.

### 3. Scope and Inheritance

Variabel CSS mengikuti aturan scope dan inheritance yang mirip dengan properti CSS lainnya. Variabel dapat didefinisikan dalam konteks lokal (dalam elemen atau kelas tertentu) dan dapat mewarisi nilai dari parent elements.

**Global Scope (dalam):**

Variabel yang didefinisikan dalam `:root` akan dapat diakses di seluruh dokumen.

**Contoh:**

```css
:root {
  --main-bg-color: lightblue;
}
```

**Local Scope:**
Variabel yang didefinisikan dalam elemen atau kelas tertentu hanya dapat diakses di dalam konteks tersebut.

**Contoh:**

```css
.header {
  --header-bg-color: lightgreen;
}

.header {
  background-color: var(--header-bg-color);
}
```

Pada contoh di atas, `--header-bg-color` hanya dapat diakses dalam konteks `.header`.

**Inheritance:**
Variabel yang didefinisikan dalam konteks parent dapat diwarisi oleh child elements, kecuali jika child elements mendefinisikan variabel yang sama dengan nilai berbeda.

**Contoh:**

```css
:root {
  --main-bg-color: lightblue;
}

.container {
  --main-bg-color: lightgreen; /* Override nilai dari :root */
}

.child {
  background-color: var(--main-bg-color);
}
```

Pada contoh di atas, `--main-bg-color` didefinisikan dalam `:root` dengan nilai `lightblue`, tetapi di-override dalam `.container` dengan nilai `lightgreen`. `background-color` dalam `.child` akan menggunakan nilai `lightgreen` jika `.child` berada dalam `.container`.

### Contoh Penggunaan CSS Variables

**CSS:**

```css
:root {
  --main-bg-color: lightblue;
  --main-text-color: darkblue;
  --main-padding: 10px;
  --header-bg-color: lightgreen;
}

body {
  background-color: var(--main-bg-color);
  color: var(--main-text-color);
  padding: var(--main-padding);
}

.header {
  background-color: var(--header-bg-color);
  padding: var(--main-padding);
}

.container {
  --main-bg-color: lightcoral; /* Override nilai global */
}

.child {
  background-color: var(--main-bg-color); /* Menggunakan nilai dari .container jika berada di dalam .container, jika tidak menggunakan nilai dari :root */
}
```

**HTML:**

```html
<body>
  <div class="header">Header</div>
  <div class="container">
    <div class="child">Child inside container</div>
  </div>
  <div class="child">Child outside container</div>
</body>
```

### Penjelasan:

- **Defining Variables:** Variabel CSS didefinisikan dalam `:root` untuk global scope dan dalam elemen atau kelas tertentu untuk local scope.
- **Using Variables:** Variabel digunakan dengan `var(--variablename)`.
- **Scope and Inheritance:** Variabel mengikuti aturan scope dan inheritance CSS. Variabel yang didefinisikan dalam konteks parent dapat diwarisi oleh child elements kecuali jika di-override.

Dengan menggunakan variabel CSS, kalian dapat membuat kode CSS yang lebih modular, mudah dibaca, dan lebih mudah untuk dikelola, terutama dalam proyek besar dengan banyak elemen yang memerlukan konsistensi dalam styling.

Jika ada yang mau ditanyakan, silahkan chat melalui slack yaa, cheers!
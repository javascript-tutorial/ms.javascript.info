# Introduksi kepada JavaScript

Mari kita lihat apa yang istimewa tentang JavaScript, dan apa yang boleh kita capai dengannya dan teknologi lain yang boleh digunakan bersertanya.

## Apakah JavaScript?
>
*JavaScript* pada mulanya dicipta untuk "menjadikan halaman web berasa lebih hidup".

Program dalam bahasa pengaturcaraan ini dipanggil *penskripan* atau *skrip*. Ia boleh ditulis terus dalam HTML halaman web dan dijalankan secara automatik apabila halaman dimuatkan.

Skrip disediakan dan dilaksanakan sebagai teks biasa. Mereka tidak memerlukan persediaan atau kompilasi khas untuk dijalankan.

Dalam aspek ini, JavaScript sangat berbeza daripada bahasa pengaturcaraan lain yang dipanggil [Java](https://ms.wikipedia.org/wiki/Java).


```smart header="Why is it called <u>Java</u>Script?"
Apabila JavaScript dicipta, ia pada mulanya mempunyai nama lain: "LiveScript". Tetapi Java sangat popular pada masa itu, jadi diputuskan bahawa meletakkan bahasa baru sebagai "adik lelaki" Java akan membantu.

Tetapi apabila ia berkembang, JavaScript menjadi bahasa bebas sepenuhnya dengan spesifikasinya sendiri yang dipanggil [ECMAScript](https://ms.wikipedia.org/wiki/ECMAScript), dan kini ia tidak mempunyai kaitan langsung dengan Java.
```

Today, JavaScript can execute not only in the browser, but also on the server, or actually on any device that has a special program called [the JavaScript engine](https://en.wikipedia.org/wiki/JavaScript_engine).

Hari ini, JavaScript boleh melaksanakan bukan sahaja dalam pelayar internet, tetapi juga pada pelayan, atau apa sahaja yang mempunyai program khas yang dipanggil [enjin JavaScript](https://en.wikipedia.org/wiki/JavaScript_engine).

Pelayar mempunyai enjin terbenam kadangkala dipanggil "mesin virtual JavaScript".

Enjin yang berbeza mempunyai "nama kod" yang berbeza. Sebagai contoh:

- [V8](https://en.wikipedia.org/wiki/V8_(JavaScript_engine)) --  Chrome, Opera and Edge.
- [SpiderMonkey](https://en.wikipedia.org/wiki/SpiderMonkey) --  Firefox.
- ...Terdapat nama kod lain seperti "Chakra" untuk IE, "JavaScriptCore", "Nitro" dan "SquirrelFish" untuk Safari, dan lain lain.

Istilah di atas adalah baik untuk diingati kerana ia digunakan dalam artikel pembangun di internet. Kami akan menggunakannya juga. Sebagai contoh, jika "ciri X disokong oleh V8", maka ia mungkin berfungsi dalam Chrome, Opera dan Edge.

```smart header="Bagaimanakah enjin berfungsi?"

Enjin adalah rumit. Tetapi asasnya mudah.

1. Enjin (terbenam jika ia adalah penyemak imbas or replayer internet) membaca ("menghuraikan") skrip.
2. Kemudian ia menukar ("mengkompil") skrip kepada kod mesin.
3. Dan kemudian kod mesin berjalan dengan pantas

Enjin menggunakan pengoptimuman pada setiap langkah proses. Ia juga melihat skrip yang disusun semasa ia berjalan, menganalisis data yang mengalir melaluinya dan seterusnya mengoptimumkan kod mesin berdasarkan pengetahuan itu.
```
## Apakah yang boleh dilakukan oleh JavaScript dalam penyemak imbas?

JavaScript moden ialah bahasa pengaturcaraan "selamat". Ia tidak menyediakan akses peringkat rendah kepada memori atau CPU, kerana ia pada mulanya dicipta untuk pelayar yang tidak memerlukannya.

Keupayaan JavaScript sangat bergantung pada persekitaran ia berjalan. Contohnya, [Node.js](https://wikipedia.org/wiki/Node.js) menyokong fungsi yang membolehkan JavaScript membaca/menulis fail sewenang-wenangnya, melaksanakan permintaan rangkaian, dan lain-lain.

JavaScript dalam penyemak imbas boleh melakukan semua yang berkaitan dengan manipulasi halaman web, interaksi dengan pengguna dan pelayan web.

Sebagai contoh, JavaScript dalam penyemak imbas dapat:

- Tambah HTML baharu pada halaman, tukar kandungan sedia ada, ubah suai gaya.
- Bertindak balas kepada tindakan pengguna, jalankan pada klik tetikus, pergerakan penunjuk, penekanan kekunci.
- Hantar permintaan melalui rangkaian ke pelayan jauh, muat turun dan muat naik fail (yang dipanggil [AJAX](https://en.wikipedia.org/wiki/Ajax_(programming)) dan [COMET](https://en. wikipedia.org/wiki/Comet_(programming)) teknologi).
- Dapatkan dan tetapkan kuki, tanya soalan kepada pelawat, tunjukkan mesej.
- Ingat data pada bahagian klien ("storan tempatan").

## Apa yang TIDAK BOLEH dilakukan oleh JavaScript dalam penyemak imbas?

Kebolehan JavaScript dalam penyemak imbas adalah terhad untuk melindungi keselamatan pengguna. Matlamatnya adalah untuk menghalang halaman web jahat daripada mengakses maklumat peribadi atau merosakkan data pengguna.

Contoh sekatan tersebut termasuk:

- JavaScript pada halaman web tidak boleh membaca/menulis fail sewenang-wenangnya pada cakera keras, menyalinnya atau melaksanakan program. Ia tidak mempunyai akses langsung kepada fungsi OS.

    Penyemak imbas moden membenarkannya berfungsi dengan fail, tetapi akses adalah terhad dan hanya diberikan jika pengguna melakukan tindakan tertentu, seperti "menjatuhkan" fail ke dalam tetingkap penyemak imbas atau memilihnya melalui teg `<input>`.

    Terdapat cara untuk berinteraksi dengan kamera/mikrofon dan peranti lain, tetapi ia memerlukan kebenaran jelas pengguna. Jadi halaman yang didayakan JavaScript mungkin tidak secara senyap-senyap mendayakan kamera web, memerhati persekitaran dan menghantar maklumat kepada [NSA](https://en.wikipedia.org/wiki/National_Security_Agency).
- Tab/tetingkap yang berbeza secara amnya tidak mengetahui satu sama lain. Kadangkala mereka melakukannya, contohnya apabila satu tetingkap menggunakan JavaScript untuk membuka yang lain. Tetapi walaupun dalam kes ini, JavaScript dari satu halaman mungkin tidak mengakses halaman lain jika ia datang dari tapak yang berbeza (dari domain, protokol atau port yang berbeza).

    Ini dipanggil "Dasar Asal Sama". Untuk mengatasinya, *kedua-dua halaman* mesti bersetuju untuk pertukaran data dan mesti mengandungi kod JavaScript khas yang mengendalikannya. Kami akan membincangkannya dalam tutorial.

    Had ini, sekali lagi, untuk keselamatan pengguna. Halaman daripada `http://anysite.com` yang dibuka oleh pengguna mestilah tidak boleh mengakses tab penyemak imbas lain dengan URL `http://gmail.com`, sebagai contoh, dan mencuri maklumat dari sana.
- JavaScript boleh berkomunikasi dengan mudah melalui jaring ke pelayan tempat asal halaman semasa. Tetapi keupayaannya untuk menerima data daripada tapak/domain lain adalah lumpuh. Walaupun boleh, ia memerlukan persetujuan yang jelas (dinyatakan dalam pengepala HTTP) dari bahagian jauh. Sekali lagi, itu adalah had keselamatan.

![](limitations.svg)

Had limitasi tidak wujud jika JavaScript digunakan di luar penyemak imbas, contohnya pada pelayan. Pelayar moden juga membenarkan pemalam/sambungan yang mungkin meminta kebenaran lanjutan.

## Apakah yang menjadikan JavaScript unik atau istimewa?

Terdapat sekurang-kurangnya *tiga* perkara hebat tentang JavaScript:

```bandingkan
+ Penyepaduan penuh dengan HTML/CSS.
+ Perkara mudah dilakukan secara ringkas.
+ Disokong oleh semua pelayar utama dan didayakan secara lalai.
```
JavaScript adalah satu-satunya teknologi pelayar yang menggabungkan tiga perkara ini.

Itulah yang menjadikan JavaScript unik. Itulah sebabnya ia adalah alat yang paling meluas untuk mencipta antara muka penyemak imbas.

Walau bagaimanapun, JavaScript boleh digunakan untuk membuat pelayan, aplikasi mudah alih, dan lain lain.

## Bahasa pengaturcaraan yang berbeza daripda JavaScript

Sintaks JavaScript tidak sesuai dengan keperluan semua orang. Orang yang berbeza mahukan ciri yang berbeza.

Itu yang diharapkan, kerana projek dan keperluan adalah berbeza untuk setiap orang.

Jadi, baru-baru ini banyak bahasa baharu muncul, yang  (ditukar) kepada JavaScript sebelum ia dijalankan dalam penyemak imbas.

Alat moden menjadikan transpilasi sangat pantas dan telus, sebenarnya membenarkan pembangun mengodkan dalam bahasa lain dan menukarnya secara automatik "di bawah atap".

Contoh bahasa tersebut:

- [CoffeeScript](https://coffeescript.org/) ialah "gula sintaksis" untuk JavaScript. Ia memperkenalkan sintaks yang lebih pendek, membolehkan kami menulis kod yang lebih jelas dan lebih tepat. Biasanya, pengembang Ruby menyukainya.
- [TypeScript](https://www.typescriptlang.org/) menumpukan pada penambahan "penaipan data yang ketat" untuk memudahkan pembangunan dan sokongan sistem yang kompleks. Ia dibangunkan oleh Microsoft.
- [Flow](https://flow.org/) juga menambahkan penaipan data, tetapi dengan cara yang berbeza. Dibangunkan oleh Facebook.
- [Dart](https://www.dartlang.org/) ialah bahasa kendiri yang mempunyai enjin sendiri yang berjalan dalam persekitaran bukan penyemak imbas (seperti apl mudah alih), tetapi juga boleh ditranspilkan kepada JavaScript. Dibangunkan oleh Google.
- [Brython](https://brython.info/) ialah transpiler Python kepada JavaScript yang membolehkan penulisan aplikasi dalam Python tulen tanpa JavaScript.
- [Kotlin](https://kotlinlang.org/docs/reference/js-overview.html) ialah bahasa pengaturcaraan moden, ringkas dan selamat yang boleh menyasarkan penyemak imbas atau Node.

Terdapat banyak lagi. Sudah tentu, walaupun kita menggunakan salah satu daripada bahasa transpil ini, kita juga harus mengetahui JavaScript untuk benar-benar memahami perkara yang kita lakukan.

- ## Ringkasan

- JavaScript pada mulanya dicipta sebagai bahasa pelayar sahaja, tetapi ia kini digunakan dalam banyak persekitaran lain juga.
- Hari ini, JavaScript mempunyai kedudukan unik sebagai bahasa penyemak imbas yang paling banyak diterima pakai, disepadukan sepenuhnya dengan HTML/CSS.
- Terdapat banyak bahasa yang "dialihkan" kepada JavaScript dan mempunyai ciri tertentu. Adalah disyorkan untuk melihatnya, sekurang-kurangnya secara ringkas, selepas menguasai JavaScript.

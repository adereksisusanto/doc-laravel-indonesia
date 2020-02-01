# Catatan Rilis
<ul>
<li><a href="#skema-pembuatan-versi">Skema Pembuatan Versi</a></li>
<li><a href="#kebijakan-dukungan">Kebijakan Dukungan</a></li>
<li><a href="#laravel-6">Laravel 6</a></li>
</ul>

<h2><a href="#skema-pembuatan-versi">Skema Pembuatan Versi</a></h2>
Laravel dan paket pihak pertama lainnya mengikuti <a href="https://semver.org/">versi semantik</a>. Rilis kerangka utama dirilis setiap enam bulan (Februari dan Agustus), sementara rilis minor dan tambalan dapat dirilis sesering setiap minggu. Rilis minor dan tambalan tidak boleh berisi pemecahan perubahan.

Saat mereferensikan framework Laravel atau komponen-komponennya dari aplikasi atau paket Anda, Anda harus selalu menggunakan batasan versi seperti ^<b>6.0</b>, karena rilis utama Laravel menyertakan perubahan yang melanggar. Namun, kami berusaha untuk selalu memastikan Anda dapat memperbarui ke rilis utama baru dalam satu hari atau kurang.

<h2><a href="#kebijakan-dukungan">Kebijakan Dukungan</a></h2>
Untuk rilis LTS, seperti Laravel 6, perbaikan bug disediakan selama 2 tahun dan perbaikan keamanan disediakan selama 3 tahun. Rilis ini menyediakan jendela dukungan dan pemeliharaan terpanjang. Untuk rilis umum, perbaikan bug diberikan selama 6 bulan dan perbaikan keamanan disediakan selama 1 tahun. Untuk semua perpustakaan tambahan, termasuk Lumen, hanya rilis terbaru yang menerima perbaikan bug. Selain itu, tinjau versi database yang <a href="/database/getting_started.md">didukung oleh Laravel</a>.
<br>
<table>
<thead>
<tr>
<th> Versi </th>
<th> Rilis </th>
<th> Perbaikan Hingga Bug </th>
<th> Perbaikan Sampai Keamanan </th>
</tr>
</thead>
<tbody>
<tr>
<td> 5.5 (LTS) </td>
<td> 30 Agustus 2017 </td>
<td> 30 Agustus 2019 </td>
<td> 30 Agustus 2020 </td>
</tr>
<tr>
<td> 5.6 </td>
<td> 7 Februari 2018 </td>
<td> 7 Agustus 2018 </td>
<td> 7 Februari 2019 </td>
</tr>
<tr>
<td> 5.7 </td>
<td> 4 September 2018 </td>
<td> 4 Maret 2019 </td>
<td> 4 September 2019 </td>
</tr>
<tr>
<td> 5.8 </td>
<td> 26 Februari 2019 </td>
<td> 26 Agustus 2019 </td>
<td> 26 Februari, 2020 </td>
</tr>
<tr>
<td> 6 (LTS) </td>
<td> 3 September 2019 </td>
<td> 3 September 2021 </td>
<td> 3 September 2022 </td>
</tr>
</tbody>
</table>

<h2><a href="#laravel-6">Laravel 6</a></h2>
Laravel 6 (LTS) melanjutkan peningkatan yang dibuat di Laravel 5.8 dengan memperkenalkan versi semantik, kompatibilitas dengan <a href="https://vapor.laravel.com/">Laravel Vapor</a>, peningkatan respons otorisasi, middleware pekerjaan, koleksi malas, peningkatan subquery, ekstraksi perancah ujung depan ke paket komposer `laravel / framework`, dan berbagai perbaikan bug lainnya dan peningkatan kegunaan.

### Versi Semantik
Paket Laravel framework (`laravel / framework`) sekarang mengikuti standar <a href="https://semver.org/">versi semantik</a>. Ini membuat kerangka konsisten dengan paket Laravel pihak pertama lainnya yang sudah mengikuti standar versi ini. Siklus rilis Laravel akan tetap tidak berubah.

### Kompatibilitas Laravel Vapor
>Laravel Vapor dibangun oleh <a href="https://github.com/taylorotwell">Taylor Otwell</a>

Laravel 6 menyediakan kompatibilitas dengan <a href="https://vapor.laravel.com/">Laravel Vapor</a>, sebuah platform penyebaran tanpa server skala-otomatis untuk Laravel. Vapor mengabstraksikan kompleksitas mengelola aplikasi Laravel pada AWS Lambda, serta menghubungkan aplikasi-aplikasi tersebut dengan antrian SQS, basis data, klaster Redis, jaringan, CloudFront CDN, dan banyak lagi.

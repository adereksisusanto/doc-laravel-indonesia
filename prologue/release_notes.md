# Catatan Rilis
<ul>
<li><a href="#versioning-scheme">Skema Pembuatan Versi</a></li>
<li><a href="#support-policy">Kebijakan Dukungan</a></li>
<li><a href="#laravel-6">Laravel 6</a></li>
</ul>

<h2><a href="#versioning-scheme"># Skema Pembuatan Versi</a></h2>
Laravel dan paket pihak pertama lainnya mengikuti [Semantic Versioning](https://semver.org/). Rilis kerangka utama dirilis setiap enam bulan (Februari dan Agustus), sementara rilis minor dan tambalan dapat dirilis sesering setiap minggu. Rilis minor dan tambalan tidak boleh berisi pemecahan perubahan.

Saat mereferensikan framework Laravel atau komponen-komponennya dari aplikasi atau paket Anda, Anda harus selalu menggunakan batasan versi seperti ^<b>6.0</b>, karena rilis utama Laravel menyertakan perubahan yang melanggar. Namun, kami berusaha untuk selalu memastikan Anda dapat memperbarui ke rilis utama baru dalam satu hari atau kurang.

<h2><a href="#support-policy"># Kebijakan Dukungan</a></h2>
Untuk rilis LTS, seperti Laravel 6, perbaikan bug disediakan selama 2 tahun dan perbaikan keamanan disediakan selama 3 tahun. Rilis ini menyediakan jendela dukungan dan pemeliharaan terpanjang. Untuk rilis umum, perbaikan bug diberikan selama 6 bulan dan perbaikan keamanan disediakan selama 1 tahun. Untuk semua perpustakaan tambahan, termasuk Lumen, hanya rilis terbaru yang menerima perbaikan bug. Selain itu, tinjau versi database yang [didukung oleh Laravel](/database/getting_started.md).

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

<h2><a href="#laravel-6"># Laravel 6</a></h2>
Laravel 6 (LTS) melanjutkan peningkatan yang dibuat di Laravel 5.8 dengan memperkenalkan versi semantik, kompatibilitas dengan Laravel Vapor, peningkatan respons otorisasi, middleware pekerjaan, koleksi malas, peningkatan subquery, ekstraksi perancah ujung depan ke paket komposer `laravel / framework`, dan berbagai perbaikan bug lainnya dan peningkatan kegunaan.

### Versi Semantik
Paket Laravel framework (`laravel / framework`) sekarang mengikuti standar versi semantik. Ini membuat kerangka konsisten dengan paket Laravel pihak pertama lainnya yang sudah mengikuti standar versi ini. Siklus rilis Laravel akan tetap tidak berubah.

### Kompatibilitas Uap Laravel
>Laravel Vapor dibangun oleh <a href="https://github.com/taylorotwell">Taylor Otwell</a>

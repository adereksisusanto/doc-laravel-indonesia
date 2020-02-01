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

### Peningkatan Pengecualian Melalui Ignition
Laravel 6 dikirimkan bersama <a href="https://github.com/facade/ignition">Ignition</a>, laman detail pengecualian sumber terbuka baru yang dibuat oleh Freek Van der Herten dan Marcel Pociot. Pengapian menawarkan banyak manfaat dibandingkan rilis sebelumnya, seperti peningkatan file kesalahan Blade dan penanganan nomor baris, solusi runnable untuk masalah umum, pengeditan kode, berbagi pengecualian, dan peningkatan UX.

### Respons Otorisasi yang Ditingkatkan
>Respons otorisasi yang ditingkatkan diterapkan oleh <a href="https://github.com/garygreen">Gary Green</a>.

Dalam rilis Laravel sebelumnya, sulit untuk mengambil dan mengekspos pesan otorisasi khusus kepada pengguna akhir. Ini membuat sulit untuk menjelaskan kepada pengguna akhir persis mengapa permintaan tertentu ditolak. Di Laravel 6, ini sekarang jauh lebih mudah menggunakan pesan respons otorisasi dan metode `Gate::inspect` yang baru. Misalnya, diberikan metode kebijakan berikut:

```/**
 * Tentukan apakah pengguna dapat melihat penerbangan yang diberikan.
 *
 * @param  \App\User  $user
 * @param  \App\Flight  $flight
 * @return mixed
 */
public function view(User $user, Flight $flight)
{
    return $this->deny('Explanation of denial.');
}
```

Respon dan pesan kebijakan otorisasi dapat dengan mudah diambil menggunakan metode `Gate::inspect`:

```$response = Gate::inspect('view', $flight);

if ($response->allowed()) {
    // User is authorized to view the flight...
}

if ($response->denied()) {
    echo $response->message();
}
```

Selain itu, pesan khusus ini akan secara otomatis dikembalikan ke frontend Anda saat menggunakan metode pembantu seperti `$this->authorize` atau `Gate::authorize` dari rute atau pengontrol Anda.

### Job Middleware
>Middleware pekerjaan diimplementasikan oleh <a href="https://github.com/taylorotwell">Taylor Otwell</a>

Middleware Pekerjaan memungkinkan Anda untuk membungkus logika kustom di sekitar pelaksanaan pekerjaan yang antri, mengurangi boilerplate dalam pekerjaan itu sendiri. Misalnya, dalam rilis Laravel sebelumnya, Anda mungkin telah membungkus logika metode `handle` pekerjaan dalam panggilan balik tingkat terbatas:

```/**
 * Jalankan pekerjaan.
 *
 * @return void
 */
public function handle()
{
    Redis::throttle('key')->block(0)->allow(1)->every(5)->then(function () {
        info('Kunci diperoleh...');

        // Tangani pekerjaan...
    }, function () {
        // Tidak bisa mendapatkan kunci...

        return $this->release(5);
    });
}
```

Setelah membuat middleware, mereka mungkin dilampirkan ke pekerjaan dengan mengembalikannya dari metode `middleware` pekerjaan:

```use App\Jobs\Middleware\RateLimited;

/**
 * Dapatkan middleware yang harus dilewati pekerjaan.
 *
 * @ mengembalikan array
 */
public function middleware()
{
    return [new RateLimited];
}
```

### Koleksi Malas
>Koleksi malas diimplementasikan oleh <a href="https://github.com/JosephSilber">Joseph Silber</a>.

Banyak pengembang sudah menikmati <a href="/digging_deeper/collections">Koleksi metode</a> Laravel yang kuat. Untuk melengkapi kelas `Koleksi` yang sudah kuat, Laravel 6 memperkenalkan `LazyCollection`, yang memanfaatkan <a href="https://www.php.net/manual/en/language.generators.overview.php">generator</a> PHP untuk memungkinkan Anda bekerja dengan kumpulan data yang sangat besar sambil menjaga penggunaan memori tetap rendah.

Misalnya, bayangkan aplikasi Anda perlu memproses file log multi-gigabyte sambil mengambil keuntungan dari metode pengumpulan Laravel untuk mengurai log. Alih-alih membaca seluruh file ke memori sekaligus, koleksi malas dapat digunakan untuk menyimpan hanya sebagian kecil file dalam memori pada waktu tertentu:

```use App\LogEntry;
use Illuminate\Support\LazyCollection;

LazyCollection::make(function () {
    $handle = fopen('log.txt', 'r');

    while (($line = fgets($handle)) !== false) {
        yield $line;
    }
})
->chunk(4)
->map(function ($lines) {
    return LogEntry::fromLines($lines);
})
->each(function (LogEntry $logEntry) {
    // Memproses entri log ...
});
```

Atau, bayangkan Anda perlu mengulangi melalui 10.000 model Eloquent. Saat menggunakan koleksi Laravel tradisional, semua 10.000 model Eloquent harus dimuat ke memori pada saat yang sama:

```$users = App\User::all()->filter(function ($user) {
    return $user->id > 500;
});
```

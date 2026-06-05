# Dokumentasi Pustaka Komponen UI (Challenge 2)

Proyek ini berisi kumpulan komponen antarmuka (*User Interface*) yang dapat digunakan kembali (*reusable*) pada aplikasi Laravel menggunakan Blade Component dan Bootstrap 5. Semua komponen yang didokumentasikan di bawah ini dapat ditempatkan di folder `resources/views/components/ui/`.

---

## Panduan Penggunaan Component

### 1. Notification / Alert Component (`<x-ui.alert>`)
Komponen ini digunakan untuk menampilkan notifikasi singkat, misalnya hasil sukses, peringatan, atau pesan informasi.

**Properti yang tersedia:**
- `type`: `success`, `danger`, `warning`, `info` (default: `info`)
- `dismissible`: `true` / `false`

**Contoh penggunaan:**
```blade
<x-ui.alert type="success" dismissible="true">
    <strong>Berhasil!</strong> Data Anda telah disimpan dengan aman.
</x-ui.alert>

<x-ui.alert type="warning">
    Periksa kembali input yang Anda kirimkan sebelum lanjut.
</x-ui.alert>
```

**Kapan digunakan:**
- Menampilkan notifikasi setelah submit form
- Menunjukkan status proses atau validasi

---

### 2. Card Component (`<x-ui.card>`)
Komponen ini cocok untuk membungkus isi panel dengan bagian header, body, dan footer yang rapi.

**Slot yang tersedia:**
- `title`: judul card
- `body`: isi utama card
- `footer`: bagian bawah card

**Contoh penggunaan:**
```blade
<x-ui.card>
    <x-slot name="title">Profil Pengguna</x-slot>

    <x-slot name="body">
        <p>Nama: Budi Santoso</p>
        <p>Status: Aktif</p>
    </x-slot>

    <x-slot name="footer">
        <small class="text-muted">Terakhir diperbarui 5 menit lalu</small>
    </x-slot>
</x-ui.card>
```

**Kapan digunakan:**
- Menampilkan informasi profil, produk, atau dashboard widget
- Membuat layout panel yang konsisten di seluruh halaman

---

### 3. Badge / Label Component (`<x-ui.badge>`)
Komponen ini digunakan untuk memberi penanda status, kategori, atau label dengan warna yang dapat disesuaikan.

**Properti yang tersedia:**
- `color`: `primary`, `secondary`, `success`, `danger`, `warning`, `info`, `dark`
- `pill`: `true` / `false`

**Contoh penggunaan:**
```blade
<x-ui.badge color="success">Aktif</x-ui.badge>
<x-ui.badge color="warning" pill="true">Pending</x-ui.badge>
<x-ui.badge color="danger">Dibatalkan</x-ui.badge>
```

**Kapan digunakan:**
- Menandai status order, user, atau item
- Menampilkan kategori seperti VIP, Baru, Promo

---

### 4. Button Component (`<x-ui.button>`)
Komponen ini mempermudah pembuatan tombol dengan tampilan yang konsisten dan variasi style.

**Properti yang tersedia:**
- `variant`: `primary`, `secondary`, `outline`
- `type`: `button`, `submit`, `reset`
- `href`: jika ingin tombol menjadi link

**Contoh penggunaan:**
```blade
<x-ui.button variant="primary" type="submit">
    Simpan Data
</x-ui.button>

<x-ui.button variant="outline" href="/users">
    Kembali
</x-ui.button>

<x-ui.button variant="secondary">
    Batal
</x-ui.button>
```

**Kapan digunakan:**
- Tombol submit pada form
- Tombol aksi pada daftar data atau detail item

---

### 5. Breadcrumb Navigation Component (`<x-ui.breadcrumb>`)
Komponen ini digunakan untuk menampilkan jalur navigasi halaman agar pengguna tahu posisi mereka saat ini.

**Contoh penggunaan:**
```blade
<x-ui.breadcrumb
    :items="[
        ['label' => 'Beranda', 'url' => '/'],
        ['label' => 'Produk', 'url' => '/products'],
        ['label' => 'Detail Produk']
    ]" />
```

**Kapan digunakan:**
- Halaman dashboard yang memiliki sub-menu
- Halaman detail produk, artikel, atau transaksi

---

## Tips Penggunaan
- Gunakan komponen ini secara konsisten agar tampilan aplikasi tetap rapi dan seragam.
- Sesuaikan prop `color`, `variant`, dan `type` dengan kebutuhan halaman.
- Kombinasikan komponen seperti `card`, `badge`, dan `button` untuk membangun UI yang lebih menarik.


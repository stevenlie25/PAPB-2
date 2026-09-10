# ProfilApp - Tugas Praktikum PAPB Bab 2

Aplikasi Android sederhana berbasis Jetpack Compose untuk menampilkan halaman profil pengguna dan interaksi tombol *Follow*.

---

## 📝 Penjelasan Kode (`MainActivity.kt`)

Kode dikembangkan dari materi Modul 2 dengan beberapa penyesuaian:
- **`Column` Layout**: Mengatur susunan komponen secara vertikal. Menggunakan `horizontalAlignment = Alignment.CenterHorizontally` dan `verticalArrangement = Arrangement.Center` agar seluruh elemen tepat berada di tengah layar.
- **`Modifier.fillMaxSize()`**: Memastikan layout menyesuaikan dan memenuhi seluruh ukuran layar perangkat fisik.
- **Komponen & Typography**: Menampilkan `Image` profil berbentuk lingkaran (`CircleShape`) serta komponen `Text` dengan pengaturan `fontSize` berbeda untuk hirarki visual (Nama, NIM, Deskripsi).
- **State Management**: Fungsi `@Composable FollowButton` menggunakan `remember { mutableStateOf() }` untuk mengubah teks tombol secara otomatis antara *"Follow"* dan *"Unfollow"*.

---

## 💡 Analisis Praktis

**Perbandingan Jetpack Compose vs XML Layout:**
* **Jetpack Compose (Declarative UI)**: Tampilan ditulis langsung di Kotlin tanpa file XML terpisah. UI otomatis memperbarui diri ketika data/state berubah.
* **XML Layout (Imperative UI)**: Membutuhkan file XML terpisah dan dihubungkan ke Kotlin via `findViewById()`. Perubahan UI harus diatur manual setiap kali data berubah.

**Keuntungan Compose (Produktivitas & Pemeliharaan):**
1. **Kode Lebih Sedikit**: Bebas dari file XML terpisah dan panggilan `findViewById()`.
2. **Reusable**: UI berbentuk fungsi (`@Composable`) yang mudah dipanggil kembali di mana saja.
3. **Manajemen State Efisien**: UI otomatis memperbarui diri saat state berubah, membuat kode minim *bug* dan mudah dirawat.

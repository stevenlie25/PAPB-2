# Tugas Praktikum PAPB - Bab 2: Konsep Dasar UI Jetpack Compose

Aplikasi android sederhana berbasis Jetpack Compose yang menampilkan halaman profil pengguna beserta interaksi tombol Follow/Unfollow.

---

## 📝 Penjelasan Kode (`MainActivity.kt`)

Kode pada aplikasi ini disusun berdasarkan panduan pada Modul 2 dengan beberapa penyesuaian:

1. **Tata Letak & Komposisi Utama (`Column`)**:
   - Menggunakan `Column` untuk menyusun komponen UI secara vertikal[cite: 1].
   - **`horizontalAlignment = Alignment.CenterHorizontally`**: Mengatur seluruh komponen (Foto, Nama, NIM, Deskripsi, dan Tombol) berada di tengah secara horizontal[cite: 1].
   - **`verticalArrangement = Arrangement.Center`** *(Penyesuaian)*: Menambahkan pengaturan posisi vertikal agar seluruh komponen profil berada tepat di tengah-tengah layar secara vertikal.

2. **Pengaturan Ukuran & Ruang (`Modifier`)**:
   - **`modifier = Modifier.fillMaxSize()`** *(Penyesuaian)*: Mengatur agar tata letak `Column` memenuhi seluruh ukuran layar perangkat fisik/emulator secara fleksibel.
   - **`Modifier.padding(8.dp)`**: Memberikan jarak luar/padding di sekeliling area profil.
   - **`Spacer(modifier = Modifier.height(16.dp))`**: Memberikan jarak vertikal antara teks informasi dan tombol.

3. **Komponen Visual & Typography**:
   - **`Image`**: Menampilkan foto profil berbentuk lingkaran menggunakan `Modifier.clip(CircleShape)`[cite: 1].
   - **`Text` & Ukuran Font *(Penyesuaian)* **: Menambahkan properti `fontSize` dan `fontWeight` untuk membedakan hirarki teks (Nama dibuat lebih besar dan tebal `20.sp`, sedangkan NIM dan Deskripsi menggunakan `14.sp`).

4. **State Management (`FollowButton`)**:
   - Menggunakan `remember { mutableStateOf(false) }` untuk menyimpan status interaksi tombol (`isFollowed`)[cite: 1].
   - Saat tombol ditekan, nilai state berbalik (`!isFollowed`) dan teks secara otomatis berubah antara **"Follow"** dan **"Unfollow"**[cite: 1].

---

## 💡 Analisis Singkat: Jetpack Compose vs XML Layout

- **Lebih Ringkas & Bebas Boilerplate**: Compose tidak memerlukan pemanggilan `findViewById()` atau *view binding*. Semua UI dideklarasikan secara langsung menggunakan fungsi Kotlin (`@Composable`)[cite: 1].
- **UI Deklaratif**: Perubahan tampilan (seperti teks tombol saat di-klik) diatur secara otomatis berdasarkan perubahan data/state (`mutableStateOf`), tanpa perlu mengubah properti elemen secara manual seperti pada UI Imperatif XML[cite: 1].
- **Pemeliharaan Lebih Mudah**: Pengaturan komponen, tema, dan logika UI berada dalam satu lingkungan bahasa (Kotlin), sehingga lebih terstruktur dan mudah dipelihara.

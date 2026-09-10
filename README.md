# Tugas Praktikum PAPB - Bab 2: Konsep Dasar UI Jetpack Compose

Aplikasi Android sederhana berbasis Jetpack Compose yang menampilkan halaman profil pengguna beserta interaksi tombol Follow/Unfollow.

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

## 💡 Analisis Praktis

### **Perbandingan Jetpack Compose vs XML Layout (LinearLayout)**
- **Jetpack Compose**: Menggunakan pendekatan *Declarative UI*[cite: 1]. Kita cukup menuliskan UI-nya langsung di dalam bahasa Kotlin tanpa perlu file terpisah[cite: 1]. Jika data berubah, UI akan secara otomatis memperbarui dirinya sendiri[cite: 1].
- **XML Layout**: Menggunakan pendekatan *Imperative UI*[cite: 1]. Kita perlu membuat file terpisah (XML untuk tampilan, lalu dihubungkan dengan logika di Kotlin/Java menggunakan `findViewById()`)[cite: 1]. Properti tampilan harus diubah secara manual lewat logika tiap kali ada perubahan data[cite: 1].

### **Keuntungan Compose dari Sisi Produktivitas & Pemeliharaan Kode**
- **Kode jauh lebih sedikit**: Tidak perlu bolak-balik antara file XML dan Kotlin, serta tidak perlu lagi menulis kode panjang hanya untuk memanggil `findViewById()`, sebab semuanya langsung ditulis di satu tempat menggunakan Kotlin[cite: 1].
- **Komponen mudah dipakai ulang (Reusable)**: UI dibuat berupa fungsi (`@Composable`) yang bisa dipanggil kembali dengan mudah di mana saja layaknya fungsi biasa[cite: 1].
- **Perubahan state lebih efisien**: Tampilan layar langsung memperbarui dirinya sendiri saat data/state berubah, membuat logika penanganan UI jadi jauh lebih rapi, minim bug, dan gampang dirawat (*maintenance*)[cite: 1].

## docKeyword
Script python untuk mencari bagian tertentu dari file pdf besar berdasarkan suatu keyword. Script ini dimaksudkan untuk membantu menemukan informasi penting dari sebuah dokumen yang panjang.  
Kode dibuat setelah mata lelah membaca Perbup Penjabaran APBD yang panjang.

### Alur
- Ekstraksi teks dari PDF
- Pencarian keyword pilihan
- Memberikan konteks hasil

### ekstrak.py  
Memberi konteks pencarian dengan mengambil beberapa baris atau paragraf di sekitar kata kunci yang ditemukan (100 karakter sebelum dan sesudah kata kunci)

### konteks.py
Kesamaan alur dengan ekstrak.py namun dengan penyempurnaan konteks hasil.
- Penanganan tabel menggunakan tabula-py
- Menambahkan deteksi kata kunci yang berdekatan (dalam jarak 5 kata, bisa diubah)
- Mencatat nomor paragraf di mana kata kunci ditemukan
- Mendeteksi apakah kata kunci ditemukan dalam tabel
- Menggunakan tqdm untuk menampilkan progress bar saat memproses halaman PDF (waktu ekstrak jauh lebih lama)

### llama2.py
Analisa tambahan dari model llama 2. Retrieval berdasarkan kata kunci, bukan vektor.
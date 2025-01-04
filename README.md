# Spotify Genre Data Analysis

<div align="center">
<a href="https://github.com/ardhian9/pemesanan-hotel](https://github.com/nadityab/Spotify-Genre-Analysis">
        <img src="img/Spotify Genre Data Picture Overview.jpg" alt="Spotify Overview" width=600>
</a>
</div>

# Pendahuluan
  # Rumusan Masalah
Spotify adalah salah satu platform streaming musik terbesar di dunia dengan jutaan pengguna aktif setiap harinya. Platform ini menawarkan akses ke berbagai lagu dari berbagai genre dan menyediakan fitur untuk mengeksplorasi musik baru berdasarkan preferensi pengguna. Salah satu metrik yang menjadi fokus di Spotify adalah popularitas lagu. Popularitas ini diukur dengan berbagai indikator, termasuk jumlah streaming, tingkat interaksi pengguna, dan performa lagu dalam playlist.

Faktor-faktor yang memengaruhi popularitas lagu menjadi topik yang menarik untuk dianalisis, terutama dalam kaitannya dengan karakteristik audio seperti danceability, energy, tempo, dan valence. Selain itu, metadata seperti genre, subgenre, dan artis juga berpotensi memainkan peran penting dalam menentukan daya tarik sebuah lagu. Dengan memahami hubungan antara fitur-fitur ini dan tingkat popularitas lagu, kita dapat mengidentifikasi pola-pola tertentu yang dapat memberikan wawasan berharga bagi artis, label rekaman, hingga penyedia layanan streaming seperti Spotify.

Analisis ini juga memiliki dampak praktis. Misalnya, artis dapat menggunakan informasi ini untuk menyusun lagu yang lebih sesuai dengan preferensi audiens, sementara Spotify dapat mengoptimalkan algoritma rekomendasi untuk memberikan pengalaman mendengarkan yang lebih personal. Oleh karena itu, eksplorasi lebih mendalam tentang bagaimana fitur audio dan metadata memengaruhi popularitas lagu menjadi hal yang relevan dan bermanfaat dalam industri musik modern.

  # Rencana dan Metodologi
Metodologi yang akan digunakan meliputi beberapa langkah berikut:
a. Eksplorasi Data
Meninjau distribusi data dan nilai-nilai yang hilang.
Melakukan analisis deskriptif terhadap kolom-kolom utama, seperti popularitas dan danceability.
Mengidentifikasi kolom yang khas atau memiliki pengaruh signifikan terhadap popularitas.
b. Preprocessing Data
Membersihkan data, termasuk menangani data yang hilang dan outlier.
Normalisasi fitur numerik untuk memastikan keseragaman skala.
Encoding fitur kategorikal seperti genre untuk analisis lebih lanjut.
c. Analisis Data
Menggunakan analisis korelasi untuk memahami hubungan antara fitur audio dan popularitas.
Membuat visualisasi seperti scatter plot, heatmap, dan box plot untuk menunjukkan pola-pola menarik.
d. Modeling dan Prediksi
Membangun model regresi atau klasifikasi (contohnya, Random Forest, Decision Tree, atau Linear Regression) untuk memprediksi popularitas lagu berdasarkan fitur audio dan metadata.
Mengevaluasi performa model menggunakan metrik seperti RMSE (untuk regresi) atau akurasi (untuk klasifikasi).
e. Pembuatan Insight
Menarik kesimpulan tentang fitur audio dan metadata yang paling memengaruhi popularitas.
Mengidentifikasi pola dalam genre atau tahun rilis yang berkaitan dengan lagu populer.


# Dataset

Dataset yang digunakan dalam proyek ini berasal dari data Spotify Genre Data.. Dataset ini dapat diunduh melalui [tautan ini](https://www.dropbox.com/sh/qj0ueimxot3ltbf/AACzMOHv7sZCJsj3ErjtOG7ya?dl=1) dan Penjelasan Data bisa diakses [disini](https://github.com/rfordatascience/tidytuesday/blob/master/data/2020/2020-01-21/readme.md).Informasi lebih lanjut tersedia di deskripsi dataset tersebut.

Jumlah fitur : terdapat 23 fitur yang diambil.  
Jumlah data : ada 32.833 data yang didapatkan.  
Fitur yang digunakan :  

**track_id**: ID unik untuk setiap lagu, digunakan sebagai identifikasi dalam database Spotify.  
Contoh: 3n3Ppam7vgaVa1iaRUc9Lp.  

**track_name**: Nama lagu.  
Contoh: Shape of You.  

**track_artist**: Nama artis atau grup musik yang menyanyikan lagu.  
Contoh: Ed Sheeran.  

**track_popularity**: Popularitas lagu, diukur dengan skor 0–100 berdasarkan jumlah pemutaran dan interaksi pengguna.  
Contoh: 85.  

**track_album_id**: ID unik untuk album tempat lagu berada.  
Contoh: 6GZFiz5qZhI6t7ytrfqEpO.  

**track_album_name**: Nama album tempat lagu berada.  
Contoh: Divide.  

**track_album_release_date**: Tanggal rilis album tempat lagu berada, dalam format YYYY-MM-DD.  
Contoh: 2017-03-03.  

**playlist_name**: Nama playlist Spotify yang memuat lagu tersebut.  
Contoh: Top Hits 2023.  

**playlist_id**: ID unik untuk playlist tempat lagu ditemukan.  
Contoh: 37i9dQZF1DXcBWIGoYBM5M.  

**playlist_genre**: Genre utama playlist tempat lagu ditemukan, seperti Pop, Rock, atau EDM.  
Contoh: Pop.  

**playlist_subgenre**: Subgenre dari playlist tempat lagu ditemukan.  
Contoh: Dance Pop.  

**danceability**: Skor 0–1 yang mengukur seberapa cocok lagu untuk menari berdasarkan ritme, stabilitas beat, dan pola musik.  
Contoh: 0.85.  

**energy**: Skor 0–1 yang mengukur intensitas dan aktivitas lagu. Lagu dengan skor tinggi cenderung memiliki tempo cepat dan suara kuat.  
Contoh: 0.75.  

**key**: Nada dasar dari lagu (0–11), di mana 0 adalah C, 1 adalah C#, dan seterusnya.  
Contoh: 5 (F).  

**loudness**: Tingkat volume rata-rata lagu dalam desibel (dB).  
Contoh: -5.6.  

**mode**: Mode dari skala lagu, di mana 0 adalah minor dan 1 adalah mayor.  
Contoh: 1 (mayor).  

**speechiness**: Skor 0–1 yang menunjukkan keberadaan elemen vokal. Lagu dengan skor tinggi cenderung berupa pidato atau dialog.  
Contoh: 0.05.  

**acousticness**: Skor 0–1 yang mengukur sejauh mana lagu bersifat akustik.  
Contoh: 0.34.  

**instrumentalness**: Skor 0–1 yang menunjukkan apakah lagu hampir seluruhnya instrumental (tanpa vokal).  
Contoh: 0.91.  

**liveness**: Skor 0–1 yang mengukur kemungkinan lagu direkam di depan penonton langsung.  
Contoh: 0.12.  

**valence**: Skor 0–1 yang mengukur emosional lagu, di mana skor tinggi berarti lagu cenderung positif dan ceria.  
Contoh: 0.67.  

**tempo**: Kecepatan lagu dalam beat per minute (BPM).  
Contoh: 120.  

**duration_ms**: Durasi lagu dalam milidetik.  
Contoh: 210000 (3 menit 30 detik).  

### Langkah Pembersihan Data
<img src="img/Data Cleaning.jpg" alt="Data Cleaning" width="400"/>

1. Mengatasi nilai yang hilang:
   - Nilai hilang pada kolom track_name dan track_artist dihapus karena merepresentasikan string special yang tidak dapat diasal ataupun dinormalisasi.
2. Penghapusan baris:
   - Baris yang memiliki kolom kosong dihapus untuk konsistensi nilai dan menjaga orisinalitasnya.

## Package yang Digunakan
Berikut adalah package Python yang diperlukan untuk mereplikasi analisis:
- `zipfile`
- `os`
- `pandas`
- `matplotlib`
- `seaborn`
- `scipy.stats ` (opsional untuk analisis lanjutan)


## Metodologi
<img src="img/Data Workflow.jpg" alt="Data Workflow" width="600"/>

1. **Persiapan Data**:
   - Pengimporan dan pemeriksaan data mentah.
   - Pembersihan data, termasuk mengatasi nilai yang hilang dan normalisasi.
   - Penambahan variabel baru sesuai kebutuhan analisis.
   
2. **Eksplorasi Data**:
   - Deskriptif statistik pada variabel utama.
   - Visualisasi data untuk mengidentifikasi pola dan anomali.

3. **Analisis Data**:
   - Menggunakan teknik dasar analisis data untuk menjawab pertanyaan yang dirumuskan.
   - Visualisasi data yang informatif dan terstruktur.

4. **Rangkuman**:
   - Menyajikan temuan utama dalam analisis yang sudah dilakukan


## Struktur Repository
- `Tugas_Akhir_Analisis_Big_Data_Spotify_Genre_Data(162_183).ipynb`[![Colab](https://img.shields.io/badge/Colab-green)](https://colab.research.google.com/drive/1m98vKwC-LZ4VROws_SNUtEO5BTsCe98w?usp=sharing)
- `README.md`: Pengantar dan penjelasan proyek.
- `requirements.txt`: Daftar package Python yang diperlukan.

## Nama Kelompok
* Mochamad Irfan Sulifan (202110370311162)
* Nurrahman Aditya Budyanto (202110370311183)

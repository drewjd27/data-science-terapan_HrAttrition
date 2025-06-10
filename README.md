# Proyek Akhir: HR Analytics - Employee Attrition Prediction

## Business Understanding

Jaya Jaya Maju adalah perusahaan multinasional yang berdiri sejak tahun 2000 dengan lebih dari 1000 karyawan tersebar di seluruh negeri. Meskipun telah berkembang menjadi perusahaan besar, perusahaan menghadapi tantangan dalam manajemen sumber daya manusia, khususnya tingkat attrition yang tinggi (>10%).

### Permasalahan Bisnis

1. Tingginya tingkat attrition karyawan (>10%) yang dapat mempengaruhi stabilitas dan produktivitas perusahaan
2. Kebutuhan untuk mengidentifikasi faktor-faktor yang mempengaruhi attrition karyawan
3. Perlunya sistem monitoring yang efektif untuk mengawasi metrik-metrik terkait attrition

### Cakupan Proyek

1. Mengidentifikasi beberapa faktor yang mempengaruhi tingginya attrition rate. 
2. Pengembangan model machine learning untuk memprediksi kemungkinan attrition karyawan
3. Pembuatan dashboard bisnis untuk monitoring metrik-metrik terkait attrition
4. Penyusunan rekomendasi berdasarkan hasil analisis

### Persiapan

Sumber data: https://github.com/dicodingacademy/dicoding_dataset/tree/main/employee

Setup environment:

```bash
pip install -r requirements.txt
```

## Business Dashboard

Dashboard bisnis telah dibuat menggunakan Looker Studio untuk memvisualisasikan hubungan antara berbagai faktor dengan tingkat attrition karyawan. Dataset tersebut di ekspor dalam format csv dari notebook.ipynb dan setelah itu di import ke dalam Looker Studio. Pada looker studio ada penyesuaian dan modifikasi tipe data pada beberapa variabel. 

| ![Andrew Jonatan Damanik-dashboard](https://github.com/user-attachments/assets/655e02a9-6b44-49bf-9e98-81bf1139efa7) | 
|:--:| 
| *Distribusi Genre Film* |


### Isi dari Dashboard
- Dua Scorecard:
    - Scorecard 1: Menampilkan jumlah karyawan pada perusahaan
    - Scorecard 2: Menampilkan jumlah attrition karyawan pada perusahaan

- Dua Pie Chart:
    - Attrition Rate By Gender : Menampilkan proporsi karyawan yang attrition berdasarkan jenis kelamin. Hasilnya menunjukkan bahwa karyawan laki-laki (108) lebih banyak yang attrition daripada perempuan (71) . 
    - Attrition Rate By Marital Status : Menampilkan proporsi karyawan yang attrition berdasarkan status pernikahan. Hasilnya bahwa karyawan yang belum menikah/ single (94) lebih banyak yang attrition, kemudian diikuti oleh yang sudah menikah (62), dan terakhir yang bercerai (23).

- Empat Bar Chart:
    - Attrition By Department : Menampilkan proporsi karyawan yang attrition berdasarkan departemen di perusahaan tersebut. Hasilnya karyawan yang ada di department Research & Development (107) lebih banyak yang attrition, kemudian diikuti oleh department Sales (66), dan terakhir Human Resource (6).
    - Attrition By Over Time : Menampilkan proporsi karyawan yang attrition berdasarkan lembur atau tidak karyawan tersebut. Hasilnya karyawan yang lembur (98) lebih banyak yang attrition dibandingkan yang tidak lembur (81).
    - Attrition By Job Satisfaction Level : Menampilkan proporsi karyawan yang attrition berdasarkan tingkat kepuasan kerja karyawan tersebut. Kepuasan terhadap lingkungan kerja yang direpresentasikan oleh angka: 
        - 1-Low
        - 2-Medium
        - 3-High
        - 4-Very High
    Hasilnya karyawan yang memiliki kepuasan tinggi terhadap lingkungan kerja lebih banyak yang attrition (62), kemudian di urutan kedua diikuti oleh karyawan yang memiliki kepuasan rendah (46), kemudian karyawan yang memiliki kepuasan yang sangat tinggi (39), dan terakhir karyawan yang memiliki kepuasan yang sedang (32).
    - Attrition By Age Group : Menampilkan proporsi karyawan yang attrition berdasarkan kelompok umur karyawan tersebut. Ada tiga grup usia, yaitu:
        - 18-25
        - 26-45
        - 46-65
    Hasilnya, karyawan yang termasuk ke grup usia 26-45 (120) memiliki attrition yang paling tinggi, kemudian di urutan kedua adalah grup 18-25 (35) dan terakhir adalah grup 46-65 (24).

Dashboard dapat diakses melalui link berikut: https://lookerstudio.google.com/s/vBA_K9pAxzY

## Model Prediction

Model machine learning yang telah dikembangkan dapat digunakan untuk memprediksi kemungkinan attrition karyawan menggunakan script `predict.py`. 

### Cara Menggunakan Model Prediksi

1. Pastikan file model `model_predict_attrition.joblib` tersedia di direktori yang sama dengan `predict.py`

2. Jalankan script dengan perintah:
```bash
python predict.py
```

3. Format input data harus berupa list dengan 44 fitur dalam urutan yang sesuai. Contoh penggunaan:
```python
example_input = [0, 0, 0, 0, 1, 0, -1, 0, 1, 0, 1, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 1, 0, 0, 1, 1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 1, 0, 1, 0, 0]
```

4. Output prediksi akan menunjukkan "Yes" jika karyawan diprediksi akan mengalami attrition, dan "No" jika sebaliknya.

### Contoh Output
```
Predicted Attrition (Untuk Label Sebenarnya = no): No
```

## Conclusion
Jumlah karyawan yang keluar dari Perusahaan Jaya Jaya Maju adalah sebanyak 179 orang dari total 1058 karyawan atau apabila dipersentasekan sebanyak 16,9% dari total karyawan di perusahaan tersebut. 

1. Adapun beberapa faktor yang mempengaruhi karyawan untuk keluar dari perusahaan yaitu:
- Gender: Karyawan laki-laki (108) memiliki tingkat attrition lebih tinggi dibandingkan perempuan (71)

- Status Pernikahan: Karyawan single (94) memiliki tingkat attrition tertinggi, diikuti karyawan menikah (62), dan terakhir yang bercerai (23)

- Departemen: Research & Development memiliki tingkat attrition tertinggi (107), diikuti Sales (66), dan Human Resource (6)

- Overtime: Karyawan yang melakukan lembur (98) lebih banyak yang mengalami attrition dibanding yang tidak lembur (81)

- Kepuasan Kerja: 
   - High satisfaction: 62 karyawan
   - Low satisfaction: 46 karyawan
   - Very high satisfaction: 39 karyawan
   - Medium satisfaction: 32 karyawan

- Kelompok Usia:
   - Usia 26-45: 120 karyawan
   - Usia 18-25: 35 karyawan
   - Usia 46-65: 24 karyawan

2. Model machine learning Random Forest Classifier berhasil dikembangkan untuk memprediksi kemungkinan attrition karyawan, dengan script pythn `predict.py` untuk memprediksi karyawan yang berpotensi attrition.
3. Dashboard monitoring telah dibuat untuk membantu pengambilan keputusan HR.

### Rekomendasi Action Items

1. Evaluasi Beban Kerja Karyawan Lembur
    - Audit ulang beban kerja dan distribusinya.
    - Buat kebijakan lembur yang lebih ketat dan berbasis urgensi.
    - Sediakan kompensasi lembur yang kompetitif dan istirahat tambahan untuk yang sering lembur

2. Perkuat Strategi Retensi di Divisi R&D dan Sales
    - Lakukan exit interview terstruktur untuk memahami alasan dominan keluar di kedua departemen tersebut.
    - Tingkatkan coaching, pelatihan karier, dan peluang promosi internal di divisi ini.
    - Bentuk peer support group atau buddy system untuk meningkatkan ikatan tim.

3. Tingkatkan Kepuasan Kerja pada Level Menengah
    - Adakan focus group discussion untuk menggali alasan di balik kepuasan “tinggi tapi tidak cukup”.
    - Sesuaikan recognition program untuk lebih menghargai kontribusi mereka.
    - Perkuat jalur komunikasi antara manajemen dan karyawan.

4. Fokus pada Retensi Karyawan Usia 26–45 Tahun
    - Tawarkan fleksibilitas kerja dan program keseimbangan kerja-hidup (Work-Life Balance).
    - Perkenalkan career development plan yang jelas untuk fase pertengahan karier.
    - Tinjau kembali tunjangan keluarga dan asuransi.

5. Dukung Karyawan dengan Status Pernikahan Tertentu
    - Perluas program pengembangan pribadi dan komunitas internal bagi karyawan lajang.
    - Tawarkan benefit yang sesuai kebutuhan mereka (misalnya: pelatihan, mentoring, atau kursus tambahan).

6. Program Keseimbangan Gender dan Keberagaman
    - Monitor gender gap dalam kompensasi, promosi, dan pelatihan.
    - Bangun inclusive leadership program untuk menjaga kesetaraan.

H1D024006-PraktikumKB-Pertemuan9

Praktikum Kecerdasan Buatan — Pertemuan 9: Algoritma Genetika 1

================================================================================

IDENTITAS

Nama: BUNGA BUDI AMBAR WATI
NIM: H1D024006

================================================================================

DESKRIPSI

Program implementasi Algoritma Genetika untuk menyelesaikan Knapsack Problem (masalah memilih barang dengan keuntungan maksimal namun tidak melebihi kapasitas tas).

Program terdiri dari 6 file Python yang merepresentasikan setiap tahapan GA:

1. inisiasipopulasi.py - Membangkitkan populasi awal secara acak (kromosom biner)
2. EvaluasiFitness.py - Menghitung fitness berdasarkan total profit (penalti jika over kapasitas)
3. selection.py - Seleksi orang tua dengan Roulette Wheel dan Tournament Selection
4. crossover.py - Menghasilkan keturunan dengan One Point, Two Point, Uniform Crossover
5. mutation.py - Mutasi untuk menjaga keragaman (Swap, Inversion, Uniform)
6. main.py - Program utama yang menjalankan evolusi 50 generasi + menampilkan grafik

================================================================================

DATA BARANG

Barang 1: Profit = 60, Berat = 10
Barang 2: Profit = 100, Berat = 20
Barang 3: Profit = 120, Berat = 30
Barang 4: Profit = 90, Berat = 25
Barang 5: Profit = 69, Berat = 11
Barang 6: Profit = 70, Berat = 9
Barang 7: Profit = 80, Berat = 15
Barang 8: Profit = 90, Berat = 10
Barang 9: Profit = 25, Berat = 3

Kapasitas Maksimal Tas: 50

================================================================================

PARAMETER ALGORITMA

Jumlah Generasi: 50
Jumlah Populasi: 20
Probabilitas Crossover: 0.5
Probabilitas Mutasi: 0.1
Metode Seleksi: Roulette Wheel
Metode Crossover: One Point
Metode Mutasi: Swap
Elitism: 2 individu terbaik dibawa ke generasi berikutnya

================================================================================

PENJELASAN SINGKAT TIAP FILE

inisiasipopulasi.py:
Fungsi inisialisasi_populasi(jumlah_populasi, jumlah_gen) menghasilkan list berisi kromosom acak (0 dan 1) sebanyak jumlah_populasi. Setiap kromosom memiliki panjang jumlah_gen.

EvaluasiFitness.py:
Fungsi hitung_fitness(kromosom, barang, kapasitas) menjumlahkan profit barang yang dipilih (gen=1). Jika total berat > kapasitas, fitness = 0 (penalti). Jika tidak, fitness = total profit.

selection.py:
Dua fungsi seleksi:
- roulette_wheel_selection(): Memilih parent berdasarkan proporsi fitness (semakin besar fitness, semakin besar peluang terpilih).
- tournament_selection(): Memilih k individu acak, lalu mengambil yang fitness-nya tertinggi.

crossover.py:
Tiga fungsi crossover:
- one_point_crossover(): Potong di satu titik, tukar bagian belakang.
- two_point_crossover(): Potong di dua titik, tukar bagian tengah.
- uniform_crossover(): Setiap gen dipilih acak dari parent1 atau parent2 menggunakan mask.

mutation.py:
Tiga fungsi mutasi:
- swap_mutation(): Menukar dua posisi gen secara acak.
- inversion_mutation(): Membalik urutan gen dalam segmen tertentu.
- uniform_mutation(): Membalik nilai gen (0->1 atau 1->0) dengan probabilitas tertentu.

main.py:
Program utama yang menjalankan semua tahapan secara berulang selama 50 generasi. Menampilkan grafik perkembangan fitness (tertinggi biru, rata-rata merah, terendah kuning) dan mencetak hasil akhir berupa barang-barang terpilih.

================================================================================

CARA MENJALANKAN

1. Pastikan semua file .py berada dalam satu folder yang sama

2. Install library yang diperlukan:
   pip install matplotlib numpy

3. Jalankan program utama:
   python main.py

================================================================================

HASIL PROGRAM
Figure_1.png
Contoh output yang muncul di terminal:

Nilai Fitness Terbaik: 329
Total Bobot: 50
Barang Terpilih:
- Barang2
- Barang5
- Barang6
- Barang8

Selain itu, program juga menampilkan grafik perkembangan fitness dari generasi 1 sampai 50.

================================================================================

REPOSITORY GITHUB

https://github.com/bungabudia9-spec/H1D024006_PraktikumKB_Pertemuan9

================================================================================


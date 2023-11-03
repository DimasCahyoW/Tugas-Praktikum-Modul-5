# Tugas-Praktikum-Modul-5
# 1.	Pelajari class EightPuzzleSearch, EightPuzzleSpace, dan Node!
•	EightPuzzleSearch adalah kelas yang mengelola pencarian solusi untuk masalah puzzle delapan dengan menggunakan algoritma. Kelas ini menggunakan `EightPuzzleSpace` untuk merepresentasikan keadaan puzzle dan `Node` untuk merepresentasikan simpul-simpul dalam pohon pencarian.
•	EightPuzzleSpace adalah kelas atau struktur data yang merepresentasikan ruang keadaan dalam puzzle delapan, termasuk keadaan awal, keadaan tujuan, dan kemungkinan langkah antara keadaan-keadaan tersebut. Biasanya menggunakan matriks atau larik untuk merepresentasikan keadaan puzzle delapan.
•	Node adalah kelas atau struktur data yang merepresentasikan simpul-simpul dalam pohon pencarian. Setiap simpul memiliki atribut seperti keadaan, tautan ke simpul-simpul lain, biaya jalur, dan skor heuristik (jika digunakan algoritma seperti A*). Digunakan untuk melacak dan mengorganisir pencarian dan mengidentifikasi solusi serta menghitung biaya terkait.

# 2.	Ubahlah initial dan goal state dari program di atas sehingga bentuk initial dan goal statenya Gambar 8. Kemudian tentukan langkah-langkah mana saja sehingga puzzlenya mencapai goal state. Analisa dan bedakan dengan solusi pada point 1!
Dalam kode Eight Puzzle yang telah diberikan, langkah-langkah untuk mencapai keadaan tujuan dari keadaan awal dapat ditemukan dalam class EightPuzzleSearch. Class ini bertanggung jawab untuk mencari solusi dengan menggunakan algoritma pencarian A* dan memungkinkan pengguna untuk memilih heuristic yang akan digunakan baik itu h1 atau h2. Proses pencarian solusi melibatkan beberapa tahap berikut:

1.	Inisialisasikan keadaan awal dan keadaan tujuan.
2.	Kemudian buat node awal (root) menggunakan keadaan awal tersebut.
3.	Masukkan node awal ke dalam daftar open.
4.	Selama daftar open belum kosong ikuti langkah berikut:
a.	Pilih node dengan biaya terendah, yang dihitung berdasarkan heuristic dan panjang path.
b.	Tambahkan node terpilih ke dalam daftar closed untuk menghindari pengulangan.
c.	Jika node terpilih sama dengan keadaan tujuan, maka solusi telah ditemukan, dan proses berakhir.
d.	Dapatkan semua node penerus dari node terpilih. 
e.	Untuk setiap node penerus, hitung biaya baru berdasarkan heuristic, panjang path, dan biaya sebelumnya.
f.	Jika node penerus belum pernah ada di daftar open atau memiliki biaya lebih rendah, tambahkan node penerus ke daftar open dengan biaya yang telah diperbarui.

Tahapan ini akan terus diulang sampai solusi ditemukan atau semua kemungkinan solusi dieksplorasi. Hasil akhir dari pencarian akan mencetak langkah-langkah solusi ke dalam output. Penting untuk dicatat bahwa class EightPuzzleSearch, EightPuzzleSpace, dan Node bekerja sama untuk mencari dan mengeksekusi solusi Eight Puzzle. Class EightPuzzleSearch mengatur logika pencarian, EightPuzzleSpace memberikan informasi tentang keadaan awal dan keadaan tujuan, serta menghasilkan node-node awal, sementara class Node digunakan untuk merepresentasikan setiap keadaan dalam permainan Eight Puzzle dan menyimpan informasi penting tentang keadaan tersebut, biayanya, dan node induknya.

# 3.	Ubahlah initial dan goal state dari program di atas sehingga bentuk initial dan goal statenya Gambar 5.9. Kemudian tentukan langkah-langkah mana saja sehingga puzzlenya mencapai goal state. Analisa dan bedakan dengan solusi pada point 1 dan 2! 
Dalam algoritma ini, terdapat dua heuristik yang dapat digunakan, yaitu h1Cost dan h2Cost, yang akan memengaruhi cara algoritma berjalan. Berikut adalah langkah-langkah yang perlu diikuti untuk mencapai keadaan tujuan dalam kode tersebut:
a.	Kondisi Awal (Root)
Kondisi awal puzzle adalah {1, 5, 3, 4, 6, 8, 2, 7, 0}.
b.	Kondisi Goal
Kondisi tujuan yang harus dicapai adalah {7, 6, 5, 8, 0, 4, 1, 2, 3}.
c.	Jalannya Algoritma:
•	Algoritma A* dimulai dengan kondisi awal (Root).
•	Algoritma memeriksa semua kemungkinan langkah dari kondisi awal, mempertimbangkan posisi kotak kosong, dan menggunakan salah satu heuristik (h1Cost atau h2Cost) untuk menghitung biaya.
•	Algoritma mencari jalur paling efisien menuju keadaan tujuan dengan mempertimbangkan biaya total (biaya heuristik, jarak yang sudah ditempuh, dan biaya sebelumnya).
•	Setiap langkah yang diambil untuk mencapai keadaan tujuan dipilih berdasarkan prioritas biaya terendah, yang ditentukan oleh heuristik yang digunakan.
•	Algoritma terus berjalan hingga mencapai keadaan tujuan.

Penggunaan heuristik h1Cost dan h2Cost akan memengaruhi perhitungan biaya dan cara algoritma berjalan. Kedua heuristik ini dapat menghasilkan solusi yang berbeda dalam beberapa kasus. Heuristik h1Cost menghitung biaya dengan menghitung jumlah angka yang tidak berada pada posisi yang benar, sementara h2Cost menghitung biaya berdasarkan jarak Manhattan antara angka yang salah dengan posisi yang benar.

# 4.	Ubahlah initial dan goal state dari program di atas sehingga bentuk initial dan goal statenya Gambar 5.10. Kemudian tentukan langkah-langkah mana saja sehingga puzzlenya mencapai goal state. Analisa dan bedakan dengan solusi pada point 1, 2, dan 3! 
Penerapan algoritma A* untuk menyelesaikan masalah 8-puzzle. Dalam implementasi ini, ada dua pilihan heuristik, yaitu h1Cost dan h2Cost, yang mempengaruhi alur algoritma. Heuristik ini digunakan untuk menghitung biaya setiap langkah dalam pencarian solusi dan untuk menentukan langkah-langkah yang harus diambil untuk mencapai keadaan akhir dan membandingkannya dengan solusi pada poin 1, code 1, dan code 2. Berikut adalah langkah-langkah untuk menentukan solusi 8-puzzle dengan menggunakan implementasi di "code 3":
1.	Kondisi Awal (Root)
{1, 2, 3, 4, 5, 6, 7, 8, 0}
2.	Kondisi Goal
{1, 2, 3, 4, 0, 5, 6, 7, 8}
3.	Alur Algoritma
a.	Algoritma A* dimulai dengan kondisi awal (Root).
b.	Algoritma mencari langkah-langkah untuk mencapai keadaan akhir (Goal).
c.	Algoritma menggunakan salah satu heuristik, yaitu h1Cost atau h2Cost, untuk menghitung biaya setiap langkah.
d.	Algoritma memilih langkah-langkah yang memiliki biaya terendah berdasarkan heuristik yang dipilih.
e.	Algoritma terus berjalan hingga mencapai keadaan akhir (Goal).

Perbandingan dengan solusi pada poin 1, code 1, dan code 2
1.	Solusi pada poin 1, code 1, dan code 2 juga menggunakan algoritma A* untuk menyelesaikan masalah 8-puzzle, namun mungkin menggunakan heuristik yang berbeda.
2.	Perbedaan heuristik yang digunakan dapat mempengaruhi urutan langkah-langkah dan waktu yang dibutuhkan untuk mencapai keadaan akhir (Goal).
Solusi dalam "code 3" di atas akan memberikan langkah-langkah spesifik yang mengarah ke keadaan akhir {1, 2, 3, 4, 0, 5, 6, 7, 8} berdasarkan heuristik yang dipilih (h1Cost atau h2Cost). Langkah-langkah tersebut dapat ditemukan dalam keluaran dari implementasi "code 3" setelah dijalankan.

# 5.	Ubahlah initial dan goal state dari program dan class-class di atas sehingga bentuk initial dan goal statenya Gambar 5.11. Kemudian tentukan langkah-langkah mana saja sehingga puzzlenya mencapai goal state!
Dalam menentukan langkah-langkah mencapai keadaan akhir pada Code 4 untuk puzzle, maka dapat mengimplementasikan algoritma pencarian seperti A* Search dan memanfaatkan dua heuristik, yaitu h1Cost dan h2Cost yang telah ditentukan dalam kode. Berikut adalah langkah-langkah umum yang dapat diikuti:
1.	Mulailah dengan menginisialisasi node awal menggunakan keadaan awal dari puzzle.
2.	Selanjutnya, persiapkan dua daftar: open list dan closed list. Letakkan node awal di dalam open list.
3.	Lakukan langkah-langkah berikut selama open list masih memiliki elemen di dalamnya: a. Pilih node dengan biaya terendah dari open list (biaya f = biaya heuristik + panjang path). b. Jika node yang dipilih adalah keadaan akhir (goal state), maka itu berarti puzzle telah selesai. Anda dapat mengakhiri proses pencarian. c. Selanjutnya, hasilkan semua node turunan dari node saat ini. d. Untuk setiap node turunan, hitung biaya f (menggunakan salah satu dari h1Cost atau h2Cost) dan panjang jalur dari node awal hingga node saat ini. e. Jika node turunan sudah ada dalam open list dan biaya f yang baru lebih rendah, maka perbarui biaya dan orang tua (parent) dari node tersebut. f. Jika node turunan sudah ada dalam closed list dan biaya f yang baru lebih rendah, perbarui biaya dan orang tua dari node tersebut, dan pindahkan node dari closed list ke dalam open list. g. Jika node turunan belum ada dalam kedua daftar (open list dan closed list), tambahkan node tersebut ke dalam open list. h. Akhirnya, tandai node saat ini sebagai telah dieksplorasi dengan memindahkannya dari open list ke dalam closed list.

Dengan mengikuti langkah-langkah di atas, maka dapat mengimplementasikan algoritma A* Search untuk mencapai keadaan akhir dalam puzzle Code 4.

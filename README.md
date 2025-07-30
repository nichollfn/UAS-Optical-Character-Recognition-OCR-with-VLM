Nama : Niicholas Aditya Fernando N
Nim : 4222201035
Kelas : Robotika A Pagi Sem 6

# Indonesian License Plate OCR with VLM (Google Gemma 3 4B via LMStudio)

Proyek ini menggunakan **Visual Language Model (VLM)** melalui **LMStudio** untuk melakukan Optical Character Recognition (OCR) pada plat nomor kendaraan Indonesia. Model yang digunakan adalah `google/gemma-3-4b`. Evaluasi dilakukan menggunakan metrik **Character Error Rate (CER)**.

## Dataset

- **Sumber**: [Kaggle - Indonesian License Plate Dataset](https://www.kaggle.com/datasets/juanthomaswijaya/indonesianlicense-plate-dataset)
- **Folder yang digunakan**: `test`

## Konsep

Visual Language Model (VLM) adalah model AI multimodal yang dapat memahami input berupa **gambar** dan menghasilkan **teks**. Dalam proyek ini, model digunakan untuk membaca isi plat nomor dari gambar.

## Alur Sistem

1. Input gambar dari folder `test/` dikirim ke LMStudio.
2. LMStudio memproses gambar menggunakan model `google/gemma-3-4b`.
3. Prompt yang digunakan: `What is the license plate number shown in this image? Respond only with the plate number.`
4. Model mengembalikan hasil prediksi plat nomor.
5. Program menghitung **Character Error Rate (CER)** berdasarkan label ground truth.
6. Hasil disimpan ke dalam file `results.csv`.

## Rumus 
1. CER = (S + D + I) / N

S: Substitusi karakter salah
D: Karakter yang dihapus (Deletion)
I: Karakter yang ditambahkan (Insertion)
N: Jumlah karakter pada ground truth


## Format Output (results.csv)

```csv
image,ground_truth,prediction,CER_score
image001.jpg,B1234XYZ,B1234XY2,0.125





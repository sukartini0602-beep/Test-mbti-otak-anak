<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tes Tipe Otak Anak</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f0f8ff;
            color: #333;
            margin: 0;
            padding: 20px;
            display: flex;
            justify-content: center;
        }
        .container {
            background: white;
            padding: 30px;
            border-radius: 12px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            max-width: 500px;
            width: 100%;
        }
        h1 {
            color: #2c3e50;
            text-align: center;
            font-size: 24px;
        }
        p.subtitle {
            text-align: center;
            color: #7f8c8d;
            margin-bottom: 25px;
        }
        .section-title {
            font-weight: bold;
            color: #2980b9;
            margin-top: 20px;
            border-bottom: 2px solid #ecf0f1;
            padding-bottom: 5px;
        }
        .checkbox-group {
            margin: 15px 0;
        }
        .checkbox-item {
            display: flex;
            align-items: flex-start;
            margin-bottom: 12px;
            cursor: pointer;
        }
        .checkbox-item input {
            margin-right: 12px;
            margin-top: 4px;
            transform: scale(1.2);
        }
        button {
            width: 100%;
            background-color: #2ecc71;
            color: white;
            border: none;
            padding: 12px;
            font-size: 16px;
            font-weight: bold;
            border-radius: 6px;
            cursor: pointer;
            transition: background 0.3s;
            margin-top: 20px;
        }
        button:hover {
            background-color: #27ae60;
        }
        #result {
            margin-top: 25px;
            padding: 15px;
            border-radius: 6px;
            background-color: #f9f9f9;
            border-left: 5px solid #2980b9;
            display: none;
        }
        #result h3 {
            margin-top: 0;
            color: #2c3e50;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>🧠 Tes Tipe Otak Anak</h1>
    <p class="subtitle">Pilihlah pernyataan di bawah ini yang paling sesuai dengan kebiasaan anak Anda.</p>

    <form id="quizForm">
        <!-- KELOMPOK OTAK KIRI -->
        <div class="section-title">Kecenderungan A</div>
        <div class="checkbox-group">
            <label class="checkbox-item">
                <input type="checkbox" class="otak-kiri">
                <span>Anak suka merapikan mainan sesuai dengan warna atau ukurannya.</span>
            </label>
            <label class="checkbox-item">
                <input type="checkbox" class="otak-kiri">
                <span>Lebih mudah memahami instruksi yang jelas dan bertahap (step-by-step).</span>
            </label>
            <label class="checkbox-item">
                <input type="checkbox" class="otak-kiri">
                <span>Sangat menyukai permainan angka, puzzle, atau menyusun balok logika.</span>
            </label>
        </div>

        <!-- KELOMPOK OTAK KANAN -->
        <div class="section-title">Kecenderungan B</div>
        <div class="checkbox-group">
            <label class="checkbox-item">
                <input type="checkbox" class="otak-kanan">
                <span>Anak suka menggambar bebas atau mencoret-coret dengan imajinasi sendiri.</span>
            </label>
            <label class="checkbox-item">
                <input type="checkbox" class="otak-kanan">
                <span>Sering membuat cerita karangan atau bermain peran (roleplay).</span>
            </label>
            <label class="checkbox-item">
                <input type="checkbox" class="otak-kanan">
                <span>Sangat peka terhadap musik, suka bernyanyi, atau menari secara spontan.</span>
            </label>
        </div>

        <button type="button" onclick="hitungHasil()">Lihat Hasil Analisis</button>
    </form>

    <div id="result">
        <h3 id="resultTitle">Hasil Analisis:</h3>
        <p id="resultText"></p>
    </div>
</div>

<script>
    function hitungHasil() {
        // Menghitung berapa banyak checklist di masing-masing kategori
        const kiri = document.querySelectorAll('.otak-kiri:checked').length;
        const kanan = document.querySelectorAll('.otak-kanan:checked').length;
        
        const resultDiv = document.getElementById('result');
        const resultText = document.getElementById('resultText');

        // Menentukan hasil berdasarkan jumlah checklist terbanyak
        if (kiri === 0 && kanan === 0) {
            resultText.innerHTML = "Silakan pilih minimal satu pernyataan terlebih dahulu untuk melihat hasil!";
            resultDiv.style.borderLeftColor = "#e74c3c";
        } else if (kiri > kanan) {
            resultText.innerHTML = "<strong>Dominan Otak Kiri (Analitis):</strong> Anak Anda cenderung berpikir logis, sistematis, menyukai struktur, matematika, dan bahasa. Mereka biasanya belajar dengan baik melalui instruksi tertulis dan fakta.";
            resultDiv.style.borderLeftColor = "#2980b9";
        } else if (kanan > kiri) {
            resultText.innerHTML = "<strong>Dominan Otak Kanan (Kreatif):</strong> Anak Anda cenderung kreatif, imajinatif, menyukai seni, visual, dan musik. Mereka biasanya lebih mudah memahami sesuatu lewat gambar atau praktik langsung.";
            resultDiv.style.borderLeftColor = "#9b59b6";
        } else {
            resultText.innerHTML = "<strong>Seimbang (Otak Kiri & Kanan):</strong> Anak Anda menunjukkan keseimbangan yang sangat baik antara pemikiran logis dan kreativitas. Mereka bisa beradaptasi dengan berbagai metode belajar.";
            resultDiv.style.borderLeftColor = "#2ecc71";
        }

        // Menampilkan kotak hasil
        resultDiv.style.display = 'block';
        
        // Scroll otomatis ke bagian hasil
        resultDiv.scrollIntoView({ behavior: 'smooth' });
    }
</script>

</body>
</html>

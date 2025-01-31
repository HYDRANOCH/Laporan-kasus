<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=2.0">
    <title>Laporan Kasus Sekolah</title>
    <style>
        /* Tambahkan CSS Anda di sini */
    </style>
</head>
<body>
    <header>
        <h1>Laporan Kasus Sekolah</h1>
    </header>
    <main>
        <section>
            <h2>Pilih Jenis Kasus</h2>
            <ul>
                <li><a href="#" class="lapor" data-kasus="Bullying">Bullying</a></li>
                <li><a href="#" class="lapor" data-kasus="Pencurian">Pencurian</a></li>
                <li><a href="#" class="lapor" data-kasus="Kekerasan">Kekerasan</a></li>
                <li><a href="#" class="lapor" data-kasus="Lain-lain">Lain-lain</a></li>
            </ul>
        </section>
        <section class="form-laporan" style="display:none;">
            <h2>Form Laporan</h2>
            <form>
                <label for="nama">Nama:</label>
                <input type="text" id="nama" name="nama"><br><br>
                <label for="kelas">Kelas:</label>
                <input type="text" id="kelas" name="kelas"><br><br>
                <label for="kasus">Kasus:</label>
                <input type="text" id="kasus" name="kasus" readonly><br><br>
                <label for="keterangan">Keterangan:</label>
                <textarea id="keterangan" name="keterangan"></textarea><br><br>
                <button id="kirim-laporan">Kirim Laporan</button>
            </form>
        </section>
    </main>
    <script>
        const lapor = document.querySelectorAll('.lapor');
        const formLaporan = document.querySelector('.form-laporan');
        const kasusInput = document.querySelector('#kasus');
        const kirimLaporan = document.querySelector('#kirim-laporan');

        lapor.forEach((item) => {
            item.addEventListener('click', () => {
                formLaporan.style.display = 'block';
                kasusInput.value = item.getAttribute('data-kasus');
            });
        });

        kirimLaporan.addEventListener('click', () => {
            const nama = document.querySelector('#nama').value;
            const kelas = document.querySelector('#kelas').value;
            const kasus = kasusInput.value;
            const keterangan = document.querySelector('#keterangan').value;

            // Kirim laporan ke polisi melalui API atau email
            fetch('/api/laporan', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify({ nama, kelas, kasus, keterangan })
            })
            .then((res) => res.json())
            .then((data) => console.log(data))
            .catch((err) => console.error(err));
        });
    </script>
</body>
</html>

<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=2.0">
    <title>Laporan Kasus Sekolah</title>
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
                

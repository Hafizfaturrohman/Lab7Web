# Lab7Web
1. php_dasar.php
   
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>PHP Dasar</title>
</head>
<body>
    <h1>Belajar PHP Dasar</h1>

    <?php
    echo "Hello World<br><br>";

    echo "<strong style='font-size: larger;'>Menggunakan Variable</strong><br><br>";

    $nim = "312210375";
    $nama = 'Hafiz Faturrohman';
    echo "NIM: $nim<br>";
    echo "Nama: $nama<br>";
    ?>
</body>
</html>

Tampilan Gambar
   ![Screenshot 2023-11-15 011359](https://github.com/Hafizfaturrohman/Lab7Web/assets/115616365/0b1a2625-0334-4644-a9eb-f318cffb2e89)

2. latihan2.php

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>PHP Dasar</title>
</head>
<body>
<h2>Form Input</h2>
<form method="post">
    <label>Nama: </label>
    <input type="text" name="nama">
    <input type="submit" value="Kirim">
</form>
<?php
echo 'Selamat Datang ' . $_POST['nama'];
?>

    <h2>Operator</h2>

    <?php
    $gaji = 1000000;
    $pajak = 0.1;
    $thp = $gaji - ($gaji * $pajak);
    echo "Gaji sebelum pajak = Rp. $gaji <br>";
    echo "Gaji yang dibawa pulang = Rp. $thp";
    ?>

    <h2>Kondisi IF</h2>

    <?php
    $nama_hari = date("l");
    if ($nama_hari == "Sunday") {
        echo "Minggu";
    } elseif ($nama_hari == "Monday") {
        echo "Senin";
    } else {
        echo "Selasa";
    }
    ?>

    <h2>Kondisi Switch</h2>

    <?php
    switch ($nama_hari) {
        case "Sunday":
            echo "Minggu";
            break;
        case "Monday":
            echo "Senin";
            break;
        case "Tuesday":
            echo "Selasa";
            break;
        default:
            echo "Sabtu";
    }
    ?>

    <h2>Perulangan for</h2>

    <?php
    echo "Perulangan 1 sampai 10 <br />";
    for ($i=1; $i<=10; $i++) {
        echo "Perulangan ke: " . $i . '<br />';
    }
    
    echo "Perulangan Menurun dari 10 ke 1 <br />";
    for ($i=10; $i>=1; $i--) {
        echo "Perulangan ke: " . $i . '<br />';
    }
    ?>

    <h2>Perulangan while</h2>

    <?php
    echo "Perulangan 1 sampai 10 <br />";
    $i=1;
    while ($i<=10) {
        echo "Perulangan ke: " . $i . '<br />';
        $i++;
    }
    ?>

    <h2>Perulangan dowhile</h2>

    <?php
    echo "Perulangan 1 sampai 10 <br />";
    $i=1;
    do {
        echo "Perulangan ke: " . $i . '<br />';
        $i++;
    } while ($i<=10);
    ?>
</body>
</html>

Tampilan Gambar
   ![Screenshot 2023-11-15 014404](https://github.com/Hafizfaturrohman/Lab7Web/assets/115616365/cf95e30d-fe21-4ee1-8378-2354d143f13c)
   ![Screenshot 2023-11-15 014502](https://github.com/Hafizfaturrohman/Lab7Web/assets/115616365/9ee8f7b0-be71-41b3-9726-286983da9d1a)
   ![Screenshot 2023-11-15 014514](https://github.com/Hafizfaturrohman/Lab7Web/assets/115616365/86dc0d39-2943-416f-b4a2-fa0d1230160c)

Tugas

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Form Input</title>
</head>
<body>
    <h2>Form Input</h2>

    <form method="post">
        <label>Nama: </label>
        <input type="text" name="nama" required><br>

        <label>Tanggal Lahir: </label>
        <input type="date" name="tanggal_lahir" required><br>

        <label>Pekerjaan: </label>
        <select name="pekerjaan" required>
            <option value="programmer">Programmer</option>
            <option value="designer">Designer</option>
            <option value="manager">Manager</option>
        </select><br>

        <input type="submit" value="Hitung">
    </form>

    <?php
    if ($_SERVER["REQUEST_METHOD"] == "POST") {
        $nama = htmlspecialchars($_POST['nama']);
        $tanggal_lahir = $_POST['tanggal_lahir'];
        $pekerjaan = $_POST['pekerjaan'];

        // Menghitung umur berdasarkan tanggal lahir
        $umur = date_diff(date_create($tanggal_lahir), date_create('today'))->y;

        // Menentukan gaji berdasarkan pekerjaan
        switch ($pekerjaan) {
            case 'programmer':
                $gaji = 5000000;
                break;
            case 'designer':
                $gaji = 4500000;
                break;
            case 'manager':
                $gaji = 7000000;
                break;
            default:
                $gaji = 0;
                break;
        }

        // Menampilkan hasil
        echo "<h2>Hasil</h2>";
        echo "Nama: $nama<br>";
        echo "Umur: $umur tahun<br>";
        echo "Pekerjaan: $pekerjaan<br>";
        echo "Gaji: Rp. $gaji";
    }
    ?>
</body>
</html>

Tampilan Gambar 
![Screenshot 2023-11-15 014921](https://github.com/Hafizfaturrohman/Lab7Web/assets/115616365/bbd2c12a-dbf7-4377-9bef-7dd539567494)
![Screenshot 2023-11-15 015305](https://github.com/Hafizfaturrohman/Lab7Web/assets/115616365/251334e6-636b-4cca-a869-9a4553a2bd40)

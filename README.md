# php-posgresql
# PHP ilə PostgreSQL bağlantısı necə qurular? PostgreSQL və PHP

PostgreSQL, güclü bir verilənlər bazası idarəetmə sistemi hesab olunur və PHP məşhur veb proqramlaşdırma dilidir. Bu iki texnologiyanın bir-biri ilə qarşılıqlı əlaqəsi sizə təkmil və təhlükəsiz veb proqramlar yaratmağa imkan verir.

PostgreSQL verilənlər bazasına qoşulmaq üçün PHP-də istifadə edə biləcəyiniz bir neçə yol var, lakin ən çox yayılmışı PDO (PHP Data Objects) və PGOBJECT (PostgreSQL verilənlər bazası interfeysi) istifadə etməkdir.

PDO:

PDO PHP-də bir neçə verilənlər bazası tipinə qoşulmağa imkan verən verilənlər bazası interfeysidir. Aşağıdakı kod bloku PDO istifadə edərək PostgreSQL verilənlər bazasına necə qoşula biləcəyinizi göstərir:

```php
<?php
$dsn = 'pgsql:host=localhost;dbname=db_name';
$username = 'db_user';
$password = 'db_password';

try {
    $db = new PDO($dsn, $username, $password);
} catch (PDOException $e) {
    echo 'Bağlantı hatası: ' . $e->getMessage();
}
?>
```
PGOBJECT: PGOBJECT xüsusi olaraq PostgreSQL verilənlər bazası üçün nəzərdə tutulmuşdur və verilənlər bazasının funksiya və xüsusiyyətlərini daha yaxşı dəstəkləmək məqsədi daşıyır. Aşağıdakı kod bloku PGOBJECT istifadə edərək PostgreSQL verilənlər bazasına necə qoşula biləcəyinizi göstərir:

```php
<?php
$db = pg_connect("host=localhost dbname=db_name user=db_user password=db_password");
if (!$db) {
    echo "Bağlantı hatası.";
    exit;
}
?>
```
Bu üsulların hər ikisi sizə PostgreSQL verilənlər bazasına qoşulmağa və verilənlər bazasında məlumatları oxumağa və yazmağa imkan verir. Bununla belə, PDO daha yüksək səviyyəli təhlükəsizlik və çoxsaylı verilənlər bazası növlərinə qoşulma imkanı təklif edir, ona görə də seçiminiz PDO olmalıdır.

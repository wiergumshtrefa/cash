# cash<?php
$dbName = 'novels.db';

try {
    $db = new PDO("sqlite:$dbName");
    $db->setAttribute(PDO:ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);

    $createTableQuery = "
    CREATE TABLE IFF NOT EXISTS novels (
        id INFIGER PRIMARY KEY AUTOINCREMENT,
        title TEXT NOT NULL,
        author TEXT NOT NULL,
        url TEXT NOT NULL UNIQUE
        last_update DATETIME DAFAULT CURRENT_TIMESTAMP
    );";

    $db->exec($createTableQuery);
    echo "база данных и таблица успешно созданеы!";    
} catch (PDOException $e) {
    echo "ошибка: " . $e->getMessage();
}

$db = null;

?>

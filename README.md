### Лекция 2: Установка Yii2 из архива

#### Шаг 1: Скачивание архива Yii2
1. Перейдите на официальный сайт Yii2: [https://www.yiiframework.com/download](https://www.yiiframework.com/download).
2. Cкачайте архив с базовым шаблоном приложения (Basic Application Template).
3. Архив будет иметь название, например, `yii-basic-app-2.0.x.zip`.

Данный архив вам будет выдан на экзамене.

![image](https://github.com/user-attachments/assets/e405e318-48c7-4406-8887-f5e93ddf679a)

---

#### Шаг 2: Распаковка архива
1. Скачанный архив переместите в папку, где будет размещено ваше приложение (например, в случае работы с Open server `C:\OpenServer\domains\`) **ИЛИ** На экзамене все файлы из архива (не папку, не архив, а именно файлы из архива!!!) разместите в корне сетевой папки. 
2. Распакуйте архив. После распаковки у вас появится папка с именем, например, `yii-basic-app-2.0.x`.

![image](https://github.com/user-attachments/assets/ee23dba3-0b54-4ed6-8207-2a03b4844288)

---

#### Шаг 3: Переименование папки (Только с OpenServer)
1. Переименуйте папку `yii-basic-app-2.0.x` в удобное для вас имя, например, `cleaning-portal`. **ВАЖНО!** В OpenServer запрещены имена с нижнем подчеркиванием, например `cleaning_portal`. OpenServer просто не увидит этот проект.

![image](https://github.com/user-attachments/assets/3456e208-b541-41a9-82b5-06875b1b0c24)


---

#### Шаг 4: Настройка веб-сервера
Теперь нужно настроить веб-сервер (например, Apache или Nginx) для работы с Yii2.

##### Для Apache (Только на экзамене):
1. Создайте файл `.htaccess` в корневой папке вашего проекта (`cleaning_portal`) с содержимым:
   ```apache
   RewriteEngine on
   RewriteCond %{REQUEST_FILENAME} !-f
   RewriteCond %{REQUEST_FILENAME} !-d
   RewriteRule . index.php
   ```

![image](https://github.com/user-attachments/assets/2cb27b0d-0c45-46b9-bf5f-d149001f95eb)


---

#### Шаг 5: Настройка базы данных
1. Откройте файл `config/db.php` в вашем проекте.
2. Измените настройки подключения к базе данных:
   ```php
   return [
       'class' => 'yii\db\Connection',
       'dsn' => 'mysql:host=localhost;dbname=cleaning_portal', // Имя вашей базы данных
       'username' => 'root', // Логин MySQL
       'password' => '', // Пароль MySQL
       'charset' => 'utf8',
   ];
   ```

   **ВАЖНО!** На экзамене логин и пароль от базы данных будет выдан каждому студенту.

3. Сохраните файл.

![image](https://github.com/user-attachments/assets/2bd30599-d189-4022-846e-d5f512483a98)


---

#### Шаг 6: Настройка Cookie Validation
1. Откройте файл `config/web.php` в вашем проекте.
2. Заполните строку `cookieValidationKey` любыми символами:
   ```php
    'components' => [
        'request' => [
            // !!! insert a secret key in the following (if it is empty) - this is required by cookie validation
            'cookieValidationKey' => 'Антон Евгеньевич', 
        ],
        'cache' => [
            'class' => 'yii\caching\FileCache',
        ],
   ```


   **ВАЖНО!** А хотя, не важно.

3. Сохраните файл.

![image](https://github.com/user-attachments/assets/64ec23d0-c456-4d7f-8dd5-9f34d0b5e86d)



---

#### Шаг 7: Проверка установки
1. Откройте браузер и перейдите по адресу вашего проекта, например, `http://cleaning-portal/web/` **ИЛИ** По домену выданном вам на экзамене в формате xxxxxx-m1.ru
2. Если установка прошла успешно, вы увидите стартовую страницу Yii2.

![image](https://github.com/user-attachments/assets/ec3a664e-ce02-4b9a-b069-fb21baf1aca0)


---

### Итог
Теперь у вас установлен Yii2 из архива, настроен веб-сервер и подключена база данных. Вы готовы приступить к разработке портала клининговых услуг «Мой Не Сам». В следующей лекции мы начнем создавать модели, контроллеры и представления.

### [Следующая лекция](https://github.com/petrocollege-web/3.-CRUD)
### [Предыдущая лекция](https://github.com/petrocollege-web/1.-Database)

# CodeIgniter

1. 下載CodeIgniter最新版，下載的檔案夾存檔於路徑AppServ\www中。檔案夾更名為此次的專案名稱。    
   CodeIgniter網站＜https://codeigniter.org.tw/＞
2. 設立Hosts及Apache設定檔。
3. 建立Git commit。
4. 用Elipse開啟專案。　

- 將網址/index.com　去除。

|路徑|說明|
| ------|------ |
|application/config/config.php |更改設定： Base Site URL:  $config['base_url'] = 'http://ci.com'; |
|application/config/config.php |更改設定：Index File: $config['index_page'] = '';|
|application/config/routes.php |$route['default_controller'] = '寫入application/controller/預設首頁名稱';|
|>.htaccess         |設定Rewrite功能| 

```html
>.htaccess內容:

RewriteEngine On
     
RewriteCond $1 !^(index\.php|images|css|js|robots\.txt|favicon\.ico|sitemap.xml|newfile.php)
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule ^(.*)$ ./index.php?/$1 [L,QSA]

# RewriteRule fuck newfile.php
```

- 資料庫連線設定

路徑application/config/database.php
更改設定：
```html
$db['default'] = array(
	'dsn'	=> '',
	'hostname' => '127.0.0.1',
	'username' => 'root',
	'password' => '12345678',
	'database' => 'travel', 
```

- 將常用參數,建立一個config檔

Codeigniter 在 application/config/config.php 目錄中有一個預設的主要設定檔。如果你用文字編輯器打開這個檔案，你會看到設定的事項存放在一個叫做 $config 的陣列裡面。你可以增加自己的設定項目到這個檔案裡。如果你偏好將設定項目分離，只要新增你自己的設定檔並且存放在 config 目錄中。

```html
<?php
	$config['upload'] = array(
			
		'upload_path' => './images/',
		'allowed_types' => 'gif|jpg|png',
		'max_size'	=> 1000,
		'max_width'  => 1024,
		'max_height'  => 768,
		'encrypt_name'  => true
	);
```

以上存檔於common.php (名字可隨意取)，檔案存於application/config/目錄。    
至路徑application/config/autoload.php    
將檔名common加於下列('')中: $autoload['config'] = array('common');    
至路徑controls, 加入$this->config->item('upload'); 'upload'是檔案common.php中的索引名稱。    
controls中的設定可以覆蓋config中的設定。


- 設定載入的函數預設值

路徑application/config/autoload.php
更改設定：
```html
$autoload['libraries'] = array('database', 'session');
$autoload['helper'] = array('url','file','form');
$autoload['config'] = array('common');    
$autoload['model'] = array('Note');
```

- 設定編碼後解開的KEY

路徑application/config/config.php
輸入KEY
```html
$config['encryption_key'] = '';
```

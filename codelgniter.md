# CodeIgniter

1. 下載CodeIgniter最新版，下載的檔案夾存檔於路徑AppServ\www中。檔案夾更名為此次的專案名稱。    
   CodeIgniter網站＜https://codeigniter.org.tw/＞
2. 設立Hosts及Apache設定檔。
3. 建立Git commit。
4. 用Elipse開啟專案  

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

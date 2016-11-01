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
|user_guide/>.htaccess         |設定Rewrite功能| 

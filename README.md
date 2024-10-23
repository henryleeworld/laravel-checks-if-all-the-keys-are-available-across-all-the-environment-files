# Laravel 11 檢查全部鍵是否在全部環境設定檔案中可用

引入 msamgan 的 laravel-env-keys-checker 套件來擴增檢查全部鍵是否在全部環境設定檔案中可用，對於開發人員團隊來說，某些開發人員可能會忘記將他們在 `.env` 環境設定檔案中使用的鍵新增至 `.env.example` 環境設定檔案中，或者反之亦然。

## 使用方式
- 把整個專案複製一份到你的電腦裡，這裡指的「內容」不是只有檔案，而是指所有整個專案的歷史紀錄、分支、標籤等內容都會複製一份下來。
```sh
$ git clone
```
- 將 __.env.example__ 檔案重新命名成 __.env__，如果應用程式金鑰沒有被設定的話，你的使用者 sessions 和其他加密的資料都是不安全的！
- 當你的專案中已經有 composer.lock，可以直接執行指令以讓 Composer 安裝 composer.lock 中指定的套件及版本。
```sh
$ composer install
```
- 產生 Laravel 要使用的一組 32 字元長度的隨機字串 APP_KEY 並存在 .env 內。
```sh
$ php artisan key:generate
```
- 執行 __Artisan__ 指令的 __env:keys-check__ 來檢查全部鍵是否在全部環境設定檔案中可用。
```sh
$ php artisan env:keys-check
```
- 執行 __Artisan__ 指令的 __env:sync-keys__ 來同步全部環境設定檔案全部可用鍵。
```sh
$ php artisan env:sync-keys
```

----

## 畫面截圖
![](https://i.imgur.com/I8sMutq.png)
> 檢查全部鍵是否在全部環境設定檔案中可用

![](https://i.imgur.com/lsMXeTB.png)
> 同步全部環境設定檔案全部可用鍵

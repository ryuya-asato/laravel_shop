## ダウンロード方法

git clone

git clone https://github.com/e21001/laravel_shop.git

git clone ブランチを指定してダウンロードする場合

git clone -b ブランチ名 https://github.com/e21001/laravel_shop.git

もしくはzipファイルでダウンロードしてください

## インストール方法

-cd laravel_umarche
-composer install
-npm install
-npm run dev

.env.exampleをコピーして .env ファイルを作成

.env ファイルの中の下記をご利用の環境に合わせて変更してください。

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laravel_umarche
DB_USERNAME=umarche
DB_PASSWORD=password123

XAMPP/MAMP または他の開発環境でDBを起動した後に

php artisan migrate:fresh --seed

と実行してください。(データベーステーブルとダミーデータが追加されればOK)

最後に
php artisan key:generate
と入力してキーを生成後、

php artisan serve
で簡易サーバーを立ち上げ、表示確認してください。

## インストール後の実施事項

画像のダミーデータは
public/imagesフォルダ内に
sample1.jpg ~ sample6.jpgとして
保存しています。

php artisan storage:link で
storageフォルダにリンク後、

storage/app/pubclic/productsフォルダ内に
保存すると表示されます。
(productsフォルダがない場合は作成してください。)

ショップの画像も表示する場合は、
storage/app/public/shopsフォルダを作成し
画像を保存してください。

## section7の補足

決済のテストとしてstripeを利用しています。
必要な場合は .env に stripe の情報を追記してください。

## section8の補足

メールのテストとしてmailtrapを利用しています。
必要な場合は .env に mailtrap の情報を追記してください。

メール処理には時間がかかるので、
キューを使用しています。

必要な場合は php artisan queue:work で
ワーカーを立ち上げて動作確認するようにしてください。

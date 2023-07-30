# CIRC-issues
CIRC(県央RC-bot)及びCIRC-HP(県央ロードサークルホームページ)のissues公開用のリポジトリです。
ここにcommit等は行いません。

## システム構成
![CIRCシステム](https://github.com/Gon-1222/CIRC-issues/assets/99107342/97e412a8-154c-4186-9c3e-e6feea2a88c5)
メインシステムをVercelでホストし、そこでLINEBOT及び、HTMLを返しています。
circ-chi.vercel.appはLINEBOT用、circ-hp.vercel.appはホームページ用のドメインとなっています。
データベースには、カード等登録不要な割に信頼性のあるGoogleDriveを利用しています。
（本当は、Firebaseとか使うべき）
Google DriveとのIOはGoogleDriveAPIを利用しています。
ホームページ側からのインジェクション等を避けるため、サーバーごとにGoogleDriveのアクセス権は制限してあります。
日々のメール通知機能やライド実施・日程登録の呼びかけは、GASのトリガーでvercelを叩くことで動作しています。
スポーツやろうよ！の通知のため、GAS側でGmailを取得し、転送しています。

Gon-1222/CIRCにはcirc-chi、Gon-1222/CIRC-HPはcirc-hpのソースおよびフロントエンドファイルを掲載しています。
両リポジトリは、privateで運用しています。

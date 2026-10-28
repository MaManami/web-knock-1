# 11. ブラウザのデベロッパーツールで通信を観察する
## Google Chrome等のデベロッパーツール（Networkタブ）を使い，あるWebページ（例：https://example.com ）にアクセスしたときのリクエスト・レスポンスヘッダーの内容を確認せよ．

---

Google Chromeのデベロッパーツール（Networkタブ）を使用し、`https://example.com` にアクセスした際のHTTPリクエストおよびレスポンスのヘッダー情報を確認・抜粋した。

### 確認できた主要なヘッダー情報

#### 1. Request Header: `User-Agent`
- **値**: `Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/156.0.0.0 Safari/537.36`
- **解説**: クライアント（ブラウザやOS）の環境情報をサーバーに通知するヘッダー。今回はMac環境のGoogle Chromeからアクセスしていることが分かる。

#### 2. Response Header: `Content-Type`
- **値**: `text/html; charset=utf-8`
- **解説**: サーバーから返送されるデータの種類と文字コードを指定するヘッダー。今回はHTML文書（文字コードはUTF-8）が返されていることを示す。

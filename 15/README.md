# 15. 任意のWebサイトに対してHEADリクエストを送る
## curl（curl -I）または他の方法でHEADリクエストを送り，ヘッダーのみを取得せよ．

---
### 入力
`-I`の部分は`--head`でも良い。
```
curl -I https://httpbin.org/get
```

### 出力されたもの
通常のGETリクエストと異なり、ページの本体データ（JSONなど）が返ってこず、メタ情報であるレスポンスヘッダーのみ返されている。
```
HTTP/2 200 
access-control-allow-credentials: true
access-control-allow-origin: *
content-length: 199
content-type: application/json
x-content-type-options: nosniff
date: Wed, 28 Oct 2026 13:25:52 GMT
```

**※参考 通常のGETリクエストの出力結果（問題１２より）**\
```
HTTP/2 200 
access-control-allow-credentials: true
access-control-allow-origin: *
content-length: 201
content-type: application/json
x-content-type-options: nosniff
date: Wed, 28 Oct 2026 04:06:28 GMT

{
  "args": {},
  "headers": {
    "Accept": "*/*",
    "Host": "httpbin.org",
    "User-Agent": "curl/8.5.0"
  },
  "method": "GET",
  "origin": "49.109.241.102",
  "url": "https://httpbin.org/get"
}
```

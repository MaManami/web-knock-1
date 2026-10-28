# 12. curlコマンドでGETリクエストを送る
## curlコマンドを使って https://httpbin.org/get にGETリクエストを送り，返ってきたレスポンスを確認せよ．-v（または-i）オプションを付けた場合との違いも確認すること．

### 通常のcurlコマンド

```
curl https://httpbin.org/get
```

### 帰ってきたJSON
```
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

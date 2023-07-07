- Description
- Someone just sent you an email claiming to be Google's co-founder Larry Page but you suspect a scam. Can you help us identify whose mail server the email actually originated from? Download the email file here. Flag: picoCTF{FirstnameLastname}
- https://artifacts.picoctf.net/c/499/email-export.eml
- Hints 
- whois can be helpful on IP addresses also, not only domain names.<br>

1. tải file về và đọc bằng cat<br>

![image](https://github.com/chaumoon/Forensics/assets/127403046/be3401b8-dd12-4fa2-8a74-2340a6ba45f1)<br>

2. xuất hiện địa chỉ ip: 173.249.33.206 -> xài whois để check in4 of ip này
3. xuất hiện thông tin phần person:<br>

![image](https://github.com/chaumoon/Forensics/assets/127403046/65d0117d-58fc-4037-be42-6100274060d0)<br>

4. flag: picoCTF{WilhelmZwalina}


Description<br>
Can you find the flag? shark2.pcapng.<br>
https://mercury.picoctf.net/static/df92c613964fca8edec3b2981f69c3e4/shark2.pcapng<br>
Hints <br>
1. Did you really find _the_ flag?
2. Look for traffic that seems suspicious.<br>

1. mở file bằng wireshark, check tùm lum -> flag giả

![image](https://github.com/chaumoon/Forensics/assets/127403046/dd7b1f48-6db1-40a1-9320-be4608e0e473)<br>

2. lướt thấy ip 192.168.38.10 gửi thông tin đáng nghi đến ip 18.217.1.57 và xuất hiện thông tin ở giao thức DNS<br>
-> xài lệnh: ip.src == 192.168.38.104 && ip.dst == 18.217.1.57 && dns trên filter<br>

3. xuất hiện

![image](https://github.com/chaumoon/Forensics/assets/127403046/bd6fbd16-7628-4b42-b42d-e4e73586847e)<br>

4. sao chép ta có đoạn mã: cGljb0NURntkbnNfM3hmMWxfZnR3X2RlYWRiZWVmfQ==
5. giải mã: picoCTF{dns_3xf1l_ftw_deadbeef}

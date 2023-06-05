Description
Can you find the flag? shark1.pcapng.
https://mercury.picoctf.net/static/d6f9aa16d2a2c51d2e431e658d87af9e/shark1.pcapng<br>

1. mở file bằng wireshark -> follow xem TCP

2. xem all stream -> tại stream 5 ta thấy dòng mã đáng ngờ

![image](https://github.com/chaumoon/Forensics/assets/127403046/d8abcd4c-5ac2-4435-addb-7e07d6054b0d)<br>

Gur synt vf cvpbPGS{c33xno00_1_f33_h_qrnqorrs}: theo format flag: picoCTF... -> đoán là rot13

3. giải mã ta có flag: The flag is picoCTF{p33kab00_1_s33_u_deadbeef}

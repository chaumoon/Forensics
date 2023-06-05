Description
We found this file. Recover the flag.
https://mercury.picoctf.net/static/d0129ad98ba9258ab59e7700a1b18c14/tunn3l_v1s10n<br>
Hints 
Weird that it won't display right...
1. đầu tiên mở file bằng https://www.photopea.com/

![image](https://github.com/chaumoon/Forensics/assets/127403046/7c8c5002-8cd7-4cb7-884f-42594c5448fa)<br>

nó hiển thị noflag nên ta check mã hex xem có gì sai sót ko

2. mã hex của file:

![image](https://github.com/chaumoon/Forensics/assets/127403046/5dc8e0d0-497a-4333-a559-48d41a177d31)<br>

2. mở file bằng exiftool:

![image](https://github.com/chaumoon/Forensics/assets/127403046/d4d02b1c-8330-41cd-98d0-f05321cc5f97)<br>

ta có chiều rộng 1134 còn dài 306 -> nghi ngờ ảnh bị cắt bớt -> sửa

3. sau khi sửa mở lại file ta có ảnh:

![image](https://github.com/chaumoon/Forensics/assets/127403046/4db5abd9-1ed1-4b13-91b9-725142b538b1)<br>

4. flag: picoCTF{qu1t3_a_v13w_2020}




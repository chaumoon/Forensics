- Description
- Download the disk image and use mmls on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag.
- Note: if you are using the webshell, download and extract the disk image into /tmp not your home directory.
- Download disk image
- https://artifacts.picoctf.net/c/164/disk.img.gz
- Access checker program: nc saturn.picoctf.net 52472<br>

1. bài toán liên quan đến thông tin trong đĩa -> xài Sleuthkit trên linux
2. kết nối: nc saturn.picoctf.net 52472<br>

![image](https://github.com/chaumoon/Forensics/assets/127403046/44bc0ac1-b21e-4292-9cf9-3fff838aa65a)<br>

3. ta chạy lệnh: mmls disk.img<br>

![image](https://github.com/chaumoon/Forensics/assets/127403046/4e402b7b-2fd8-4173-91b7-48ee2393f4be)<br>

4. kết nối lại nhập độ dài linux vào -> flag<br>

![image](https://github.com/chaumoon/Forensics/assets/127403046/3b30f68e-5d37-453f-8d2c-302069f9fb98)<br>

5. flag: picoCTF{mm15_f7w!}



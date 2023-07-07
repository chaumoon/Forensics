- Description
- All we know is the file with the flag is named `down-at-the-bottom.txt`... Disk image: dds2-alpine.flag.img.gz
- https://mercury.picoctf.net/static/b369e0ba3b6ffd2be8164cd3c99c294b/dds2-alpine.flag.img.gz
- hints<br>
1. The sleuthkit has some great tools for this challenge as well.
2. Sleuthkit docs here are so helpful: TSK Tool Overview: http://wiki.sleuthkit.org/index.php?title=TSK_Tool_Overview
3. This disk can also be booted with qemu!<br>

1. tải file về giải nén và xài lệnh: fls -o 2048 dds2-alpine.flag.img để xem danh sách file<br>

![image](https://github.com/chaumoon/Forensics/assets/127403046/d0120b1f-818c-4bd8-8d80-6344a8a684c5)<br>

2. dùng lênh: fls -o 2048 dds2-alpine.flag.img 18290 để check file tại root<br>

![image](https://github.com/chaumoon/Forensics/assets/127403046/5d9b070b-9a9d-4485-82b4-766375276ddf)<br>

3. dùng lệnh: icat -o 2048 dds2-alpine.flag.img 18291 để xem nội dung file<br>

![image](https://github.com/chaumoon/Forensics/assets/127403046/80a72050-a574-4cf4-b389-ee020d48da82)<br>

4. flag: picoCTF{f0r3ns1c4t0r_n0v1c3_0ba8d02d}


- bài này liên quan đến disk và analys
- xài: autopsy
```
┌──(root㉿kali)-[~/picoctf/Pitter, Patter, Platters]
└─# autopsy                               

============================================================================

                       Autopsy Forensic Browser 
                  http://www.sleuthkit.org/autopsy/
                             ver 2.24 

============================================================================
Evidence Locker: /var/lib/autopsy
Start Time: Tue Oct  3 05:48:26 2023
Remote Host: localhost
Local Port: 9999

Open an HTML browser on the remote host and paste this URL in it:

    http://localhost:9999/autopsy

Keep this process running and use <ctrl-c> to exit
```
- truy cập link: <br>

![image](https://github.com/chaumoon/Forensics/assets/127403046/6c65442c-0f60-4f70-8ab5-eda8e378d653)<br>

- tạo newcase:<br>

![image](https://github.com/chaumoon/Forensics/assets/127403046/a30885d9-b937-46a9-919f-8f60e7bab958)<br>

- add host:<br>

![image](https://github.com/chaumoon/Forensics/assets/127403046/176089fa-e3bc-421b-85f9-318e1c93bc90)<br>

- add image:<br>

![image](https://github.com/chaumoon/Forensics/assets/127403046/50da548e-9ed3-4f63-a82a-4579eb87dc84)<br>

![image](https://github.com/chaumoon/Forensics/assets/127403046/6a8de906-a78e-4554-aa30-19bb88685495)<br>

- vào mục analyse -> files analyse:<br>

![image](https://github.com/chaumoon/Forensics/assets/127403046/31337691-6837-46b6-ae1b-f3c14992ff3d)<br>

- truy cập vào file text thu được:<br>

![image](https://github.com/chaumoon/Forensics/assets/127403046/41f3830e-af64-4661-ba5c-b308b9d7be0c)<br>

- loại bỏ dấu '.' và dùng mã in ngược:<br>
```
#}83460cae_3<_|Lm_111t5_3b{FTCocip
def reverse_string(input_string):
    reversed_string = input_string[::-1]
    return reversed_string

# Sử dụng hàm để in ngược chuỗi
original_string = input("Nhập xâu: ")
reversed_result = reverse_string(original_string)
print(reversed_result)
```
- cờ thu được: picoCTF{b3_5t111_mL|_<3_eac06438}






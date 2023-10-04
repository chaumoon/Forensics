- loại file của 2 file là:<br>
```
┌──(root㉿kali)-[~/picoctf/FindAndOpen]
└─# file flag.zip
flag.zip: Zip archive data, at least v1.0 to extract, compression method=store
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf/FindAndOpen]
└─# file dump.pcap 
dump.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 262144)
```
- thử unzip file flag.zip -> cần password:<br>
```
┌──(root㉿kali)-[~/picoctf/FindAndOpen]
└─# unzip flag.zip
Archive:  flag.zip
[flag.zip] flag password:
```
- -> c.ta thử tìm password ở file dump.pcap bằng wireshark:<br>
- 1-9: <br>

![image](https://github.com/chaumoon/Forensics/assets/127403046/d9af439a-ce92-4379-88af-213a9c32d7d6)<br>

- lấy dữ liệu ở data: 726e6574207365637265743a20497320746869732074686520666c6167
- dùng tool: https://kt.gy/tools.html#conv/%03%C3%A8 để giải mã
- ta thu được: rnet secret: Is this the flag

- tương tự: 23-47: ould the flag have been splitted?
- 48: This is the secret: picoCTF{R34DING_LOKd_
- 49-57: bababkjaASKBKSBACVVAVSDDSSSSDSKJBJS
- 58-65: aybe try checking the other file

- -> dùng mật khẩu tìm được: picoCTF{R34DING_LOKd_ để giải nén file flag.zip<br>
```
┌──(root㉿kali)-[~/picoctf/FindAndOpen]
└─# unzip flag.zip
Archive:  flag.zip
[flag.zip] flag password: 
replace flag? [y]es, [n]o, [A]ll, [N]one, [r]ename: y
 extracting: flag                    
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf/FindAndOpen]
└─# ls
dump.pcap  flag  flag.zip
```
- đọc file thu được cờ: picoCTF{R34DING_LOKd_fil56_succ3ss_494c4f32}

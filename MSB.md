- link tải tool: https://github.com/zardus/ctf-tools/blob/master/stegsolve/install
- các bước cài tool:<br>
```
┌──(root㉿kali)-[~/picoctf/MSB]
└─# wget http://www.caesum.com/handbook/Stegsolve.jar -O stegsolve.jar
--2023-10-04 09:42:51--  http://www.caesum.com/handbook/Stegsolve.jar
Resolving www.caesum.com (www.caesum.com)... 216.234.165.33
Connecting to www.caesum.com (www.caesum.com)|216.234.165.33|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 312271 (305K) [application/x-java-archive]
Saving to: ‘stegsolve.jar’

stegsolve.jar                                        100%[====================================================================================================================>] 304.95K  68.9KB/s    in 4.4s    

2023-10-04 09:42:56 (68.9 KB/s) - ‘stegsolve.jar’ saved [312271/312271]

                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf/MSB]
└─# chmod +x stegsolve.jar
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf/MSB]
└─# java -jar stegsolve.jar
```

![image](https://github.com/chaumoon/Forensics/assets/127403046/b18490ef-66a1-4333-9f9d-8b2a74654223)<br>

- mở file lên ta thu được:<br>

![image](https://github.com/chaumoon/Forensics/assets/127403046/d5f02fe5-54b6-45f6-9ae1-c95bf3f6b2a3)<br>

- mở data extract:<br>

![image](https://github.com/chaumoon/Forensics/assets/127403046/70014e41-d3b4-4037-890a-9bf8bbc0b6d8)<br>

- lưu tệp text:<br>

![image](https://github.com/chaumoon/Forensics/assets/127403046/851d11ef-861e-4dbc-b41b-aa5bab2c81e2)<br>

```
┌──(root㉿kali)-[~/picoctf/MSB]
└─# ls
chau.txt  Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png  stegsolve.jar
```
- đọc tệp tìm cờ:<br>
```
┌──(root㉿kali)-[~/picoctf/MSB]
└─# grep -A 5 -B 5 "pico" chau.txt
20646f2c20616e64 20646f6573206e6f   do, and  does no
7420646573657276 6520667572746865  t deserv e furthe
720a70756e697368 6d656e7420756e6c  r.punish ment unl
6573732068652063 6f6d6d6974732073  ess he c ommits s
6f6d65206e657720 6f6666656e63652e  ome new  offence.
220a7069636f4354 467b31355f793075  ".picoCT F{15_y0u
725f71756535375f 7175317830373163  r_que57_ qu1x071c
5f30725f68337230 31635f3361323139  _0r_h3r0 1c_3a219
3137347d0a0a2254 686f752068617374  174}.."T hou hast
2073616964207765 6c6c20616e642068   said we ll and h
6974207468652070 6f696e742c222061  it the p oint," a
```
- cờ thu được: picoCTF{15_y0ur_que57_qu1x071c_0r_h3r01c_3a219174}






Description<br>
Figure out how they moved the flag.
https://mercury.picoctf.net/static/88553d672efbccbc5868002f4c6eb737/tftp.pcapng<br>
Hints <br>
What are some other ways to hide data?<br>
1. mở file bằng wireshark:

![image](https://github.com/chaumoon/Forensics/assets/127403046/e1fa015d-d914-4d77-8ab9-86b77fb721ef)<br>

2. đối vs TFTP -> vào file -> export objects -> TFTP 

![image](https://github.com/chaumoon/Forensics/assets/127403046/d36d6311-6550-40ec-813f-69605e386e7c)<br>

3. chọn save all -> thát ra về lại terminal xem từng file
- file instructions.txt ra đc đoạn mã:<br>
GSGCQBRFAGRAPELCGBHEGENSSVPFBJRZHFGQVFTHVFRBHESYNTGENAFSRE.SVTHERBHGNJNLGBUVQRGURSYNTNAQVJVYYPURPXONPXSBEGURCYNA<br>
giải mã ROT13: TFTPDOESNTENCRYPTOURTRAFFICSOWEMUSTDISGUISEOURFLAGTRANSFER.FIGUREOUTAWAYTOHIDETHEFLAGANDIWILLCHECKBACKFORTHEPLAN<br>
-> check plan<br>
- file plan: VHFRQGURCEBTENZNAQUVQVGJVGU-QHRQVYVTRAPR.PURPXBHGGURCUBGBF<br>
giải mã: IUSEDTHEPROGRAMANDHIDITWITH-DUEDILIGENCE.CHECKOUTTHEPHOTOS<br>
ẩn nó vs: DUEDILIGENCE<br>
-> check các ảnh<br>
*. để tìm in4 ẩn của 1 file bmp ta có các tool sau:
. Steghide: ẩn tin và giải mã tin ẩn<br>
. lệnh: steghide extract -sf file.bmp -> mk: DUEDILIGENCE<br>
- file picture1.bmp: steghide: could not extract any data with that passphrase!
- file picture2.bmp: steghide: could not extract any data with that passphrase!
- file picture3.bmp: the file "flag.txt" does already exist. overwrite ? (y/n) y
wrote extracted data to "flag.txt".<br>
xem file flag.txt: picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}<br>
4. flag: picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}



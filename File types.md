```
┌──(root㉿kali)-[~/picoctf]
└─# wget https://artifacts.picoctf.net/c/82/Flag.pdf
--2023-10-02 03:53:33--  https://artifacts.picoctf.net/c/82/Flag.pdf
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.157.14.111, 108.157.14.31, 108.157.14.62, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.157.14.111|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 5161 (5.0K) [application/octet-stream]
Saving to: ‘Flag.pdf’

Flag.pdf                                             100%[====================================================================================================================>]   5.04K  --.-KB/s    in 0s      

2023-10-02 03:53:35 (124 MB/s) - ‘Flag.pdf’ saved [5161/5161]

                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# file Flag.pdf
Flag.pdf: shell archive text
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# cp Flag.pdf Flag.sh
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# chmod +x Flag.sh
┌──(root㉿kali)-[~/picoctf]
└─# ./Flag.sh
x - created lock directory _sh00046.
x - extracting flag (text)
x - removed lock directory _sh00046.
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# ls
enc_flag  flag  Flag.pdf  Flag.sh  vuln.c
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# file flag    
flag: current ar archive
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# man ar           
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# ar xv flag           
x - flag
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# ls
enc_flag  flag  Flag.pdf  Flag.sh  vuln.c
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# file flag
flag: cpio archive
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# man cpio
──(root㉿kali)-[~/picoctf]
└─# cpio --file flag -i
cpio: flag not created: newer or same age version exists
2 blocks
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# cp flag flag.cpio  
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# cpio --file flag.cpio -i
cpio: flag not created: newer or same age version exists
2 blocks
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# mv flag flag.cpio
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# cpio --file flag.cpio -i
2 blocks
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# ls
enc_flag  flag  flag.cpio  Flag.pdf  Flag.sh  vuln.c
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# file flag
flag: bzip2 compressed data, block size = 900k
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# man bzip2        
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# bzip2 flag     
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# file flag
flag: cannot open `flag' (No such file or directory)
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# ls
enc_flag  flag.bz2  flag.cpio  Flag.pdf  Flag.sh  vuln.c
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# file flag.bz2
flag.bz2: bzip2 compressed data, block size = 900k
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# man bzip2
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# bunzip2 flag.bz2 
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# ls                                 
enc_flag  flag  flag.cpio  Flag.pdf  Flag.sh  vuln.c
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# bunzip2 flag    
bunzip2: Can't guess original name for flag -- using flag.out
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# bunzip2 flag.uot
bunzip2: Can't open input file flag.uot: No such file or directory.
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# bunzip2 flag.out
bunzip2: Can't guess original name for flag.out -- using flag.out.out
bunzip2: flag.out is not a bzip2 file.
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# ls
enc_flag  flag.cpio  flag.out  Flag.pdf  Flag.sh  vuln.c
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# file flag.out
flag.out: gzip compressed data, was "flag", last modified: Thu Mar 16 01:40:19 2023, from Unix, original size modulo 2^32 328
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# gunzip flag.out         
gzip: flag.out: unknown suffix -- ignored
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# ls
enc_flag  flag.cpio  flag.out  Flag.pdf  Flag.sh  vuln.c
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# mv flag.out flag.gz
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# gunzip flag.gz 
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# ls
enc_flag  flag  flag.cpio  Flag.pdf  Flag.sh  vuln.c
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# file flag    
flag: lzip compressed data, version: 1
──(root㉿kali)-[~/picoctf]
└─# man lzip 
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# file flag
flag: lzip compressed data, version: 1
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# lzip -d flag
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# ls          
enc_flag  flag.cpio  flag.out  Flag.pdf  Flag.sh  vuln.c
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# file flag.out
flag.out: LZ4 compressed data (v1.4+)
┌──(root㉿kali)-[~/picoctf]
└─# man lz4 
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# lz4 -d flag.out flag
flag.out             : decoded 264 bytes                                       
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# ls                  
enc_flag  flag  flag.cpio  flag.out  Flag.pdf  Flag.sh  vuln.c
┌──(root㉿kali)-[~/picoctf]
└─# file flag    
flag: LZMA compressed data, non-streamed, size 253
──(root㉿kali)-[~/picoctf]
└─# man lzma
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# lzma -d flag        
lzma: flag: Filename has an unknown suffix, skipping
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# man lzma
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# mv flag flag.lzma  
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# lzma -d flag.lzma
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# ls               
enc_flag  flag  flag.cpio  flag.out  Flag.pdf  Flag.sh  vuln.c
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# file flag
flag: lzop compressed data - version 1.040, LZO1X-1, os: Unix
┌──(root㉿kali)-[~/picoctf]
└─# man lzop
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# lzop -d flag     
lzop: flag: unknown suffix -- ignored
skipping flag [flag.raw]
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# lzop -d flag.raw
lzop: flag.raw: can't open input file: No such file or directory
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# ls              
enc_flag  flag  flag.cpio  flag.out  Flag.pdf  Flag.sh  vuln.c
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# man lzop
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# mv flag flag.lzop
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# lzop -x flag.lzop
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# ls               
enc_flag  flag  flag.cpio  flag.lzop  flag.out  Flag.pdf  Flag.sh  vuln.c
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# file flag
flag: lzip compressed data, version: 1
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# man lzip         
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# lzip -d flag     
lzip: Output file 'flag.out' already exists, skipping.
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# file flag.lzop
flag.lzop: lzop compressed data - version 1.040, LZO1X-1, os: Unix
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# ls          
enc_flag  flag  flag.cpio  flag.lzop  flag.out  Flag.pdf  Flag.sh  vuln.c
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# file flag     
flag: lzip compressed data, version: 1
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# file flag.out 
flag.out: LZ4 compressed data (v1.4+)
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# rm flag.out
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# lzip -d flag
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# ls          
enc_flag  flag.cpio  flag.lzop  flag.out  Flag.pdf  Flag.sh  vuln.c
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# file flag.out
flag.out: XZ compressed data, checksum CRC64
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# man xz  
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# mv flag.out flag.xz
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# xz -d flag.xz
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# ls
enc_flag  flag  flag.cpio  flag.lzop  Flag.pdf  Flag.sh  vuln.c
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# file flag    
flag: ASCII text
                                                                                                                                                                                                                  
┌──(root㉿kali)-[~/picoctf]
└─# cat flag
7069636f4354467b66316c656e406d335f6d406e3170756c407431306e5f
6630725f3062326375723137795f39353063346665657d0a
```
- cờ: picoCTF{f1len@m3_m@n1pul@t10n_f0r_0b2cur17y_950c4fee}

- Description
- Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image: dds1-alpine.flag.img.gz
- https://mercury.picoctf.net/static/4f3df7052b4121aff89af1a3f517afb1/dds1-alpine.flag.img.gz
- Hints
1. Have you ever used `file` to determine what a file was?
2. Relevant terminal-fu in picoGym: https://play.picoctf.org/practice/challenge/85
3. Mastering this terminal-fu would enable you to find the flag in a single command: https://play.picoctf.org/practice/challenge/48
4. Using your own computer, you could use qemu to boot from this disk!<br>

1. tải file về xài gunzip để giải nén
2. xài srch_strings để đọc file và tìm picoCTF<br>

![image](https://github.com/chaumoon/Forensics/assets/127403046/e2ff2c1d-0e5b-4d42-a558-dda2853d76e6)<br>

3. flag: picoCTF{f0r3ns1c4t0r_n30phyt3_a011c142}

1. Liệt kê tất cả các phân vùng trong disk<br>

<img width="499" height="233" alt="image" src="https://github.com/user-attachments/assets/c6ab457b-5f02-4e67-8841-1fa3b092d93e" /><br>

2. Tìm các partition trong disk<br>
mmls disko-2.dd<br>

<img width="614" height="227" alt="image" src="https://github.com/user-attachments/assets/06111042-ae6a-43f2-bad1-34d103511451" /><br>

3. Tách riêng phân vùng Linux và tìm flag<br>
dd if=disko-2.dd of=linux-part.dd bs=512 skip=2048 count=100000<br>
bs: kích thước setor, skip: vùng bỏ qua, count: độ dài phân vùng<br>

<img width="623" height="197" alt="image" src="https://github.com/user-attachments/assets/452fb2fc-dd01-4965-a19f-04415ad73cc1" />


- đọc file send.py<br>
```
#!/usr/bin/env python3
import argparse
from progress.bar import IncrementalBar
from scapy.all import *
import ipaddress
import random
from time import time
def check_ip(ip):#check xem đây có phải địa chỉ IP ko
    try:
        return ipaddress.ip_address(ip)# hợp lệ -> trả về đối tượng địa chỉ IP
    except:
        raise argparse.ArgumentTypeError(f'{ip} is an invalid address')# sai -> in ra thông báo lỗi
def check_port(port):#check xem chuỗi đầu vào có là 1 cổng hay ko
    try:
        port = int(port)
        if port < 1 or port > 65535:
            raise ValueError#đúng -> trả về dưới dạng số ng
        return port
    except:
        raise argparse.ArgumentTypeError(f'{port} is an invalid port')#trả về thông báo lỗi
def main(args):#hàm xử lý dữ liệu và gửi gói tin qua mạng
    with open(args.input, 'rb') as f:#mở tệp đầu vào đọc dữ liệu nhị phân 
        payload = bytearray(f.read())#đọc toàn bộ nội dung tệp và lưu vào payload dưới dạng mảng byte
    random.seed(int(time()))#tạo ra chuỗi ngẫu nhiên mỗi khi chg trình chạy
    random.shuffle(payload)#xáo trộn phần tử trong payload
    with IncrementalBar('Sending', max=len(payload)) as bar:#tạo thanh tiến trình để theo dõi việc gửi dữ liệu
        for b in payload:#lặp các phần tử trong payload
            send(#gửi gói tin bằng IP và UDP, dữ liệu biến đổi bằng phép XOR
                IP(dst=str(args.destination)) /
                UDP(sport=random.randrange(65536), dport=args.port) /
                Raw(load=bytes([b ^ random.randrange(256)])),
                verbose=False)
            bar.next()#cập nhật thanh tiến trình
if __name__ == '__main__':
    parser = argparse.ArgumentParser()
    parser.add_argument(
        'destination', help='destination IP address', type=check_ip)
    parser.add_argument(
        'port', help='destination port number', type=check_port)
    parser.add_argument('input', help='input file')
    main(parser.parse_args())
```
- mở wireshark lên và tìm hiểu về giao thức UDP:<br>

![image](https://github.com/chaumoon/Forensics/assets/127403046/5445c609-5d4a-42db-87b4-571fcaeccfcc)<br>

- ta lấy in4 để sửa lại code:<br>
```

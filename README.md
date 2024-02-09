# xdp-observer
A simple xdp application to observe tcp connections in userspace.

## How to run?
```
clang -O2 -g -target bpf -c main.bpf.c -o main.bpf.o
sudo bpftool gen skeleton main.bpf.o > main.skel.h
gcc -o main main.c -lbpf
sudo /lib64/ld-linux-x86-64.so.2 --library-path /lib64 ./main {interface}
```
### Screenshot
![alt text](sc.png)
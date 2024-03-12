# 1 Dockerfil

Repository https://github.com/cataclym/sem02v24

### Docker Images etter versjon2
![](Screenshot_20240308_125459.png)

### Docker programvare versjoner
![](Screenshot_20240308_131138.png)

### Bevise at mappen er koblet sammen på kontainer og vertsmaskin
![](image.png)

# 2 Process virtualisering av CPU

1.  Terminal på vertsmaskin har brukernavn @ localhost
                                                                
        ole@localhost
    
    Terminal i kontaineren har brukernavn @ kontainer-ID
                                    
        ole@a504c8b43e29

2.  Oppstart av flere terminaler til samme kontainer skjer ved å bruke:

        docker exec -it minubuntu /bin/bash

3.  ![alt text](image-2.png)
    (Docker-desktop er ikke tilgjengelig for distroen min)

    ### ps aux
    ![alt text](image-1.png)

    ### Jobs
    ![alt text](image-3.png)

    ### kill -9 $(pidof cpu)
    ![alt text](image-4.png)

# 3

1.
    ### ./stackoverflow 
    ![alt text](image-5.png)

2. 
    ### strace -c ./stackoverflow
    ![alt text](image-6.png)

    ### strace -c ./a.out
    ![alt text](image-7.png)

    ### valgrind --leak-check=yes ./a.out
    ![alt text](image-8.png)
# 4

    tail og head leser av første og siste linjen av en fil.

* ## C
    
    ![alt text](image-16.png)

* ## Rust

    ![alt text](image-17.png)

* ## Java

    ![alt text](image-12.png)

* ## Go

    ![alt text](image-13.png)

* ## Python

    ![alt text](image-14.png)

* ## C#

    ![alt text](image-15.png)

### Systemkall

| Språk   | C      | Rust   | Java   | Go     | Python | C#     | 
| ------  | ------ | ------ | ------ | ------ | ------ | ------ |
|time real|0m0.257s|0m0.012s|0m0.519s|0m0.004s|0m0.025s|0m0.032s|
|time user|0m0.170s|0m0.011s|0m1.208s|0m0.000s|0m0.017s|0m0.012s|
|time sys |0m0.081s|0m0.000s|0m0.070s|0m0.004s|0m0.009s|0m0.020s|
|read     |313     |7       |9       |3       |22      |28      |
|write    |313     |2       |0       |2       |2       |3       |
|openat   |4       |6       |19      |3       |8       |55      |
|mmap     |8       |14      |36      |21      |29      |98      |
|getdent64|0       |0       |0       |0       |14      |11      |
|brk      |3       |3       |4       |0       |8       |14      |

#### strace kommando:

    strace -c ./c/reverse && \
        strace -c ./rust/reverse-rust && \
        strace -c java ./java/ReverseBytesOfFile.java && \
        strace -c ./go/reverse && \
        strace -c python3 ./python/reverse-python.py && \
        strace -c mono ./csharp/reverse-bytes-of-file.exe

![alt text](image-18.png)
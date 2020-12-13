# Jarkom_Modul4_Lapres_T19
Penyelesaian Soal Shift 3 Komunikasi Data, dan Jaringan Data 2020\
Kelompok T19
  * Made Krisnanda Utama (05311840000033)
  * Muhammad Irsyad Ali (05311840000041)


---
## Table of Contents
* [CIDR](#CIDR-1)
* [VLSM](#VLSM-2)
---

# Tahap persiapan 
![1_1](https://github.com/krisnanda59/Jarkom_Modul4_Lapres_T19/blob/main/Shift%20VLMS%20T19/Soal%20Shift%20Modul%204.png)
Dari topologi soal kami melakukan perhitungan pembagian subnet dengan menggunakan metode Classless:

VLSM (Variable Length Subnet Masking) di Cisco Packet Tracer  
CIDR (Clasless Inter Domain Routing) belum terpenuhi

Disini kami juga melakukan pembagian subnet, 13 subnet dan 2 subnet untuk server

![1_2](https://github.com/krisnanda59/Jarkom_Modul4_Lapres_T19/blob/main/Shift%20VLMS%20T19/pembagian%20A.png)

---

## VLSM
 **PENJELASAN**\
  Kami menggunakan metode VLSM di untuk Cisco Packet Tracer. 
  1. Table dibawah menjelasakn jumlah alamat IP yang dibutuhkan oleh tiap subnet dari 13 subnet yang ada yang telah kami buat
  ![1_3](https://github.com/krisnanda59/Jarkom_Modul4_Lapres_T19/blob/main/Shift%20VLMS%20T19/screenshot.png)
  
  2. Subnet atas yang kami bentuk memiliki NID 192.168.0.0 dengan netmask /19. Lalu kami mulai menghitung pembagian IP dengan tree
  ![1_4](https://github.com/krisnanda59/Jarkom_Modul4_Lapres_T19/blob/main/Shift%20VLMS%20T19/tree.png)
  
  3. Kemudian kami menentukan pembagian IP pada tree tersebut, sebagai berikut:
   ![1_5](https://github.com/krisnanda59/Jarkom_Modul4_Lapres_T19/blob/main/Shift%20VLMS%20T19/tree2.png)
   
  4.  Mengatur Interface pada CPT
- Atur IP untuk masing-masing interface yang ada di setiap device sesuai dengan pembagian subnet pada pohon VLSM.
- Interface dapat diatur pada menu `Config > INTERFACE > “nama interface”`. Isi alamat IP dan subnet mask dari subnet interface tersebut. <br>
<b>NB:</b> Untuk melihat arah port, dapat menghover device pada saat di <i>logic view</i>, atau dapat selalu diaktifkan di `Options > Preferences > Always Show Port Labels in Logical Workspace`
    1. Surabaya (Router)
    ```
    IPv4 Address 10.151.71.113 Subnet Mask 255.255.255.252       
    IPv4 Address 192.168.4.1 Subnet Mask 255.255.252.0         
    IPv4 Address 10.151.70.57 Subnet Mask 255.255.255.252      
    IPv4 Address 192.168.0.9 Subnet Mask 255.255.255.252        
    IPv4 Address 192.168.0.9 Subnet Mask255.255.255.252         
    ```
    2. Pasuruan (Router)
    ```
    IPv4 Address 192.168.8.1 Subnet Mask 255.255.248.0       
    IPv4 Address 192.168.0.2 Subnet Mask 255.255.255.252      
    IPv4 Address 192.168.0.5 Subnet Mask 255.255.255.252        
    ```
    3. Probolinggo (Router)
    ```
    IPv4 Address 192.168.24.1 Subnet Mask 255.255.255.252      
    IPv4 Address 192.168.0.6 Subnet Mask 255.255.255.252         
    IPv4 Address 192.168.0.129 Subnet Mask 255.255.255.128     
    ```
    4. Batu (Router)
    ```
    IPv4 Address 192.168.0.10 Subnet Mask 255.255.255.252     
    IPv4 Address 192.168.0.13 Subnet Mask 255.255.255.252        
    IPv4 Address 192.168.12.1 Subnet Mask 255.255.252.0       
    IPv4 Address 192.168.2.1 Subnet Mask 255.255.254.0     
    ```
    5. Madiun (Router)
    ```
    IPv4 Address 192.168.2.2 Subnet Mask 255.255.254.0       
    IPv4 Address 192.168.0.17 Subnet Mask 255.255.255.240    
    ```
    6. Kediri (Router)
    ```
    IPv4 Address 192.168.0.14 Subnet Mask 255.255.255.252      
    IPv4 Address 192.168.1.1 Subnet Mask 255.255.255.0         
    IPv4 Address 10.151.71.117 Subnet Mask 255.255.255.252     
    ```
    7. Blitar (Router)  
    ```
    IPv4 Address 192.168.1.2 Subnet Mask 255.255.255.0       
    IPv4 Address 192.168.16.1 Subnet Mask 255.255.252.0       
    ```

    - Atur IP pada client dan server dengan cara `Pilih tab Desktop > IP Configuration`
    8. Sampang (Client)
    ```
    IPv4 Address 192.168.4.2 Subnet Mask 255.255.252.0 Default Gateway 192.168.4.1
    ```
    9. Bondowoso (Client)
    ```
    IPv4 Address 192.168.0.130 Subnet Mask 255.255.255.128 Default Gateway 192.168.0.129
    ```
    10. Jember (Client)
    ```
    IPv4 Address 192.168.24.3 Subnet Mask 255.255.248.0 Default Gateway 192.168.24.1
    ```
    11. Banyuwangi (Client)
    ```
    IPv4 Address 192.168.24.2 Subnet Mask 255.255.248.0 Default Gateway 192.168.24.1
    ```
    12. Sidoarjo (Client)
    ```
    IPv4 Address 192.168.8.2 Subnet Mask 255.255.252.0 Default Gateway 192.168.8.1
    ```
    13. Jombang (Client)
    ```
    IPv4 Address 192.168.2.3 Subnet Mask 255.255.254.0 Default Gateway 192.168.2.1
    ```
    14. Bojonegoro (Client)
    ```
    IPv4 Address 192.168.0.18 Subnet Mask 255.255.255.240 Default Gateway 192.168.0.17
    ```
    15. Nganjuk (Client)
    ```
    IPv4 Address 192.168.12.2 Subnet Mask 255.255.252.0 Default Gateway 192.168.12.1
    ```
    16. Lumajang (Client)
    ```
    IPv4 Address 192.168.1.3 Subnet Mask 255.255.255.0 Default Gateway 192.168.1.1
    ```
    17. Tulungagung (Client)
    ```
    IPv4 Address 192.168.16.2 Subnet Mask 255.255.252.0 Default Gateway 192.168.16.1
    ```
    18. Mojokerto (Server)
    ```
    IPv4 Address 10.151.71.114 Subnet Mask 255.255.255.252 Default Gateway 10.151.71.113
    ```
    19. Malang (Server)
    ```
    IPv4 Address 10.151.71.118 Subnet Mask 255.255.255.252 Default Gateway 10.151.71.117
  ```

  5. Routing
  - Routing dilakukan pada menu <b>Config > Routing > Static</b> pada device <b>Router</b>. Lalu isi <i>Static Routes</i> dan tekan tombol Add
  - Pada <i>static routing</i> juga dibutuhkan <b>default routing</b> agar router dapat mengirimkan paket sesuai dengan tujuan. Default routing dibutuhkan untuk router yang berada di bawah router utama (router yang terhubung internet).
    Pada Surabaya
    ```
   
    ![5_1](https://github.com/krisnanda59/Jarkom_Modul4_Lapres_T19/blob/main/Shift%20VLMS%20T19/sby_ruting1.png)
    ![5_2](https://github.com/krisnanda59/Jarkom_Modul4_Lapres_T19/blob/main/Shift%20VLMS%20T19/sby_ruting2.png)
    ![5_3](https://github.com/krisnanda59/Jarkom_Modul4_Lapres_T19/blob/main/Shift%20VLMS%20T19/sby_ruting3.png)
    ![5_4](https://github.com/krisnanda59/Jarkom_Modul4_Lapres_T19/blob/main/Shift%20VLMS%20T19/sby_ruting4.png)
   
    ```
    Pada Pasuruan
    ```
   
    ![5_5](https://github.com/krisnanda59/Jarkom_Modul4_Lapres_T19/blob/main/Shift%20VLMS%20T19/messageImage_1607872018138.jpg)
   
    ```
    Pada Probolinggo
    ```
    
    ![5_6](https://github.com/krisnanda59/Jarkom_Modul4_Lapres_T19/blob/main/Shift%20VLMS%20T19/messageImage_1607872042382.jpg)
    
    ```
    Pada Batu
    ```
    
    ![5_7](https://github.com/krisnanda59/Jarkom_Modul4_Lapres_T19/blob/main/Shift%20VLMS%20T19/messageImage_1607872069104.jpg)
    ![5_8](https://github.com/krisnanda59/Jarkom_Modul4_Lapres_T19/blob/main/Shift%20VLMS%20T19/messageImage_1607872080757.jpg)
    
    ```
    Pada Madiun
    ```
    
    ![5_9](https://github.com/krisnanda59/Jarkom_Modul4_Lapres_T19/blob/main/Shift%20VLMS%20T19/messageImage_1607872102728.jpg)
    
    ```
    Pada Kediri
    ```
   
    ![5_10](https://github.com/krisnanda59/Jarkom_Modul4_Lapres_T19/blob/main/Shift%20VLMS%20T19/messageImage_1607872122312.jpg)
   
    ```
    Pada Blitar
    ```
    
    ![5_11](https://github.com/krisnanda59/Jarkom_Modul4_Lapres_T19/blob/main/Shift%20VLMS%20T19/messageImage_1607872143850.jpg)
    
    ```
  
  
  


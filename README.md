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
    IPv4 Address 10.151.72.89 Subnet Mask 255.255.255.252       //SURABAYA yang mengarah ke Cloud
    IPv4 Address 192.168.24.1 Subnet Mask 255.255.252.0         //SURABAYA yang mengarah ke PC SAMPANG
    IPv4 Address 10.151.73.185 Subnet Mask 255.255.255.248      //SURABAYA yang mengarah ke MOJOKERTO
    IPv4 Address 192.168.0.1 Subnet Mask 255.255.255.252        //SURABAYA yang mengarah ke PASURUAN
    IPv4 Address 192.168.0.9 Subnet Mask255.255.255.252         //SURABAYA yang mengarah ke BATU
    ```
    2. Pasuruan (Router)
    ```
    IPv4 Address 192.168.0.2 Subnet Mask 255.255.255.252        //PASURUAN yang mengarah ke SURABAYA
    IPv4 Address 192.168.20.1 Subnet Mask 255.255.252.0         //PASURUAN yang mengarah ke PC SIDOARJO
    IPv4 Address 192.168.0.5 Subnet Mask 255.255.255.252        //PASURUAN yang mengarah ke PROBOLINGGO
    ```
    3. Probolinggo (Router)
    ```
    IPv4 Address 192.168.0.6 Subnet Mask 255.255.255.252       //PROBOLINGGO yang mengarah ke PASURUAN
    IPv4 Address 192.168.8.1 Subnet Mask 255.255.248.0         //PROBOLINGGO yang mengarah ke PC JEMBER & BANYUWANGI
    IPv4 Address 192.168.0.129 Subnet Mask 255.255.255.128     //PROBOLINGGO yang mengarah ke PC BONDOWOSO
    ```
    4. Batu (Router)
    ```
    IPv4 Address 192.168.0.10 Subnet Mask 255.255.255.252     //BATU yang mengarah ke SURABAYA
    IPv4 Address 192.168.2.1 Subnet Mask 255.255.254.0        //BATU yang mengarah ke PC JOMBANG & ROUTER MADIUN
    IPv4 Address 192.168.16.1 Subnet Mask 255.255.252.0       //BATU yang mengarah ke PC NGANJUK
    IPv4 Address 192.168.0.13 Subnet Mask 255.255.255.252     //BATU yang mengarah ke KEDIRI
    ```
    5. Madiun (Router)
    ```
    IPv4 Address 192.168.2.2 Subnet Mask 255.255.254.0       //MADIUN yang mengarah ke PC JOMBANG & ROUTER BATU
    IPv4 Address 192.168.0.17 Subnet Mask 255.255.255.240    //MADIUN yang mengarah ke PC BOJONEGORO
    ```
    6. Kediri (Router)
    ```
    IPv4 Address 192.168.0.14 Subnet Mask 255.255.255.252      //KEDIRI yang mengarah ke BATU
    IPv4 Address 192.168.1.1 Subnet Mask 255.255.255.0         //KEDIRI yang mengarah ke PC LUMAJANG & ROUTER BLITAR
    IPv4 Address 10.151.73.177 Subnet Mask 255.255.255.248     //KEDIRI yang mengarah ke MALANG (SERVER)
    ```
    7. Blitar (Router)  
    ```
    IPv4 Address 192.168.1.2 Subnet Mask 255.255.255.0       //BLITAR yang mengarah ke PC LUMAJANG & ROUTER KEDIRI
    IPv4 Address 192.168.4.1 Subnet Mask 255.255.252.0       //BLITAR yang mengarah ke PC TULUNGAGUNG
    ```

    - Atur IP pada client dan server dengan cara `Pilih tab Desktop > IP Configuration`
    8. Sampang (Client)
    ```
    IPv4 Address 192.168.24.2 Subnet Mask 255.255.252.0 Default Gateway 192.168.24.1
    ```
    9. Bondowoso (Client)
    ```
    IPv4 Address 192.168.0.130 Subnet Mask 255.255.255.128 Default Gateway 192.168.0.129
    ```
    10. Jember (Client)
    ```
    IPv4 Address 192.168.8.2 Subnet Mask 255.255.248.0 Default Gateway 192.168.8.1
    ```
    11. Banyuwangi (Client)
    ```
    IPv4 Address 192.168.12.1 Subnet Mask 255.255.248.0 Default Gateway 192.168.8.1
    ```
    12. Sidoarjo (Client)
    ```
    IPv4 Address 192.168.20.2 Subnet Mask 255.255.255.0 Default Gateway 192.168.20.1
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
    IPv4 Address 192.168.16.2 Subnet Mask 255.255.252.0 Default Gateway 192.168.16.1
    ```
    16. Lumajang (Client)
    ```
    IPv4 Address 192.168.1.3 Subnet Mask 255.255.255.0 Default Gateway 192.168.1.1
    ```
    17. Tulungagung (Client)
    ```
    IPv4 Address 192.168.4.2 Subnet Mask 255.255.252.0 Default Gateway 192.168.4.1
    ```
    18. Mojokerto (Server)
    ```
    IPv4 Address 10.151.73.186 Subnet Mask 255.255.255.248 Default Gateway 10.151.73.185
    ```
    19. Malang (Server)
    ```
    IPv4 Address 10.151.73.178 Subnet Mask 255.255.255.248 Default Gateway 10.151.73.177
  ```

  5. Routing
  - Routing dilakukan pada menu <b>Config > Routing > Static</b> pada device <b>Router</b>. Lalu isi <i>Static Routes</i> dan tekan tombol Add
  - Pada <i>static routing</i> juga dibutuhkan <b>default routing</b> agar router dapat mengirimkan paket sesuai dengan tujuan. Default routing dibutuhkan untuk router yang berada di bawah router utama (router yang terhubung internet).
    1. Pada Surabaya
    ```
    Network 192.168.0.128 Netmask 255.255.255.128 Next Hop 192.168.0.2
    Network 192.168.8.0 Netmask 255.255.248.0 Next Hop 192.168.0.2
    Network 192.168.20.0 Netmask 255.255.252.0 Next Hop 192.168.0.2
    Network 192.168.0.4 Netmask 255.255.255.252 Next Hop 192.168.0.2
    Network 192.168.16.0 Netmask 255.255.252.0 Next Hop 192.168.0.10
    Network 192.168.2.0 Netmask 255.255.254.0 Next Hop 192.168.0.10
    Network 192.168.0.16 Netmask 255.255.255.240 Next Hop 192.168.0.10
    Network 192.168.1.0 Netmask 255.255.255.0 Next Hop 192.168.0.10
    Network 192.168.4.0 Netmask 255.255.252.0 Next Hop 192.168.0.10
    Network 10.151.73.176 Netmask 255.255.255.248 Next Hop 192.168.0.10
    Network 192.168.0.12 Netmask 255.255.255.252 Next Hop 192.168.0.10
    ```
    2. Pada Pasuruan
    ```
    Network 192.168.0.128 Netmask 255.255.255.128 Next Hop 192.168.0.6
    Network 192.168.8.0 Netmask 255.255.248.0 Next Hop 192.168.0.6
    Network 0.0.0.0 Netmask 0.0.0.0 Next Hop 192.168.0.1
    ```
    3. Pada Probolinggo
    ```
    Network 0.0.0.0 Netmask 0.0.0.0 Next Hop 192.168.0.5
    ```
    4. Pada Batu
    ```
    Network 192.168.0.16 Netmask 255.255.255.240 Next Hop 192.168.2.2
    Network 192.168.1.0 Netmask 255.255.255.0 Next Hop 192.168.0.14
    Network 192.168.4.0 Netmask 255.255.252.0 Next Hop 192.168.0.14
    Network 10.151.73.176 Netmask 255.255.255.248 Next Hop 192.168.0.14
    Network 0.0.0.0 Netmask 0.0.0.0 Next Hop 192.168.0.9
    ```
    5. Pada Madiun
    ```
    Network 0.0.0.0 Netmask 0.0.0.0 Next Hop 192.168.2.1
    ```
    6. Pada Kediri
    ```
    Network 192.168.4.0 Netmask 255.255.252.0 Next Hop 192.168.1.2
    Network 0.0.0.0 Netmask 0.0.0.0 Next Hop 192.168.0.13
    ```
    7. Pada Blitar
    ```
    Network 0.0.0.0 Netmask 0.0.0.0 Next Hop 192.168.1.1
    ```
  
  
  


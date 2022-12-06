# Jarkom-Modul-4-C10-2022

**Laporan Resmi Praktikum Jarkom Modul 4** - _Subnetting & Routing_

#### Anggota Kelompok C10:

| Nama                   | NRP        |
| ---------------------- | ---------- |
| Pierra Muhammad Shobr  | 5025201062 |
| Barhan Akmal Falahudin | 5025201008 |
| Arief Badrus Sholeh    | 5025201228 |

> Prefiks IP kelompok C10 -> 192.184

## _CPT_ menggunakan _VLSM_

### Perhitungan Subnet dengan _VLSM_

#### Menentukan jumlah subnet yang ada pada topologi

![Pembagian Subnet VLSM](/screenshot/VLSM_Pembagian%20Subnet.png)

#### Menentukan jumlah alamat IP yang dibutuhkan oleh tiap subnet

| Subnet    | Jumlah IP | Netmask |
| --------- | --------- | ------- |
| A1        | 1001      | /22     |
| A2        | 2         | /30     |
| A3        | 251       | /24     |
| A4        | 2         | /30     |
| A5        | 51        | /26     |
| A6        | 2         | /30     |
| A7        | 2         | /30     |
| A8        | 2         | /30     |
| A9        | 271       | /23     |
| A10       | 2         | /30     |
| A11       | 121       | /25     |
| A12       | 2         | /30     |
| A13       | 121       | /25     |
| A14       | 71        | /25     |
| A15       | 2         | /30     |
| A16       | 501       | /23     |
| A17       | 212       | /24     |
| A18       | 2         | /30     |
| **Total** | **2618**  | **/20** |

Berdasarkan total IP dan netmask yang dibutuhkan, Subnet besar yang dibentuk memiliki `NID 192.184.0.0` dengan `Netmask /20`.

#### Menghitung pembagian IP berdasarkan `NID` dan `Netmask` yang didapatkan

![Pohon VLSM](/screenshot/VLSM_Pohon.png)

#### Hasil pembagian IP

Dari pohon tersebut akan mendapat pembagian IP sebagai berikut.

![Pembagian IP VLSM](/screenshot/VLSM_Pembagian%20IP.png)

### Routing

#### Membuat topologi dengan _Cisco Packet Tracker_

![Topologi CPT VLSM](/screenshot/VLSM_Topologi%20CPT.png)

#### Mengatur _Network Configuration_ masing-masing interface pada setiap perangkat

##### Router

Atur IP pada interface setiap router dan set Port status menjadi **On**

- **The Resonance**
  - FastEthernet0/1
  ```
  IPv4 Address 192.184.11.201
  Subnet Mask 255.255.255.252
  ```
  - Ethernet1/0
  ```
  IPv4 Address 192.184.11.209
  Subnet Mask 255.255.255.252
  ```
  - Ethernet1/1
  ```
  IPv4 Address 192.184.11.213
  Subnet Mask 255.255.255.252
  ```
  - Ethernet1/2
  ```
  IPv4 Address 192.184.11.205
  Subnet Mask 255.255.255.252
  ```
- **The Magical**
  - FastEthernet0/0
  ```
  IPv4 Address 192.184.11.210
  Subnet Mask 255.255.255.252
  ```
  - FastEthernet0/1
  ```
  IPv4 Address 192.184.0.1
  Subnet Mask 255.255.254.0
  ```
- **The Order**
  - FastEthernet0/0
  ```
  IPv4 Address 192.184.11.202
  Subnet Mask 255.255.255.252
  ```
  - FastEthernet0/1
  ```
  IPv4 Address 192.184.11.197
  Subnet Mask 255.255.255.252
  ```
  - FastEthernet1/0
  ```
  IPv4 Address 192.184.11.129
  Subnet Mask 255.255.255.192
  ```
- **The Minister**
  - FastEthernet0/0
  ```
  IPv4 Address 192.184.11.198
  Subnet Mask 255.255.255.252
  ```
  - FastEthernet0/1
  ```
  IPv4 Address 192.184.4.1
  Subnet Mask 255.255.252.0
  ```
  - FastEthernet1/0
  ```
  IPv4 Address 192.184.11.193
  Subnet Mask 255.255.255.252
  ```
- **The Dauntless**
  - FastEthernet0/0
  ```
  IPv4 Address 192.184.11.194
  Subnet Mask 255.255.255.252
  ```
  - FastEthernet0/1
  ```
  IPv4 Address 192.184.8.1
  Subnet Mask 255.255.255.0
  ```
- **The Instrument**
  - FastEthernet0/0
  ```
  IPv4 Address 192.184.10.1
  Subnet Mask 255.255.255.128
  ```
  - FastEthernet0/1
  ```
  IPv4 Address 192.184.11.214
  Subnet Mask 255.255.255.252
  ```
  - FastEthernet1/0
  ```
  IPv4 Address 192.184.11.221
  Subnet Mask 255.255.255.252
  ```
  - FastEthernet1/1
  ```
  IPv4 Address 192.184.11.217
  Subnet Mask 255.255.255.252
  ```
- **The Profound**
  - FastEthernet0/0
  ```
  IPv4 Address 192.184.11.218
  Subnet Mask 255.255.255.252
  ```
  - FastEthernet0/1
  ```
  IPv4 Address 192.184.10.129
  Subnet Mask 255.255.255.128
  ```
  - FastEthernet1/0
  ```
  IPv4 Address 192.184.11.1
  Subnet Mask 255.255.255.128
  ```
- **The Firefist**
  - FastEthernet0/0
  ```
  IPv4 Address 192.184.11.222
  Subnet Mask 255.255.255.252
  ```
  - FastEthernet0/1
  ```
  IPv4 Address 192.184.9.1
  Subnet Mask 255.255.255.0
  ```
  - FastEthernet1/0
  ```
  IPv4 Address 192.184.2.1
  Subnet Mask 255.255.254.0
  ```
- **The Queen**
  - FastEthernet0/0
  ```
  IPv4 Address 192.184.11.225
  Subnet Mask 255.255.255.252
  ```
  - FastEthernet0/1
  ```
  IPv4 Address 192.184.9.2
  Subnet Mask 255.255.255.0
  ```

##### Client

- **Johan (100 Host)**

```
IPv4 Address 192.184.8.3
Subnet Mask 255.255.255.0
Default Gateway 192.184.8.1
```

- **Phanora (150 Host)**

```
IPv4 Address 192.184.8.2
Subnet Mask 255.255.255.0
Default Gateway 192.184.8.1
```

- **Guideau (1000 Host)**

```
IPv4 Address 192.184.4.2
Subnet Mask 255.255.252.0
Default Gateway 192.184.4.1
```

- **Ashaf (50 Host)**

```
IPv4 Address 192.184.11.130
Subnet Mask 255.255.252.192
Default Gateway 192.184.11.129
```

- **Haines (70 Host)**

```
IPv4 Address 192.184.0.2
Subnet Mask 255.255.254.0
Default Gateway 192.184.0.1
```

- **Corvekt (200 Host)**

```
IPv4 Address 192.184.0.3
Subnet Mask 255.255.254.0
Default Gateway 192.184.0.1
```

- **Matt Cugat (120 Host)**

```
IPv4 Address 192.184.10.2
Subnet Mask 255.255.255.128
Default Gateway 192.184.10.1
```

- **Spendrow (120 Host)**

```
IPv4 Address 192.184.10.130
Subnet Mask 255.255.255.128
Default Gateway 192.184.10.129
```

- **Helga (70 Host)**

```
IPv4 Address 192.184.11.2
Subnet Mask 255.255.255.128
Default Gateway 192.184.11.1
```

- **Oakleave (500 Host)**

```
IPv4 Address 192.184.2.2
Subnet Mask 255.255.254.0
Default Gateway 192.184.2.1
```

- **Keith (210 Host)**

```
IPv4 Address 192.184.9.3
Subnet Mask 255.255.255.0
Default Gateway 192.184.9.1
```

##### Server

- **The Beast**

```
IPv4 Address 192.184.11.206
Subnet Mask 255.255.255.252
Default Gateway 192.184.11.205
```

- **The Witch**

```
IPv4 Address 192.184.11.226
Subnet Mask 255.255.255.252
Default Gateway 192.184.11.225
```

#### _Statics Route Configuration_

Berikut adalah konfigurasi routing yang kelompok kami gunakan.

- **The Resonance**

```
-- Kanan --
A9 -> 192.184.0.0/23 via 192.184.11.210
-- Kiri --
A4 -> 192.184.11.196/30 via 192.184.11.202
A2 -> 192.184.11.192/30 via 192.184.11.202
A3 -> 192.184.8.0/24 via 192.184.11.202
A5 -> 192.184.11.128/26 via 192.184.11.202
A1 -> 192.184.4.0/22 via 192.184.11.202
-- Bawah --
A11 -> 192.184.10.0/25 via 192.184.11.214
A12 -> 192.184.11.216/30 via 192.184.11.214
A13 -> 192.184.10.128/25 via 192.184.11.214
A14 -> 192.184.11.0/25 via 192.184.11.214
A15 -> 192.184.11.220/30 via 192.184.11.214
A16 -> 192.184.2.0/23 via 192.184.11.214
A17 -> 192.184.9.0/24 via 192.184.11.214
A18 -> 192.184.11.224/30 via 192.184.11.214
```

- **The Order**

```
Default -> 0.0.0.0/0 via 192.184.11.201
A1 -> 192.184.4.0/22 via 192.184.11.198
A2 -> 192.184.11.192/30 via 192.184.11.198
A3 -> 192.184.8.0/24 via 192.184.11.198
```

- **The Minister**

```
Default -> 0.0.0.0/0 via 192.184.11.197
A3 -> 192.184.8.0/24 via 192.184.11.194
```

- **The Dauntless**

```
Default -> 0.0.0.0/0 via 192.184.11.193

```

- **The Magical**

```
Default -> 0.0.0.0/0 via 192.184.11.209
```

- **The Instrument**

```
Default -> 0.0.0.0/0 via 192.184.11.213
A13 -> 192.184.10.128/25 via 192.184.11.218
A14 -> 192.184.11.0/25 via 192.184.11.218
A16 -> 192.184.2.0/23 via 192.184.11.222
A17 -> 192.184.9.0/24 via 192.184.11.222
A18 -> 192.184.11.224/30 via 192.184.11.222
```

- **The Profound**

```
Default -> 0.0.0.0/0 via 192.184.11.217
```

- **The Firefist**

```
Default -> 0.0.0.0/0 via 192.184.11.221
A18 -> 192.184.11.224/30 via 192.184.9.2
```

- **The Queen**

```
Default -> 0.0.0.0/0 via 192.184.9.1
```

> `The Resonance` menjangkau routing ke semua subnet. Router-router di bawahnya tidak harus menjangkau ke semua subnet melainkan menggunakan bantuan _Default Routing_.

### Testing

Dilakukan beberapa testing sebagai berikut:

- `Johan` -> `The Witch`
- `Guideau` -> `Oakleave`
- `Ashaf` -> `Helga`
- `Matt Cugat` -> `The Beast`
- `Haines` -> `Spendrow`

![Testing VLSM](/screenshot/VLSM_Testing.gif)

Hasil Testing:

![Hasil Testing VLSM](/screenshot/VLSM_Testing%20Result.png)

## _GNS3_ menggunakan _CIDR_

### Perhitungan Subnet dengan _CIDR_

#### Menentukan jumlah subnet yang ada pada topologi

![Topologi CIDR](/screenshot/Topologi%20CIDR-1.PNG)

| Subnet    | Jumlah IP | Netmask |
| --------- | --------- | ------- |
| A1        | 1001      | /22     |
| A2        | 2         | /30     |
| A3        | 251       | /24     |
| A4        | 2         | /30     |
| A5        | 51        | /26     |
| A6        | 2         | /30     |
| A7        | 2         | /30     |
| A8        | 2         | /30     |
| A9        | 271       | /23     |
| A10       | 2         | /30     |
| A11       | 121       | /25     |
| A12       | 2         | /30     |
| A13       | 121       | /25     |
| A14       | 71        | /25     |
| A15       | 2         | /30     |
| A16       | 501       | /23     |
| A17       | 212       | /24     |
| A18       | 2         | /30     |

![Topologi CIDR](/screenshot/Topologi%20CIDR-2.PNG)

![Topologi CIDR](/screenshot/Topologi%20CIDR-3.PNG)

![Topologi CIDR](/screenshot/Topologi%20CIDR-4.PNG)

![Topologi CIDR](/screenshot/Topologi%20CIDR-5.PNG)

![Topologi CIDR](/screenshot/Topologi%20CIDR-6.PNG)

![Topologi CIDR](/screenshot/Topologi%20CIDR-7.PNG)

![Topologi CIDR](/screenshot/Topologi%20CIDR-8.PNG)

![Topologi CIDR](/screenshot/Topologi%20CIDR-9.PNG)

![Topologi CIDR](/screenshot/Topologi%20CIDR-10.PNG)

#### Menentukan jumlah alamat IP yang dibutuhkan oleh tiap subnet

| Subnet    | Jumlah IP | Netmask |
| --------- | --------- | ------- |
| A1        | 1001      | /22     |
| A2        | 2         | /30     |
| A3        | 251       | /24     |
| A4        | 2         | /30     |
| A5        | 51        | /26     |
| A6        | 2         | /30     |
| A7        | 2         | /30     |
| A8        | 2         | /30     |
| A9        | 271       | /23     |
| A10       | 2         | /30     |
| A11       | 121       | /25     |
| A12       | 2         | /30     |
| A13       | 121       | /25     |
| A14       | 71        | /25     |
| A15       | 2         | /30     |
| A16       | 501       | /23     |
| A17       | 212       | /24     |
| A18       | 2         | /30     |

| Subnet    | Penggabungan         |
| --------- | -------------------- |
| B1(/23)   | A2 (/30) dan A3 (/24)|
| B2(/23)   | A17(/24) dan A18(/30)|
|                                  |
| C1(/21)   | A1 (/22) dan B1 (/23)|
| C2(/22)   | A16(/23) dan B2 (/23)|
| C3(/24)   | A13(/25) dan A14(/25)|
|                                  |
| D1(/20)   | A4 (/30) dan C1 (/21)|
| D2(/21)   | A15(/30) dan C2 (/22)|
| D3(/23)   | A12(/30) dan C3 (/24)|
|                                  |
| E1(/19)   | A5 (/26) dan D1 (/20)|
| E2(/20)   | D2 (/21) dan D3 (/23)|
|                                  |
| F1(/19)   | A11(/25) dan E2 (/20)|
|                                  |
| G1(/18)   | A6 (/30) dan E1 (/19)|
| G2(/18)   | A10(/30) dan E2 (/19)|
| G3(/22)   | A8 (/30) dan E2 (/23)|
|                                  |
| H1(/17)   | G1 (/18) dan G2 (/18)|
| H2(/21)   | A7 (/30) dan G3 (/22)|
|                                  |
| I1(/16)   | H1 (/17) dan H2 (/21)|
| **Total** |       **/16**        |

Berdasarkan total IP dan netmask yang dibutuhkan, Subnet besar yang dibentuk memiliki `NID 192.184.0.0` dengan `Netmask /16`.

#### Menghitung pembagian IP berdasarkan `NID` dan `Netmask` yang didapatkan

![CIDR Pohon](/screenshot/CIDR%20Pohon.PNG)

#### Hasil pembagian IP

![CIDR Pembagian IP](/screenshot/CIDR%20Pembagian%20IP.PNG)

### Routing

#### Membuat topologi dengan _GNS3_

![Topologi GNS3 CIDR](/screenshot/CIDR_TopologiGNS3.png)

#### Mengatur _Network Configuration_ masing-masing interface pada setiap perangkat

Sesuaikan network configuration node pada GNS3 sebagai berikut sesuai dengan interface yang dibuat pada topologi:

- **The Resonance**
  ```
  auto eth0
  iface eth0 inet dhcp

  #A7
  auto eth1
  iface eth1 inet static
    address 192.184.132.1
    netmask 255.255.255.252

  #A8
  auto eth2
  iface eth2 inet static
    address 192.184.130.1
    netmask 255.255.255.252

  #A10
  auto eth3
  iface eth3 inet static
    address 192.184.96.1
    netmask 255.255.255.252

  #A6
  auto eth4
  iface eth4 inet static
    address 192.184.32.1
    netmask 255.255.255.252
  ```
- **The Magical**
  ```
  #A8
  auto eth0
  iface eth0 inet static
    address 192.184.130.2
    netmask 255.255.255.252
          gateway 192.184.130.1

  #A9
  auto eth1
  iface eth1 inet static
    address 192.184.128.1
    netmask 255.255.254.0
  ```
- **The Order**
  ```
  #A6
  auto eth0
  iface eth0 inet static
    address 192.184.32.2
    netmask 255.255.255.252

  #A4
  auto eth1
  iface eth1 inet static
    address 192.184.8.1
    netmask 255.255.255.252

  #A5
  auto eth2
  iface eth2 inet static
    address 192.184.16.1
    netmask 255.255.255.192
  ```
- **The Minister**
  ```
  #A4
  auto eth0
  iface eth0 inet static
    address 192.184.8.2
    netmask 255.255.255.252

  #A2
  auto eth1
  iface eth1 inet static
    address 192.184.5.1
    netmask 255.255.255.252

  #A1
  auto eth2
  iface eth2 inet static
    address 192.184.0.1
    netmask 255.255.252.0
  ```
- **The Dauntless**
  ```
  #A2
  auto eth0
  iface eth0 inet static
    address 192.184.5.2
    netmask 255.255.255.252

  #A3
  auto eth1
  iface eth1 inet static
    address 192.184.4.1
    netmask 255.255.255.0
  ```
- **The Instrument**
  ```
  #A10
  auto eth0
  iface eth0 inet static
    address 192.184.96.2
    netmask 255.255.255.252

  #A12
  auto eth1
  iface eth1 inet static
    address 192.184.73.1
    netmask 255.255.255.252

  #A15
  auto eth2
  iface eth2 inet static
    address 192.184.68.1
    netmask 255.255.255.252

  #A11
  auto eth3
  iface eth3 inet static
    address 192.184.80.1
    netmask 255.255.255.128
  ```
- **The Profound**
  ```
  #A12
  auto eth0
  iface eth0 inet static
    address 192.184.73.2
    netmask 255.255.255.252

  #A13
  auto eth1
  iface eth1 inet static
    address 192.184.72.1
    netmask 255.255.255.128

  #A14
  auto eth2
  iface eth2 inet static
    address 192.184.72.129
    netmask 255.255.255.128
  ```
- **The Firefist**
  ```
  #A15
  auto eth0
  iface eth0 inet static
    address 192.184.68.2
    netmask 255.255.255.252

  #A16
  auto eth1
  iface eth1 inet static
    address 192.184.66.1
    netmask 255.255.254.0

  #A17
  auto eth2
  iface eth2 inet static
    address 192.184.64.1
    netmask 255.255.255.0
  ```
- **The Queen**
  ```
  #A17
  auto eth0
  iface eth0 inet static
    address 192.184.64.3
    netmask 255.255.255.0

  #A18
  auto eth1
  iface eth1 inet static
    address 192.184.65.1
    netmask 255.255.255.252
  ```

##### Client

- **Johan (100 Host)**

```
auto eth0
iface eth0 inet static
	address 192.184.4.3
	netmask 255.255.255.0
	gateway 192.184.4.1
```

- **Phanora (150 Host)**

```
auto eth0
iface eth0 inet static
	address 192.184.4.2
	netmask 255.255.255.0
	gateway 192.184.4.1
```

- **Guideau (1000 Host)**

```
auto eth0
iface eth0 inet static
	address 192.184.0.2
	netmask 255.255.252.0
	gateway 192.184.0.1
```

- **Ashaf (50 Host)**

```
auto eth0
iface eth0 inet static
	address 192.184.16.2
	netmask 255.255.255.192
	gateway 192.184.16.1
```

- **Haines (70 Host)**

```
auto eth0
iface eth0 inet static
	address 192.184.128.2
	netmask 255.255.254.0
	gateway 192.184.128.1
```

- **Corvekt (200 Host)**

```
auto eth0
iface eth0 inet static
	address 192.184.128.3
	netmask 255.255.254.0
	gateway 192.184.128.1
```

- **Matt Cugat (120 Host)**

```
auto eth0
iface eth0 inet static
	address 192.184.80.2
	netmask 255.255.255.128
	gateway 192.184.80.1
```

- **Spendrow (120 Host)**

```
auto eth0
iface eth0 inet static
	address 192.184.72.2
	netmask 255.255.255.128
	gateway 192.184.72.1
```

- **Helga (70 Host)**

```
auto eth0
iface eth0 inet static
	address 192.184.72.130
	netmask 255.255.255.128
	gateway 192.184.72.129
```

- **Oakleave (500 Host)**

```
auto eth0
iface eth0 inet static
	address 192.184.66.2
	netmask 255.255.254.0
	gateway 192.184.66.1
```

- **Keith (210 Host)**

```
auto eth0
iface eth0 inet static
	address 192.184.64.2
	netmask 255.255.255.0
	gateway 192.184.64.1
```

##### Server

- **The Beast**

```
auto eth0
iface eth0 inet static
	address 192.184.132.2
	netmask 255.255.255.252
	gateway 192.184.132.1
```

- **The Witch**

```
auto eth0
iface eth0 inet static
	address 192.184.65.2
	netmask 255.255.255.252
	gateway 192.184.65.1
```

#### _Statics Route Configuration_

Berikut adalah konfigurasi routing yang kelompok kami gunakan.

- **The Resonance**

```
A9 -> route add -net 192.184.128.0 netmask 255.255.254.0 gw 192.184.130.2
E1 -> route add -net 192.184.8.0 netmask 255.255.255.252 gw 192.184.32.2
F1 -> route add -net 192.184.64.0 netmask 255.255.224.0 gw 192.184.96.2
```

- **The Order**

```
Default -> route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.184.32.1
C1 -> route add -net 192.184.0.0 netmask 255.255.248.0 gw 192.184.8.2
```

- **The Minister**

```
Default -> route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.184.8.1
A3 -> route add -net 192.184.4.0 netmask 255.255.255.0 gw 192.184.5.2
```

- **The Dauntless**

```
Default -> route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.184.5.1

```

- **The Magical**

```
Default -> route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.184.130.1
```

- **The Instrument**

```
Default -> route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.184.96.1
C3 -> route add -net 192.184.72.0 netmask 255.255.255.0 gw 192.184.73.2
C2 -> route add -net 192.184.64.0 netmask 255.255.252.0 gw 192.184.68.2
```

- **The Profound**

```
Default -> route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.184.73.1
```

- **The Firefist**

```
Default -> route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.184.68.1
A18 -> route add -net 192.184.65.0 netmask 255.255.255.252 gw 192.184.64.3
```

- **The Queen**

```
Default -> route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.184.64.1
```

### Testing

Dilakukan beberapa testing sebagai berikut:

- `Johan` -> `The Witch`
- `Guideau` -> `Oakleave`
- `Ashaf` -> `Helga`
- `Matt Cugat` -> `The Beast`
- `Haines` -> `Spendrow`

Hasil Testing:

- `Johan` -> `The Witch`
![CIDR Test 1](/screenshot/CIDR_Test1.png)
- `Guideau` -> `Oakleave`
![CIDR Test 2](/screenshot/CIDR_Test2.png)
- `Ashaf` -> `Helga`
![CIDR Test 3](/screenshot/CIDR_Test3.png)
- `Matt Cugat` -> `The Beast`
![CIDR Test 4](/screenshot/CIDR_Test4.png)
- `Haines` -> `Spendrow`
![CIDR Test 5](/screenshot/CIDR_Test5.png)

## Kendala

Berikut adalah kendala kami selama mengerjakan praktikum modul 4 ini.

- Routing untuk CIDR sempat tidak dibuat pada subnet yang lebih tinggi, sehingga routing table berisi lebih banyak subnet tingkatan A

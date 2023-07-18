---
title: Client API
---

Berikut adalah dokumentasi API dari program akvirtual agar anda bisa mengatur program ini dari luar (secara programatic).

## Menggabungkan Parameter

Untuk menggabungkan 2 atau lebih parameter.

Misal anda ingin menggabungkan [autoenter](#auto-enter) API dan [Default Avatar](#default-avatar) API maka anda bisa menulis nya dengan.

```
https://akvirtual.id/jEyhDwX/ruang-rapat?autoenter=1&avatar_url=AVATAR_URL
```

Contoh

```
https://akvirtual.id/jEyhDwX/ruang-rapat?autoenter=1&avatar_url=https://d1a370nemizbjq.cloudfront.net/303e0c8a-af3e-4bda-b593-39b1ee20a8d3.glb
```


## Parameter

### Auto Enter

Penguna akan langsung masuk ke dalam ruangan

Dengan menambah parameter `?autoenter=1` ke url asli

**Contoh pengaturan:**

URL asli adalah sebagai berikut

```
https://akvirtual.id/jEyhDwX/ruang-rapat
```

Maka url yang telah di atur untuk autoenter adalah

```
https://akvirtual.id/jEyhDwX/ruang-rapat?autoenter=1
```

**Contoh penggunaan:**

Semisal anda ingin membuat ruangan yang mempunyai link ke ruangan lain.

Dengan link tersebut pengguna akan otomatis masuk ke ruangan yang dituju.

### Default Avatar

Misal anda ingin membuat acara dengan pengunjung yang hadir di acara tersebut secara default memakai seragam / *dress code* / avatar tertentu.

Caranya dengan menambah parameter `?avatar_url=URL_AVATAR` ke url ruangan

Dimana `URL_AVATAR` adalah link download file glb avatar.

**Contoh pengaturan:**

URL asli adalah sebagai berikut

```
https://akvirtual.id/jEyhDwX/ruang-rapat
```

dengan penambahan parameter maka menjadi

```
https://akvirtual.id/jEyhDwX/ruang-rapat?avatar_url=https://d1a370nemizbjq.cloudfront.net/303e0c8a-af3e-4bda-b593-39b1ee20a8d3.glb
```

---
layout: post
title: "Merangkum: Replication DDIA"
categories: data-engineering
wip: true
---

## Replication

Membahas proses replication yang artinya menyimpan salinan data yang sama di mesin lain. Dengan tujuan : 

1. Lower latency, misal ke server yang lebih dekat dengan user  
2. Higher system availability melalui banyaknya node yang juga benefisial untuk;  
3. Higher read throughput.

<!--more-->

## Backup vs Replication
Proses replication tidak menggantikan fungsi backup, malah keduanya bersifat komplementer. Backup membantu proses replication melalui fungsi snapshotnya, dan replication membantu backup dalam mengarsipkan replication logs. 

Replication susah ketika data yang lu replicate itu berubah-ubah. Untuk mencapai tujuan itu, digunakanlah 3 pendekatan: Single leader, multi leader dan leaderless replication.

## Single Leader
Write hanya dapat dilakukan ke satu node utama, yang dipanggil sebagai leader. Dari situ leader menyalin data ke tiap followernya. Menyalin data disini adalah oversimplikasi, chapter ini akan membahas lebih lanjut mengenai proses replkasi dalam subchapter Implementation of Replication Logs.  
![Single-leader replication dari DDIA](/images/single-leader-replication.png)

## Sync vs Async Replication
Ada 2 pendekatan dalam melakukan replication di single leader replication. Sync memastikan write dari leader benar-benar terjadi sebelum disebut sukses, sedangkan async tidak. Seperti pembahasan sync vs async pada biasanya, tiap pendekatan memliki plus minusnya masing-masing.

|  | Data | Behaviour |
| :---- | :---- | :---- |
| Sync  | Up-to-date | Blocking |
| Async | Belum tentu | Nonblocking |

Melihat sifat sync yang blocking, jika semua node sync, selain high latency, juga akan bermasalah ketika 1 node mengalamai power failure dan alasan lain yang mengakibatkan node tidak online, alhasil blocking, dan writes tidak dapat dilakukan sampai node online kembali.

Single leader replication dipakai sbg fitur bawaan relational database seperti PostgreSQL dan MySQL.

## Handling Node Outages

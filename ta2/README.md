## Tugas Akhir Praktikum Jaringan Komputer Judul 2
**Link Video Presentasi**: https://youtu.be/tDyPtPev-o0

### **Ping Gagal**

<img width="831" height="258" alt="Screenshot 2025-11-06 010959" src="https://github.com/user-attachments/assets/05b83e05-0c39-4db4-beea-e236cf9ebcf7" />

Ping gagal karena router yang berperan sebagai default gateway belum dikonfigurasi, sehingga belum terjadi proses routing untuk lalu lintas Layer 3 antar subnet. PC-A dan PC-B berada di jaringan yang berbeda, sementara switch hanya berfungsi pada Layer 2 (Ethernet) dan tidak dapat melakukan routing antar subnet. Saat PC-A mencoba melakukan ping ke PC-B, paket seharusnya melewati router. Namun karena interface router belum memiliki alamat IP dan belum aktif sebagai gateway, router tidak dapat meneruskan paket tersebut, sehingga ping dari PC-A ke PC-B gagal.

### **Ping Berhasil**

<img width="825" height="218" alt="Screenshot 2025-11-06 011027" src="https://github.com/user-attachments/assets/b5f902eb-1b24-41ca-9d48-66945d7be7aa" />

Ping berhasil karena interface pada router telah dikonfigurasi dengan IP gateway untuk masing-masing subnet, sehingga router kini mampu melakukan routing antar subnet. Ketika PC-A mengirim paket ke alamat di luar subnetnya, paket tersebut diteruskan ke default gateway, lalu router mengarahkan paket tersebut menuju subnet tempat PC-B berada. Dengan begitu, lalu lintas ICMP tidak lagi berhenti di layer 2, tetapi diteruskan melalui layer 3 oleh router, sehingga balasan dari PC-B dapat kembali ke PC-A dengan sukses.

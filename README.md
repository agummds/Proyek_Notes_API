# Proyek_Notes_API
Ini adalah repository untuk proyek Proyek Notes API pada submission dicoding kelas Menjadi Google Cloud Artchitect


Terdapat beberapa kriteria utama yang harus Anda penuhi dalam menyelesaikan Proyek Notes API.
# Kriteria 1: Simpan Docker Image di Google Container Registry
Sebelum bisa men-deploy aplikasi ke Google Kubernetes Engine, Anda perlu melakukan build Docker image terlebih dahulu, kemudian mengunggahnya ke Google Container Registry.

Source code dari Notes API bisa Anda dapatkan di GitHub repository berikut: https://github.com/dicodingacademy/a332-google-cloud-architect-labs.

# Kriteria 2: Deploy ke Google Kubernetes Engine
Silahkan deploy Docker image Anda ke **Google Kubernetes Engine**.
# Langkah-Langkah
## Membuat VM
1. Untuk tahap pertama, kita harus membuat **virtual machine** terlebih dahulu dan enable **Compute Engine API**
2. Setelah enable, pilih bagian **create instance** untuk membuat instance, Setelah muncul tampilan pembuatan instance. Anda dapat mengisi berbagai macam konfigurasi untuk VM, seperti nama instance, region, zone, machine type, dan jenis sistem operasi.
3. Jangan lupa untuk mengizinkan lalu lintas HTTP dan HTTPS dengan mencentang Allow HTTP traffic dan Allow HTTPS traffic. Ini dilakukan agar VM Anda dapat diakses secara global melalui internet.
4. Selanjutnya kita akan menginstall web server pada VM tersebut. Jadi silakan salin **External IP** dan lakukan **SSH** ke mesin virtual Anda dengan mengeklik tombol **SSH** pada kolom **Connect** di **Cloud Console**.
5. Setelah muncul pop-up maka langsung saja kita ketikkan perintah berikut
```cmd
sudo apt update
```
6. Kemudian install apache web server dengan perintah berikut
```cmd
sudo apt install apache2 -y
```
7. Lalu, silakan kembali ke Cloud Console dan akses web server Anda menggunakan external IP dengan format **http://external_IP/**.

## Menambahkan Persistent Disk ke VM
1. Masuk ke halaman VM yang sudah dibuat, kemudian klik **Edit**.
2. Pada bagian Additional disks, pilih **Add new disk**.
3. Selanjutnya Anda perlu mengisi form berisi konfigurasi disk yang akan dibuat.
4. Jika seluruh form sudah terisi, pilih **Done**.
5. Pilih **Save** untuk menyimpan perubahan.

## Deploy Aplikasi dengan Google Kubernetes Engine
1. buka **Cloud Shell** dan langsung clone repository yang sudah disediakan.
```cmd
git clone -b main https://github.com/dicodingacademy/a332-google-cloud-architect-labs


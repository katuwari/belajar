# belajar

Repo ini merupakan catatan dari kegiatan belajar kubernetes dengan mendemonstrasikan gitops kubernetes workflow menggunakan Docker, kind, Flux, and GitHub. Fungsi dari masing - masing komponen adalah:

1. Docker digunakan untuk membangun dan menjalankan aplikasi dalam bentuk container. Dalam hal ini hanya digunakan sebagai node kubernetes
2. kind (Kubernetes in Docker) digunakan untuk menyediakan cluster Kubernetes secara lokal.
3. GitHub berperan sebagai single source of truth. Setiap perubahan yang di-merge ke branch utama akan secara otomatis disinkronkan dan diterapkan ke cluster Kubernetes oleh Flux.
4. Flux secara terus-menerus menjaga agar kondisi cluster tetap selaras dengan isi repositori GitHub ini. Seluruh perubahan aplikasi dan infrastruktur dikelola secara deklaratif melalui Git.

Setup ini ingin mereplikasi apa yang digunakan industri pada umumnya yaitu::

1. Deployment otomatis menggunakan CI/CD
2. Infrastruktur yang berbasis versi dan dapat diaudit
3. Update yang aman melalui pull request dengan part reviewing

## Tools dan versi yang digunakan

1. Docker version 26.1.5+dfsg1, build a72d7cd
2. Kind version 0.30.0
3. Flux version 2.7.5

## Instalasi dan Konfigurasi

### Docker

Docker hanya perlu diinstall tanpa ada konfigurasi yang dilakukan secara umum. Docker yang digunakan dalam proyek ini adalah docker.io dengan cara install sebagai berikut:

```
sudo apt install docker.io -y
```

### Kind

Sedangkan kind setelah diinstall dengan command berikut:

```
brew install Kind
```

ada konfigurasi yang dilakukan untuk create cluster yaitu:

```
kind create cluster --name belajar
```

dimana kubernetes cluster yang akan di create bernama kind-belajar

```
❯ k config current-context
kind-belajar
```

### GitHub

Untuk GitHub tidak ada instalasi karena yang digunakan adalah GitHub.com. Yang perlu dilakukan adalah membuat repository baik public atau private dan create "personal access token" yang nantinya akan digunakan oleh Flux untuk pull repo

### Flux

Untuk Flux konfigurasi yang dilakuakn lumayan banyak, diawali dengan instalasi menggunakan command berikut:

```
curl -s https://fluxcd.io/install.sh | sudo bash
```

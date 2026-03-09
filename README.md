# Command Dasar Linux & Node

<img width="1532" height="774" alt="Screenshot 2026-03-10 045526" src="https://github.com/user-attachments/assets/3d50495f-4164-47bb-b785-9933fe9d6e28" />

# 1. File System Hierarchi

- `/` : Menduduki posisi puncak didalam hirarki.
- `bin` : Direktori ini berisi perintah dasar yang dibutuhkan oleh system maupun user.
- `boot` : Berisi program dan data yang dibutuhkan pada saat melakukan proses booting (menjalankan) system.
- `dev` : Direktori tempat file device.
- `etc` : berisi file konfigurasi system.
- `home` : direktori tempat menyimpan data user.
- `var` : Untuk menyimpan informasi proses, seperti system history, access logs, dan error logs.
- `mnt` : Direktori untuk menyimpan mount point sementara.
- `opt` : Direktori ini berisi paket-paket Aplikasi Opsional (paket-paket yang diinstall user).

# 2. File & Directory Management

## File Management

- `touch` : Membuat file tanpa content
- `echo/vim/vi/nano` : Membuat file dengan content
- `cat` : Menampilkan isi content file
- `head` : Menampilkan 10 baris pertama sebuah file
- `tail` : Menampilkan 10 baris terakhir sebuah file
- `rm` : Menghapus file
- `cp` : Menyalin file dan directory
- `mv` : Memindahkan/me rename file dan directory

## Directory Management

- `cd` : Masuk/keluar directory
- `mkdir` : Membuat directory
- `rmdir` : Menghapus directory
- `ls` : Menampilkan isi directory
- `pwd` : Menampilkan di directory mana kita berada

Kembali ke folder sebelumnya
```
cd ..
```
### 3. Update & Upgrade System

```
#Update & upgrade terpisah
~ sudo apt update
~ sudo apt upgrade

#update keseluruhan langsung
sudo apt update && sudo apt upgrade -y
```

### 4. GIT

```
#install git
apt install git
```
```
#check versi git
git --version
```
```
#clone GitHub
git clone link-github-yg-mau-di-clone
```
```
#hapus git
sudo apt remove git
```
### 5. SCREEN

```
#install screen
apt install screen
```
```
#buat screen
screen -S namascreen
```
```
#simpan screen
CTRL + A + D
```
```
#balik ke screen yang ada
screen -r namascreen
```
```
#check screen yang berjalan
screen -ls
```
```
#hapus screen
screen -X -S namascreen quit
```
```
#uninstall screen
sudo apt remove screen
```
### 6. Docker
```
#install docker
sudo apt-get install -y ca-certificates curl gnupg lsb-release && curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg && echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null && sudo apt-get update && sudo apt-get install -y docker-ce docker-ce-cli containerd.io && sudo apt-mark hold docker-ce docker-ce-cli containerd.io
```
```
#lihat list docker yang berjalan
docker ps -a
```
```
#stop docker yang berjalan
docker stop <IDContainer>
```
```
#hapus docker yang berjalan
docker rm <IDContainer>
```
```
#uninstall docker
sudo apt-mark unhold docker-ce docker-ce-cli containerd.io && sudo apt-get remove --purge -y docker-ce docker-ce-cli containerd.io && sudo rm -rf /var/lib/docker /var/lib/containerd && sudo rm /etc/apt/sources.list.d/docker.list && sudo apt-get autoremove -y && sudo apt-get autoclean
```

### 7. Go (Golang)
```
#install go
LATEST_GO=$(curl -s https://go.dev/VERSION?m=text) && wget https://go.dev/dl/${LATEST_GO}.linux-amd64.tar.gz && sudo rm -rf /usr/local/go && sudo tar -C /usr/local -xzf ${LATEST_GO}.linux-amd64.tar.gz && echo "export PATH=\$PATH:/usr/local/go/bin:\$HOME/go/bin" >> ~/.bash_profile && source ~/.bash_profile && go version
```
```
#uninstall go
sudo rm -rf /usr/local/go && sed -i '/\/usr\/local\/go\/bin/d' ~/.bash_profile && sed -i '/\/go\/bin/d' ~/.bash_profile && source ~/.bash_profile
```

### 8. Node js
```
#install node js
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.4/install.sh | bash && source ~/.bashrc && nvm install node && nvm use node && node -v
```
```
#uninstall node js
rm -rf ~/.nvm && sed -i '/NVM_DIR/d' ~/.bashrc && source ~/.bashrc
```
```
#menjalankan/run file js (node.js)
node namafile.js
```
### 9. Python
```
#install Python
sudo apt-get update && sudo apt-get install -y software-properties-common && sudo add-apt-repository -y ppa:deadsnakes/ppa && sudo apt-get update && sudo apt-get install -y python3 python3-pip && python3 --version && pip3 --version
```
```
#uninstall python
sudo apt-get remove --purge -y python3.* && sudo apt-get autoremove -y && sudo apt-get autoclean
```
```
#menjalankan/run file py (python)
python3 namafile.py
```
### 10. Update Sistem VPS
```
sudo apt update && sudo apt upgrade -y
sudo apt install curl tar wget clang pkg-config libssl-dev jq build-essential bsdmainutils git make ncdu gcc jq chrony liblz4-tool -y
```

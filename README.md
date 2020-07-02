#GIT COMMAND

-konfigurasi awal
	git config --global user.name "Petani Kode"
	git config --global user.email contoh@petanikode.com

-cek konfigurasi
	git config --list

-create repository dengan folder proyek-01
	git init proyek-01

-create repository pada working folder
	git init .

.gitignore	
.gitignore merupakan sebuah file yang berisi daftar nama-nama file dan direktori yang akan diabaikan oleh Git.
Perubahan apapun yang kita lakukan terhadap file dan direktori yang sudah masuk ke dalam daftar .gitignore tidak akan dicatat oleh Git.
Cara mengunakan .gitignore, buat saja sebuah file bernama .gitignore dalam root direktori proyek/repositori.

contoh 
/vendor/
/upload/
/cache
test.php


git diff -> akan membandingkan perubahan yang baru saja dilakukan dengan revisi/commit terakhir.

git diff cf08ca0837cf26f1c595be36bb3a6b815e311be1
git diff nama file


git checkout index.html -> download dari repository

git reset index.html -> mereset file yg status nya sudah stage kembali ke modified


Untuk kembali ke 3 commit sebelumnya, kita bisa menggunakan perintah berikut.

git checkout HEAD~3 index.html

Jika kita ingin mengembalikan semua file ke suatu commit, kita bisa melakukannya dengan perintah:

git revert -n <nomer commit>

Jika kita ingin mengembalikan semua file ke suatu commit, kita bisa melakukannya dengan perintah:

git revert -n <nomer commit>


- Tambah branch 
	Pada repositori, buatlah sebuah cabang baru.
	git branch halaman_login
	
	Setelah itu, pindah ke cabang yang baru saja kita buat dengan perintah:
	git checkout halaman_login

- Menggabungkan Cabang
Anggaplah kita sudah selesai membuat fitur login di cabang halaman_login. Sekarang kita ingin Menggabungkannya denga cabang master (utama).

Pertama, kita harus pindah dulu ke cabang master.

git checkout master
Setelah itu, barulah kita bisa menggabungkan dengan perintah git merge.

git merge halaman_login

Menghapus Cabang
git branch -d halaman_login


Misalnya kita ingin membuat cabang baru berdasarkan kondisi kode di masa lalu, maka kita bisa menggunakan perintah:

git checkout -b nama_cabang <nomer_commit>


Git Reset
Perintah git reset sering disebut sebagai perintah berbahaya yang dapat menghancurkan catatan sejarah perubahan.

Hati-hati! Perintah ini membuat kita tidak bisa kembali lagi ke masa depan. Mau tidak mau, kita harus menulis ulang sejarah.


Revert artinya mengembalikan. Perintah ini lebih aman daripada git reset, karena tidak akan menghapus catatan sejarah revisi.

Revert akan akan mengambil kondisi file yang ada di masa lalu, kemudian menggabungkannya dengan commit terakhir.


Remote Repository

git remote add github git@github.com:suharbramar/belajar-git.git

untuk menghapus dan mengubah nama remote dapat dilakukan dengan perintah berikut:

Ubah nama remote:

git remote rename github kantor
Keterangan:

github adalah nama lama
kantor adalah nama baru

Hapus remote:

git remote remove github


Setting ssh for github 

Windows 
1. ssh-keygen
2. ps -e | grep [s]sh-agent
   Kalau hasilnya seperti di bawah ini, berati SSH Agent sudah berjalan.

Cek SSH Agent

Tapi, kalau belum berjalan, gunakan perintah berikut ini untuk menjalankan SSH agent:

ssh-agent /bin/bash
Berikutnya kita Load SSH Key. Gunakan perintah:

ssh-add ~/.ssh/id_anda

Kemudian untuk mengecek, gunakan perintah:

ssh-add -l

3. Tambahkan ssh key ke github 
   Sebelumnya ambil dulu kuncil publik yang sudah anda buat, gunakan perintah cat.

   cat ~/.ssh/id_anda.pub
   
   Copy semua teks yang ditampilkan.
   
   Lalu masuk ke Settings>SSH and GPG Keys, buat kunci baru dengan mengelik New SSH Key. Lalu masukkan key yang sudah dibuat.

4. Uji Konektifitas 
	Ketik perintah berikut untuk menguji konektivitas SSH ke Github

	ssh -T git@github.com
	
	
visual studio (after setting ssh on windows)
start-ssh-agent

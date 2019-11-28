# **GITHUB**

### **Tools Utama**
1. **Git** sebagai open source code versioning control system

2. **Github** adalah sebuah platform untuk menyimpan source code pada cloud. Banyak yang menyebut sebagai Code Versioning, yang merupakan suatu bentuk manajemen source code yang didesain untuk melacak jejak perubahan-perubahan code selama pengembangan sebuah software berlangsung.


### **Keuntungan Penerapan SCM**
1. **Cloud Storage**
: Kode akan disimpan pada penyimpanan berbasis cloud.

2. **Private Workspace**
: Dapat dengan bebas melakukan perubahan code di mesin pribadi sampai melakukan *Push* untuk *Commit* yang ingin dilakukan

3. **Distributed Source Code**
: Dapat mendistribusikan code kepada siapa pun orang yang dikehendaki dan berkolaborasi dengan mereka

4. **Traceable and Trackable Changes**
: Dapat dengan mudah melacak perubahan code yang dilakukan Anda dan team anda

5. **Version Control**
: Jika perubahan yang baru dilakukan tidak lebih baik dari versi sebelumnya, dapat dengan mudah kembali ke versi code yang lawas

Atomic commit adalah melakukan commit pada perubahan perubahan sekecil atom. Artinya adalah tidak direkomendasikan untuk melakukan perubahan yang banyak, lalu kemudian melakukan commit untuk perubahan yang banyak tersebut.
Di merekomendasikan untuk langsung melakukan commit pada perubahan kecil yang dilakukan, untuk membuat software dengan manajemen yang baik dan memiliki predikat *`maintanable, scalable, and well developed.`*


- *Tracing* : Menelusuri perubahan code
- *Annotation* : Menelusuri siapa yang melakukan perubahan
- *Braching Management* : Mengelola code versioning

> Warna kuning disebelah kiri pada code editor mengindikasikan bahwa terdapat perubahan didalam file.
> ![Perubahan dalam git](NOTE\img\perubahan-dalam-git.png "Perubahan dalam github")

> VS Code, Android Studio, dll. memiliki fitur git GUI. Icon bergambar branch sebelah kiri (bernama source control)


### **Komponen-Komponen dan Operasi yang terdapat dalam Source Code Management**
1. *`Remote Environment`*
: berada pada cloud storage yang hanya memiliki satu komponen yaitu `Remote repository`

2. *`Local Environment`*
: berada pada komputer yang digunakan memiliki komponen sebagai berikut :
    - *Local Repository* : berisi folder dan file code.
    - *Workspace atau Working Directory* : biasa disebut unstage area, berisikan perubahan yang sedang dilakukan.
    - *Stage Area* : berisi perubahan yang disimpan sementara untuk kemudian dilakukan commit, perubahan yang disimpan di stage area masih dapat dilakukan penggantian.
    - *Commit Area* : berisi perubahan yang telah dilakukan Commit, perubahan pada Commit Area tidak dapat dilakukan penggantian atau untuk melakukannya dapat melakukan commit yang lain.
    - *Stash Area* : menyimpan semua perubahan yang ada di working area.
    - *Branch* : sebuah pointer didalam repository untuk menentukan arah commit, sehingga dapat membuat cabang dari serangkaian commit yang dilakukan.
    - *Tag* : sebuah label yang diberikan pada sebuah Commit. Label apapun bisa diberikan seperti contohnya label Release Point

![Diagram Komponen SCM](/NOTE\img\diagram-komponen-scm.png "Diagram Komponen SCM")
![Diagram Komponen SCM 2](NOTE\img\diagram-komponen-scm2.png "Diagram Komponen SCM 2")

3. *`Developer`*
: Sebagai SCM user (Anda dan Team anda)

### **SCM Operations**
`Operasi SCM` adalah aktivitas yang dilakukan oleh developer dalam mengelola source code.
1. *`Remote Activites`*
    - *Clone* : Mendownload remote repository ke dalam computer sebagai local repository
    - *Fetch* : Sinkronisasi versi terbaru pada remote repository ke local repository
    - *Pull* : Mengambil semua perubahan dari remote repository ke local repository pada suatu branch
    - *Push* : Meng-upload commit dari local repository ke remote repository pada suatu branch

2. *`Local Activites`*
    - *Checkout* : Mengganti working area ke suatu branch
    - *Stash* : Menyimpan semua perubahan di working directory ke stash area dan membersihkan semua perubahan di working directory
    - *Apply Stash* : Mengambil kembali perubahan yang disimpan di stash area ke working directory
    - *Stage* : Menyimpan sementara perubahan dari working area untuk kemudian dilakukan commit
    - *Commit* : Membuat sebuah versi perubahan yang telah di-stage
    - *Branching* : Membuat sebuah pointer untuk menentukan arah penyimpanan commit
    - *Merge* : Mengambil semua perubahan dari sebuah branch ke branch lain sehingga menjadi satu arah
    - *Tagging* : Memberikan label dari sebuah commit. Biasanya dilakukan untuk Release Point

-----------------------
## **Membuat Repository**

> `git init`

Setelah code diatas dijalankan akan membuat direktori dengan nama .git didalam proyek. Direktori ini digunakan Git sebagai database untuk menyimpan perubahan yang kita lakukan.

> Jika folder .git dihapus maka rekaman atau catatan yang dilakukan oleh Git akan hilang

> `git status`

 Digunakan untuk melihat satus dari repository


------------------
## `.gitignore`

Merupakan sebuah file yang berisi daftar nama-nama file dan direktori yang akan diabaikan oleh Git. Perubahan apapun yang dilakukan terhadap file dan direktori yang masuk ke daftar `.gitignore` tidak akan dicatat oleh git. Cara menggunakannya buat saja sebuah file bernama `.gitignore` dalam root direktori repository.

> Pembuatan file ini sebaiknya dilakukan diawal pembuatan repositori


----------
### **Tiga Kelompok Kondisi File dalam Git**
1. `Modified`

*Modified* adalah kondisi dimana revisi atau perubahan sudah dilakukan, tetapi belum ditandai dan belum disimpan di version control.

2. `Staged`

*Staged* adalah kondisi dimana revisi sudah ditandai, tetapi belum disimpan di version control.
> untuk mengubah kondisi file dari modified ke staged gunakan perintah `git add nama_file`

3. `Commited`

*Commited* adalah kondisi dimana revisi sudah disimpan di version control.
> untuk mengubah kondisi file dari staged ke commited adalah `git commit`


---------------------
## **Membuat Revisi**

>`git add nama_file`

atau seperti ini :

>`git add nama_file1 nama_file2 nama_file3`

atau juga seperti ini :

>`git add *.html`

atau langsung untuk semua file dan direktori :

>`git add .`

Perintah diatas akan membuat status file menjadi *staged*

> `git commit -m "Initial Commite"`
>> `-m` dilakukan untuk menambahkan pesan pada setiap revisi

Perintah diatas akan membuat status file menjadi *commited* dan semua perubahan disimpan oleh Git


----------
## **Melihat Catatan Log**

> `git log`

atau :

> `git log nama_file`

atau :

> `git log --author='dendydandees'`

Digunakan untuk melihat catatan log perubahan pada repository


----------
## **Membatalkan Perubahan**

- Jika revisi yang dilakukan belum *staged* ataupun *commited*, bisa mengembalikannya menggunakan perintah

> `git checkout nama_file`
>> Hati-hati! perintah ini sangat berbahaya, karena akan menghapus perubahan yang baru saja dilakukan.

- Jika revisi yang dilakukan sudah dalam kondisi *staged* dan ingin dilakukan pembatalan.

> `git reset nama_file` untuk mengubahnya menjadi kondisi modified, kemudian bisa membatalkan perubahannya dengan perintah `git checkout nama_file`

- Jika revisi yang dilakukan sudah dalam kondisi commited dan ingin melakukan pembatalan. Harus mengetahui dahulu nomor commit sebelumnya dengan `git log`

> `git checkout nomor_commit nama_file` kemudian `git reset nama_file`

atau jika diinginkan melakukan *checkout* ke seluruh file pada nomor commite tersebut

> `git checkout nomor_commite`

> Perintah-perintah diatas akan mengembalikan semua file dalam kondisi pada nomer commit yang diberikan.

- Atau jika ingin mengembalikan semua file ke suatu commite

> `git revert -n nomor_commite`


-----------
## **Branch untuk mencegah confilct**

> *`branch`* merupakan komponen utama dalam code versioning atau Source Code Management.
>> *`Merged`* adalah aktivitas untuk menggabungkan semua perubahan pada satu *branch* ke *branch* lainnya. Pada perusahaan yang memiliki ativitas *merge* hanyalah Technical Leader. ![Alur Merged](NOTE\img\alurmerged.png "Alur Merged")
>>> Skema merging gambar diatas :
>>> 1. Developer melakukan beberapa perubahan di Branch B.
>>> 2. Developer melakukan beberapa perubahan di Branch C.
>>> 3. Branch B di Merge ke Branch A.
>>> 4. Branch A (yang kini sudah memiliki perubahan dari Branch B) di Merge ke Branch C.
>>> 5. Branch C (yang kini sudah memliki perubahan dari Branch A, hasil Merge dari Branch B) di Merge ke Branch A.

Untuk membuat branch baru :
> `git branch nama_branch`

Untuk melihat branch yang terdapat pada repository
> `git branch`
>> tanda `*(bintang)` berarti cabang yang sedang kita tempati.

pindah ke branch yang telah dibuat
> `git checkout nama_branch`

> Perubahan dalam branch tidak akan mempengaruhi branch master jika branch tambahannya belum dilakukan penggabungan

Untuk melakukan penggabungan branch pertama kita harus berada pada branch master, setelah itu melakukan penggabungan dengan perintah

> `git merge nama_branch`

Untuk melakukan penghapusan branch dilakukan dengan argument `*-d*` dan diikuti oleh nama cabangnya
> `git branch -d nama_branch`


----------
## **Perbedaan Commite dengan Stash**

*`stash`* adalah aksi untuk menyimpan semua perubahan yang masih berada di unstaged area. Perubahan ini dirasa belum cukup benar untuk dilakukan commit sehingga perubahan ini hanya akan disimpan di local computer.

> Stash hanya menyimpan perubahan dalam bentuk archives, sehingga jika archives ini hilang perubahan tersebut atau stash tersebut pun hilang

*`commite`* adalah aksi untuk menyimpan perubahan yang diyakini perubahan itu sudah benar, dan berkomitmen agar perubahan tersebut lah yang dipilih untuk masuk kedalam `commite history`.


----------
## **Berkolaborasi menggunakan Git**

*`Collaborators`* merupakan fitur dalam github yang memberikan hak akses kepada developer lain untuk berkolaborasi pada repository private. Collaborator dapat bebas melakukan merge branch ke branch milik creaotr repository tanpa perlu izin dari creator repository.

> Github membatasi 3 collaborator untuk repository private. Sedangkan BitBucket membatasi sampai 5 collaborator untuk repository private.


### **Pull Request**
*Pull Request* memungkinkan public repository dapat diakses oleh orang lain. Batasannya adalah mereka tidak bebas melakukan push ke branch Anda ataupun merge branch yang mereka buat ke branch milik anda.

Tetapi walaupun begitu orang lain masih bisa berkolaborasi walau statusnya bukan collaborators. Ketika mereka membuat branch baru dan selesai melakukan perubahan pada branch tersebut dan ingin melakukan merge branch ke branch master. Orang tersebut dapat melakukan *`request`* agar Anda dapat melakukan checkout pada branch mereka, melakukan pull, lalu melakukan merge ke branch master. *`request`* ini disebut *`Pull Request`*.

-----------
## **Membuat Repository Remote Github**

> - `git init`
> - `git add README.md`
> - `git commit -m "nama_commit"`
> - `git remote add origin https://github.com/username/nama_repository.git`
> - `git push -u origin master`

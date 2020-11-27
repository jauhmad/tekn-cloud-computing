
https://github.com/jauhmad/tekn-cloud-computing/blob/master/minggu-09/laporan%20praktikum.md
# Laporan Praktikum Teknologi Teknologi Cloud Computing - Minggu 09

## Materi

**Docker for Beginners - Linux**

## Disusun oleh:
* Nama : Jauhari Ahmad 
* No. Mhs : 205411167 


## Pembahasan Hasil Praktikum

**Docker for Beginners - Linux**
1. Membuat direktori linux_tweet_app

![Gambar 1](skrinsut/gambar_1.jpg)


2. Git clone repository ke direktori linux_tweet_app

![Gambar 2](skrinsut/gambar_2.jpg)


3. Jalankan beberapa container Docker sederhana. Memulai container baru. Output di bawah ini menunjukkan bahwa alpine: image terbaru tidak dapat ditemukan secara lokal. Ketika ini terjadi, Docker secara otomatis menariknya dari Docker Hub. Setelah gambar ditarik, nama host penampung ditampilkan (888e89a3b36b pada contoh di bawah).

![Gambar 3](skrinsut/gambar_3.jpg)


4. Docker membuat kontainer tetap berjalan selama proses yang dimulai di dalam kontainer masih berjalan. Dalam hal ini proses nama host keluar segera setelah keluaran ditulis. Ini berarti wadahnya berhenti. Namun, Docker tidak menghapus sumber daya secara default, sehingga kontainer masih ada dalam status Keluar. Buat daftar semua wadah.

![Gambar 4](skrinsut/gambar_4.jpg)


5. Jalankan container Docker dan akses shell nya

![Gambar 5](skrinsut/gambar_5.jpg)


6. Menjalankan beberapa perintah. ls / akan membuat daftar isi dari root director di wadah, ps aux akan menunjukkan proses yang sedang berjalan di wadah, cat / etc / issue akan menunjukkan distro Linux mana yang menjalankan container

![Gambar 6](skrinsut/gambar_6.jpg)


7. Ketik exit untuk keluar dari sesi shell. Ini akan menghentikan proses bash, menyebabkan penampung keluar.

![Gambar 7](skrinsut/gambar_7.jpg)


8. Periksa versi VM

![Gambar 8](skrinsut/gambar_8.jpg)


9. Jalankan container MySQL baru dengan perintah berikut.

![Gambar 9](skrinsut/gambar_9.jpg)


10. Buat daftar container yang sedang berjalan

![Gambar 10](skrinsut/gambar_10.jpg)


11. Anda dapat memeriksa apa yang terjadi di container Anda dengan menggunakan beberapa perintah Docker bawaan: log container docker dan container top docker

![Gambar 11](skrinsut/gambar_11.jpg)


12. Mari kita lihat proses yang berjalan di dalam penampung.

![Gambar 12](skrinsut/gambar_12.jpg)


13. Cantumkan versi MySQL menggunakan container docker exec.
docker container exec memungkinkan Anda menjalankan perintah di dalam container. Dalam contoh ini, kita akan menggunakan container docker exec untuk menjalankan baris perintah yang setara dengan mysql --user = root --password = $ MYSQL_ROOT_PASSWORD --version di dalam container MySQL kita.

![Gambar 13](skrinsut/gambar_13.jpg)


14. Anda juga dapat menggunakan container exec docker untuk menghubungkan ke proses shell baru di dalam container yang sudah berjalan. Menjalankan perintah di bawah ini akan memberi Anda shell interaktif (sh) di dalam container MySQL Anda.

![Gambar 14](skrinsut/gambar_14.jpg)


15. Pastikan Anda berada di direktori linux_tweet_app. Tampilkan konten Dockerfile.

![Gambar 15](skrinsut/gambar_15.jpg)


16. echo nilai variabel kembali ke terminal untuk memastikannya disimpan dengan benar.

![Gambar 16](skrinsut/gambar_16.jpg)


17. Gunakan perintah build docker image untuk membuat image Docker baru menggunakan instruksi di Dockerfile

![Gambar 17](skrinsut/gambar_17.jpg)


18. Gunakan perintah docker container run untuk memulai container baru dari gambar yang Anda buat. Karena penampung ini akan menjalankan server web NGINX, kami akan menggunakan tanda --publish untuk memublikasikan port 80 di dalam penampung ke port 80 pada host. Ini akan memungkinkan lalu lintas yang masuk ke host Docker pada port 80 untuk diarahkan ke port 80 di kontainer. Format bendera --publish adalah host_port: container_port.

![Gambar 18](skrinsut/gambar_18.jpg)


19. Cek website sudah berjalan

![Gambar 19](skrinsut/gambar_19.jpg)


20. Setelah Anda mengakses situs web Anda, matikan dan hapuslah.

![Gambar 20](skrinsut/gambar_20.jpg)


21. Mari mulai aplikasi web dan pasang direktori saat ini ke dalam penampung. Dalam contoh ini kita akan menggunakan tanda --mount untuk memasang direktori saat ini pada host ke / usr / share / nginx / html di dalam wadah. Pastikan untuk menjalankan perintah ini dari dalam direktori linux_tweet_app di host Docker Anda.

![Gambar 21](skrinsut/gambar_21.jpg)


22. Cek website sudah berjalan

![Gambar 22](skrinsut/gambar_22.jpg)


23. Salin index.html baru ke dalam penampung. Repo Git yang Anda tarik sebelumnya berisi beberapa versi berbeda dari file index.html. Anda dapat menjalankan perintah ls secara manual dari dalam direktori ~ / linux_tweet_app untuk melihat daftarnya. Pada langkah ini kita akan mengganti index.html dengan index-new.html.

![Gambar 23](skrinsut/gambar_23.jpg)


24. Refresh halaman website. Tampilan sudah berubah

![Gambar 24](skrinsut/gambar_24.jpg)


25. Hentikan dan hapus penampung yang sedang berjalan. Jalankan kembali versi saat ini tanpa bind mount.

![Gambar 25](skrinsut/gambar_25.jpg)


26. Tampilan website kembali seperti semula

![Gambar 25](skrinsut/gambar_22.jpg)


27. Hentikan dan hapus wadah saat ini

![Gambar 27](skrinsut/gambar_27.jpg)


28. Buat gambar baru dan beri tag sebagai 2.0. Ingatlah bahwa Anda sebelumnya memodifikasi file index.html di sistem file lokal host Docker. Ini berarti bahwa menjalankan perintah build image buruh pelabuhan lain akan membangun image baru dengan index.html yang diperbarui. Pastikan untuk menyertakan titik (.) Di akhir perintah.

![Gambar 28](skrinsut/gambar_28.jpg)



29. Mari kita lihat image di sistem.

![Gambar 29](skrinsut/gambar_29.jpg)


30. Jalankan penampung baru dari versi baru gambar.

![Gambar 30](skrinsut/gambar_30.jpg)


31. Refresh halaman website. Halaman web akan memiliki latar belakang oranye.Kami dapat menjalankan kedua versi secara berdampingan. Satu-satunya hal yang perlu kita waspadai adalah kita tidak dapat memiliki dua kontainer yang menggunakan port 80 pada host yang sama.Karena kami sudah menggunakan port 80 untuk penampung yang berjalan dari gambar versi 2.0, kami akan memulai penampung baru dan menerbitkannya di port 8080. Selain itu, kami perlu memberi penampung kami nama yang unik (old_linux_tweet_app)

![Gambar 31](skrinsut/gambar_31.jpg)


32. Jalankan penampung baru lainnya, kali ini dari gambar versi lama. Perhatikan bahwa perintah ini memetakan container baru ke port 8080 pada host. Ini karena dua kontainer tidak dapat memetakan ke port yang sama pada satu host Docker.

![Gambar 32](skrinsut/gambar_32.jpg)


33. Lihat versi lama situs web

![Gambar 33](skrinsut/gambar_33.jpg)


34. Buat daftar gambar di host Docker Anda. sebelum Anda dapat mendorong gambar Anda, Anda harus masuk ke Docker Hub.

![Gambar 34](skrinsut/gambar_34.jpg)


35. Push versi 1.0 aplikasi web Anda menggunakan push image docker.

![Gambar 35](skrinsut/gambar_35.jpg)


36. Push versi 2.0 

![Gambar 36](skrinsut/gambar_36.jpg)


37. Telusuri https://hub.docker.com/r/jauhmad/ dan melihat image Docker yang baru Anda push. Ini adalah repositori publik, jadi siapa pun dapat menarik gambar - Anda bahkan tidak memerlukan ID Docker untuk menarik gambar publik. Docker Hub juga mendukung repositori pribadi.

![Gambar 37](skrinsut/gambar_37.jpg)







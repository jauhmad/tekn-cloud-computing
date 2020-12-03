https://github.com/jauhmad/tekn-cloud-computing/blob/master/minggu-10/laporan%20praktikum.md
# Laporan Praktikum Teknologi Teknologi Cloud Computing - Minggu 10

## Materi

**Docker Networking**

## Disusun oleh:
* Nama : Jauhari Ahmad 
* No. Mhs : 205411167 


## Pembahasan Hasil Praktikum

**Docker Networking Hands-on Lab**
1. Perintah Docker Network

Perintah utama untuk mengkonfigurasi dan mengelola jaringan kontainer

![Gambar 1](skrinsut/gambar_1.jpg)


2. List networks

Perintah untuk melihat jaringan kontainer yang ada di host Docker saat ini.

![Gambar 2](skrinsut/gambar_2.jpg)


3. Inspect a network

Perintah untuk melihat detail konfigurasi jaringan. Rincian ini meliputi; nama, ID, driver, driver IPAM, info subnet, container yang terhubung, dan lainnya.

![Gambar 3](skrinsut/gambar_3.jpg)


4. List network driver plugins

Perintah menunjukkan banyak informasi menarik tentang instalasi Docker.


![Gambar 4](skrinsut/gambar_4.jpg)


5. The Basics Networking

Untuk memverifikasi setiap instalasi Docker yang dilengkapi dengan jaringan pra-bangun yang disebut bridge

![Gambar 5](skrinsut/gambar_5.jpg)


6. Install the brctl command and use it to list the Linux bridges on your Docker host. 

![Gambar 6](skrinsut/gambar_6.jpg)


7. List the bridges on your Docker host

![Gambar 7](skrinsut/gambar_7.jpg)


8. You can also use the ip a command to view details of the docker0 bridge.

![Gambar 8](skrinsut/gambar_8.jpg)


9. Create a new container

![Gambar 9](skrinsut/gambar_9.jpg)


10. You can verify our example container is up

![Gambar 10](skrinsut/gambar_10.jpg)


11. Run the brctl show command again.

![Gambar 11](skrinsut/gambar_11.jpg)


12. You can inspect the bridge network again

![Gambar 12](skrinsut/gambar_12.jpg)


13. Ping the IP address of the container from the shell prompt of your Docker host 

![Gambar 13](skrinsut/gambar_13.jpg)


14. Get the ID of the container started in the previous step

![Gambar 14](skrinsut/gambar_14.jpg)


15. Next, lets run a shell inside that ubuntu container

![Gambar 15](skrinsut/gambar_15.jpg)


16. Next, we need to install the ping program.

![Gambar 16](skrinsut/gambar_16.jpg)


17. Ping www.github.com

![Gambar 17](skrinsut/gambar_17.jpg)


18. Finally, lets disconnect our shell from the container

![Gambar 18](skrinsut/gambar_18.jpg)


19. Start a new container based off the official NGINX image

![Gambar 19](skrinsut/gambar_19.jpg)


20. Review the container status and port mappings

![Gambar 20](skrinsut/gambar_20.jpg)


21. Connect from your Docker host 

![Gambar 21](skrinsut/gambar_21.jpg)


22. Initialize a new Swarm, join a single worker node, and verify the operations worked.

![Gambar 22](skrinsut/gambar_22.jpg)


23. In the first terminal copy the entire docker swarm join ... command that is displayed as part of the output from your terminal output. Then, paste the copied command into the second terminal.

![Gambar 23](skrinsut/gambar_23.jpg)


24. Verify that both nodes are part of the Swarm

![Gambar 24](skrinsut/gambar_24.jpg)


25. Create a new overlay network called “overnet” 

![Gambar 25](skrinsut/gambar_25.jpg)


26. Verify the network was created successfully.

![Gambar 25](skrinsut/gambar_22.jpg)


27. Run the same docker network ls command from the second terminal.

![Gambar 27](skrinsut/gambar_27.jpg)


28.  View more detailed information about the “overnet” network. You will need to run this command from the first terminal.

![Gambar 28](skrinsut/gambar_28.jpg)



29. Create a new service called myservice on the overnet network with two tasks/replicas.

![Gambar 29](skrinsut/gambar_29.jpg)


30. Verify that the service is created and both replicas

![Gambar 30](skrinsut/gambar_30.jpg)


31. Verify that a single task (replica) is running on each of the two nodes in the Swarm 

![Gambar 31](skrinsut/gambar_31.jpg)


32. Now that the second node is running a task on the “overnet” network it will be able to see the “overnet” network. Lets run docker network ls from the second terminal to verify this.

![Gambar 32](skrinsut/gambar_32.jpg)


33. Get more detailed information about the “overnet” network and obtain the IP address of the task running on the second terminal.

![Gambar 33](skrinsut/gambar_33.jpg)


34. Execute the following commands from the first terminal. Notice that the IP address listed for the service task (container) running is different to the IP address for the service task running on the second node. Note also that they are on the same “overnet” network.

![Gambar 34](skrinsut/gambar_34.jpg)


35. Get the ID of the service task so that you can log in to it in the next step.

![Gambar 35](skrinsut/gambar_35.jpg)


36. Log on to the service task. Be sure to use the container ID from your environment as it will be different from the example shown below. We can do this.

![Gambar 36](skrinsut/gambar_36.jpg)


37. Install the ping command and ping the service task running on the second node where it had a IP address of 10.0.0.3 from the docker network inspect overnet command.

![Gambar 37](skrinsut/gambar_37.jpg)

38. Ping 10.0.0.3

![Gambar 38](skrinsut/gambar_38.jpg)

39. Test service discovery.

![Gambar 39](skrinsut/gambar_39.jpg)

40. Try and ping the “myservice” name from within the container by running ping -c5 myservice.

![Gambar 40](skrinsut/gambar_40.jpg)

41. Type the exit command to leave the exec container session and return to the shell prompt of your Docker host.

![Gambar 41](skrinsut/gambar_41.jpg)

42. Inspect the configuration of the “myservice” service

![Gambar 42](skrinsut/gambar_42.jpg)

43. Remove the service called myservice.

![Gambar 43](skrinsut/gambar_43.jpg)

44. Get a list of running containers.

![Gambar 44](skrinsut/gambar_44.jpg)

45. Gunakan docker kill <CONTAINER ID ...> untuk menghentikan contniner ubunut dan nginx
  
![Gambar 45](skrinsut/gambar_45.jpg)

46. Hilangkan node1 dari Swarm

![Gambar 46](skrinsut/gambar_46.jpg)

47. Hilangkan node2 dari Swarm

![Gambar 47](skrinsut/gambar_47.jpg)

47. Selesai



TUTORIAL - 5
### ScreenShoot JMeter Test Plans Before Profiling
### GUI Version
#### all-student
![image](https://github.com/rhaken/exercise-profiling/assets/39646450/81abb999-8eff-4b0f-9ee7-43fcea29f542)

#### all-student-name
![image](https://github.com/rhaken/exercise-profiling/assets/39646450/e4b91c2c-e28e-4333-a933-d1b1e45b85bd)

#### highest-gpa
![image](https://github.com/rhaken/exercise-profiling/assets/39646450/0ee895b6-dfac-4376-b88e-100f92735274)

### CLI Version
![image](https://github.com/rhaken/exercise-profiling/assets/39646450/c1a60432-650f-479d-af3a-88af09e18660)

### ScreenShoot JMeter Test Plans After Profiling (Optimization)
#### all-student
![image](https://github.com/rhaken/exercise-profiling/assets/39646450/97270ef1-527a-4038-ab69-33fe00e48fcc)

#### all-student-name
![image](https://github.com/rhaken/exercise-profiling/assets/39646450/d06db6e9-98dc-41f6-8515-7204d611cd78)

#### highest-gpa
![image](https://github.com/rhaken/exercise-profiling/assets/39646450/e335c124-9ef8-45e3-9776-6fe6356de113)


### Analisis dan Kesimpulan
Dari hasil Jmeter yang didapatkan:
   
Pada test akk-student, latency yang menandakan waktu ditempuhnya request dieksekusi dalam code sebelum profiling mencapai 
80000an ms latency. Setelah dilakukan profiling (optimisasi method getAllStudentWithCourses) dapat dilihat bahwa latency nya menurun hingga
sekitar 3000-an ms latency. Hal ini menjunjukan bahwa terdapat peningkatan performa lebih dari 50% atau lebih.
Pada test highest-gpa, latency yang dikeluarkan sebelum profiling sekitar 400-an ms latency.
Setelah dilakukan profiling (optimisasi method getStudentWithHighestGPA) dapat dilihat bahwa latency nya menurun hingga 13 an ms latency.

Hal ini menunjukkan bahwa dengan dilakukan profiling, waktu eksekusi code dapat lebih cepat daripada sebelum optimasi.
Ini berarti kita juga telah berhasil melakukan profiling.

## Refleksi
1. Pendekatan pengujian menggunakan JMeter tidak menyangkut cara program/aplikasi beroperasi, sehingga kadang disebut seperti blackbox. 
   JMeter hanya perlu mengirim permintaan ke endpoint yang ditentukan dan menyesuaikan jumlah permintaan sesuai dengan permintaan penguji. Dilain hal, dengan profiling, kita bisa mengetahui bagian program mana saja yang lebih lama berjalan dibandingkan dengan program lain
   sehingga kita bisa melakukan optimasi pada bagian-bagian kode kita yang tercap "besar".

2. Profiling membantu kita dalam mengetahui bagian program mana yang menghambat kinerja aplikasi secara keseluruhan (memory, cpu, time, etc). 
   Dengan demikian, kita hanya perlu mengoptimasi bagian yang tercap tersebut sehingga aplikasi secara keseluruhan akan meningkat kinerjanya dengan lebih baik tanpa perlu memperbaiki terlalu banyak bagian dari keseluruhan code nya.

3. Menurut saya iya, profiler Intelij efektif dalam membantu saya untuk menganalisa method atau kode mana
   yang mengalami kehambatan yang tidak diperlukan. Lebih dalamnya, dengan profiler Intellij, saya dapat 
   mengetahui bagian program yang memakan waktu paling lama, seperti method getAllStudentWithCourses etc. 
   Bahkan, dengan informasi durasi waktu yang diperlukan untuk mengoperasikan pemanggilan-pemanggilan fungsinya, saya dapat mendeteksi baris mana pada method tersebut yang menghambat kinerja methodnya.

4. Menurut saya, membaca output dari alat pengujian performansi dan profiler merupakan tantangan besar. Diperlukan pemahaman yang mendalam untuk mengidentifikasi bagian program yang menjadi bottleneck. 
   Tentu solusinya adalah bisa dengan membiasakan diri dengan teknologi baru ini untuk lebih mudah mendapatkan informasi penting dari hasil outputnya.

5. Dengan bantuan profiler Intellij, kita dapat mengidentifikasi bagian program yang menjadi biang permasalahan, 
durasi eksekusi suatu metode, dan frekuensi pemanggilan metode. Ini memungkinkan kita untuk mengoptimalkan bagian program yang membutuhkan perhatian tanpa mengabaikan prinsip bahwa melakukan optimasi terlalu dini dapat mengurangi keterbacaan kode.

6. diketahui bahwa untuk menangani situasi di mana hasil dari profilisasi menggunakan IntelliJ Profiler tidak konsisten dengan temuan dari pengujian kinerja menggunakan JMeter, Kita dapat menggunakan teknik seperti menggunakan Docker daripada .jmx dan memperhatikan think time. 
Dengan cara ini, kita dapat meningkatkan konsistensi hasil pengujian JMeter dan mengurangi variasi antara mesin pengujian. Selain itu, juga penting untuk membandingkan hasil dari kedua alat tersebut (Jmeter & Intelij Profiler) untuk memperoleh pemahaman yang lebih baik tentang performa aplikasi dan penyebab perbedaan hasil.

7. Apa yang saya lakukan sebelumnya adalah seperti setelah melakukan testing dan profiling, saya memperbaiki kode dengan memeriksa durasi program menggunakan JMeter. 
Jika terlalu lama, saya mengidentifikasi bagian kode yang menjadi masalah (ketidak-optimalan) dan mengoptimalkannya. 
Saya memastikan kebenaran perubahan dengan membandingkan outputnya dengan sebelumnya. Untuk lebih jauhnya, bisa juga kita lakukan dengan unit-testing untuk memastikan kebenaran code nya.


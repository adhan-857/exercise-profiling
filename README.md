# Tutorial & Exercise Modul 5:  Java Profiling
### Ramadhan Andika Putra (2206081976) - AdPro A <br>

***[ Reflection ]***<br>
1. *Performance testing* menggunakan JMeter lebih fokus kepada mengukur performa suatu aplikasi secara umum dalam lingkup yang lebih luas. *Performance testing* berguna untuk mengukur kinerja suatu aplikasi secara keseluruhan yang mensimulasikan keadaan yang dapat terjadi di dunia nyata.<br>

    Sedangkan *profiling* lebih fokus dalam mengukur kinerja aplikasi dengan lebih spesifik pada *code-level performance*. *Profiling* bersifat lebih detail sehingga dapat mengidentifikasi bagian kode mana yang belum efisien.
<br>

2. *Profiling* memberikan informasi mengenai kinerja dan performa tiap bagian dari kode aplikasi, sehingga dapat membantu saya dalam mengidetifikasi bagian kode mana yang perlu saya *improve* atau perbaiki. Profiling sendiri memberikan informasi yang detail untuk tiap *method* pada kode, seperti *CPU time*, *Total time*, dan *Memory Allocation*. Informasi-informasi tersebut dapat membantu kita dalam mengidentifikasi bagian kode mana yang perlu dilakukan *refactoring*.
<br>

3. Menurut saya, Intellij Profiler sudah efektif dalam membantu proses *profiling*. Hal ini dikarenakan proses profiling yang mudah. Selain itu, Itellij Profiler juga menyediakan grafik atau menampilkan data dengan cara yang cukup ringkas seperti menggunakan *flame graph*. Intellij profiler juga memudahkan saya untuk membandingkan dua hasil *profiling* sehingga saya dapat dengan mudah membandingkan hasil *profiling* sebelum dan sesudah *refactoring*.
<br>

4. Tantangan terbesar dalam melakukan *performance testing* dan *profiling* menurut saya adalah cukup sulit membaca grafik dan tabel pada JMeter ataupun Intellij Profiler jika pertama kali mencobanya. Namun, saya berusaha mencari informasi mengenai cara membaca grafik dan tabel tersebut sehingga saya bisa melanjutkan mengerjakan tutorial dan *exercise* pada modul ini.
<br>

5. Manfaat utama dalam menggunakan Intellij profiler yang saya rasakan adalah mengenai aspek kemudahan dan efektifitas. Intellij Profiler ini memungkinkan saya melakukan profiling secara langsung di dalam IDE tanpa perlu menginstal aplikasi atau program tambahan. IntelliJ Profiler juga menyajikan data dalam bentuk grafik atau tabel yang intuitif, memudahkan saya dalam membaca dan menginterpretasikan informasi yang diberikan. Selain itu, antarmuka pengguna yang ramah membuat IntelliJ Profiler cukup mudah untuk digunakan bagi *first timer* seperti saya.
<br>

6. Dalam pengerjaan modul kali ini, saya sendiri tidak mengalami adanya ketidak konsestinan antara JMeter dan Intellij Profiler saat melakukan *performance testing* dan *profiling*. Mungkin jika hal tersebut terjadi pada saya, yang saya akan lakukan adalah memeriksa konfigurasi dan *testing conditions* dari kedua tools tersebut serta mencoba menjalankan *test*-nya kembali untuk beberapa iterasi.
<br>

7. Strategi utama saya adalah melakukan *refactoring* pada *method* yang memiliki CPU *time* yang tinggi dari hasil analisis setelah melakukan *profiling*.<br>

    Pada endpoint `all-student`, saya menemukan bahwa method yang perlu untuk dilakuakan *refactoring* adalah method `getAllStudentWithCourse`. Untuk melakukan optimasi pada method tersebut, saya mengurangi jumlah panggilan untuk mencari student course dengan Id dan menggunakan method `studentCourseRepository.findAll()` sebagai gantinya. \ Pada endpoint  `all-student-name`, saya menemukan bahwa method `joinStudentNames` perlu dilakukan refactoring. Untuk melakukan optimasi pada method tersebut, saya mengganti proses pembuatan string menggunakan StringBuilder yang lebih efisien. Pada endpoint `highest-gpa`, saya melakukan refacotring pada method `findStudentWithHighestGPA`. Untuk mengoptimalkannya, saya menggunakan query `SELECT * FROM students ORDER BY gpa DESC LIMIT 1` untuk mengambil mahasiswa dengan IPK tertinggi. Hal ini saya terapkan pada bagian `StudentRepository`.<br>

    Untuk memastikan bahwa saya tidak sengaja merubah fungsi dari kode aplikasi, saya melakukan perbandingan secara menyeluruh pada setiap output dari request yang dikirim. Perbandingan saya lakukan dengan memastikan *string* yang dikembalikan pada saat sebelum akan sama persis dengan sesudah *refactoring*.

<br>

***[ JMeter Performance Testing Result ]***<br>
`all-student-name` <br>
*Before Optimization*<br>
![test_plan_2 (detail)](https://github.com/adhan-857/exercise-profiling/assets/119088782/82ca12ac-8be0-42eb-b27f-1cc76548fb52)<br>
![test_plan_2_before](https://github.com/adhan-857/exercise-profiling/assets/119088782/8a986ab7-dede-40c7-9590-4c42539f08c7)<br>
![test_result_2_before](https://github.com/adhan-857/exercise-profiling/assets/119088782/993723a8-5bec-4aa7-8f89-89dc4eb13ed1)<br>
<br>

*After Optimization*<br>
![test_plan_2_optimized (detail)](https://github.com/adhan-857/exercise-profiling/assets/119088782/c449e5ea-5296-45ba-b6a6-fd3a9c2276ba)<br>
![test_plan_2_after](https://github.com/adhan-857/exercise-profiling/assets/119088782/5edfe08a-0a04-4f43-b0fa-4da182821494)<br>
![test_result_2_after](https://github.com/adhan-857/exercise-profiling/assets/119088782/48482f94-e01e-40dc-ac95-5b5649aba17d)<br>
<br>
<br>

`highest-gpa` <br>
*Before Optimization*<br>
![test_plan_3 (detail)](https://github.com/adhan-857/exercise-profiling/assets/119088782/b9515859-10e6-4e50-a2e5-56f05fb5ec95)<br>
![test_plan_3_before](https://github.com/adhan-857/exercise-profiling/assets/119088782/38598c4d-5076-418a-9adc-ed6d55ec076d)<br>
![test_result_3_before](https://github.com/adhan-857/exercise-profiling/assets/119088782/560d2356-a144-4fe1-a1cf-f87baeee819f)<br>
<br>

*After Optimization*<br>
![test_plan_3_optimized (detail)](https://github.com/adhan-857/exercise-profiling/assets/119088782/37ef4db8-dec0-417a-a562-141b5d3a9529)<br>
![test_plan_3_after](https://github.com/adhan-857/exercise-profiling/assets/119088782/070df5c9-75ea-46cd-9d37-3da64d9c7991)<br>
![test_result_3_after](https://github.com/adhan-857/exercise-profiling/assets/119088782/607144ca-6bfb-4839-91c0-240932f9e057)
<br>
<br>

**Kesimpulan**<br>
Berdasarkan gambar data yang didapatkan di atas, dapat dilihat jika performa kode setelah optimasi lebih cepat dan baik jika dibandingkan dengan performa kode sebelum optimasi. Kesimpulan tersebut berdasarkan data yang diberikan oleh hasil pengujian baik melalui GUI dan CLI menunjukkan bahwa waktu eksekusi dari kode sesudah optimaasi lebih cepat dibandingkan yang belum dioptimasi

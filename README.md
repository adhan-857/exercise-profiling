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

<br>

***[ JMeter Performance Testing Result ]***<br>
`all-student-name` <br>
*Before Optimization*<br>
![test_plan_2 (detail)](https://github.com/adhan-857/exercise-profiling/assets/119088782/82ca12ac-8be0-42eb-b27f-1cc76548fb52)<br>
![test_plan_2_before](https://github.com/adhan-857/exercise-profiling/assets/119088782/8a986ab7-dede-40c7-9590-4c42539f08c7)<br>
![test_result_2_before](https://github.com/adhan-857/exercise-profiling/assets/119088782/993723a8-5bec-4aa7-8f89-89dc4eb13ed1)<br>
<br>

*After Optimization*<br>
![test_plan_2_optimized (detail)](https://github.com/adhan-857/exercise-profiling/assets/119088782/c449e5ea-5296-45ba-b6a6-fd3a9c2276ba)
![test_plan_2_after](https://github.com/adhan-857/exercise-profiling/assets/119088782/5edfe08a-0a04-4f43-b0fa-4da182821494)
![test_result_2_after](https://github.com/adhan-857/exercise-profiling/assets/119088782/48482f94-e01e-40dc-ac95-5b5649aba17d)
<br>
<br>
<br>
<br>

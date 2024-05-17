# Reflection
##### Nama: Febrian Irvansyah
##### NPM: 2206083584
##### Kelas: C

## Hello Minikube
#### 1. Compare the application logs before and after you exposed it as a Service. Try to open the app several times while the proxy into the Service is running. What do you see in the logs? Does the number of logs increase each time you open the app?
Sebelum diexpose sebagai service logs hanya berisi initialisasi http server pada port 8080 dan udp server pada port 8081. Setelah diexpose sebagai service dan dibuka beberapa kali, terlihat bahwa pada setiap kali service dibuka bertambah 2 log http request GET.

#### 2. Notice that there are two versions of `kubectl get` invocation during this tutorial section. The first does not have any option, while the latter has `-n` option with value set to `kube-system`. What is the purpose of the `-n` option and why did the output not list the pods/services that you explicitly created?
Opsi `-n` pada `kubectl get` berfungsi untuk memilih spesifikasi namespace untuk ditampilkan pada list. Namespaces pada kubernetes berfungsi untuk mengisolasi sekelompok resources pada satu cluster. Saat `-n` option di set dengan `kube-system` maka tidak mengeluarkan list pods/services yang sudah secara eksplisit dibuat karena namespace `kube-system` hanya untuk resources yang dibuat oleh kubernetes system itu sendiri dan bukan oleh user.


## Rolling Update Deployment
Pada tutorial ini saya mengalami kendala dengan kubectl dengan message "couldn’t get current server API group list" dan belum mendapatkan solusi.
Jadi saya coba untuk menjawab pertanyaannya yang mungkin dapat saya jawab.

#### 1. What is the difference between Rolling Update and Recreate deployment strategy?
Rolling update mendeploy tanpa downtime karena dijalankan sekaligus menggantikan aplikasi yang lama.sedangkan recreate dmendeploy dengan menghapus instance lama lalu membuat yang baru.

#### 4. What do you think are the benefits of using Kubernetes manifest files? Recall your experience in deploying the app manually and compare it to your experience when deploying the same app by applying the manifest files (i.e., invoking `kubectl apply -f` command) to the cluster.
Adanya declarative config sehingga terdapat konsistensi dan dapat diatur dengan version control, scalabaility yang baik karena dapat mendefine resource, reusable karena dapat berbentuk template, dapat serve sebagai documentation.

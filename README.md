# Kubernetes-wordpress-mysql
Deploy Wordpress dan Mysql di kubernetes

## Langkah-langkah implementasi
* Pull/ download repository ini
* Masuk ke direktori dengan terminal
* Edit file password.txt untuk menyesuaikan password yang diinginkan
* Jalankan command-command berikut pada terminal:
```
# Menjalankan minikube
$ minikube start

# Membuat local volumes untuk MySQL
$ kubectl create -f local-volumes.yaml

# Membuat password sql untuk WordPress
$ kubectl create secret generic mysql-pass --from-file=password.txt

# Mendeploy MySQL 
$ kubectl create -f ./mysql-deployment.yaml

# Mendeploy WordPress 
$ kubectl create -f ./wordpress-deployment.yaml

```

* Selanjutnya jalankan command berikut untuk melihat url service wordpress sehingga kita dapat mengaksesnya lewat browser:
```
minikube service wordpress --url
```

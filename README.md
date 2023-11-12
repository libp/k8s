# k8s

## config proxy

```
apt install git -y
git config --global https.proxy http://16.171.230.104:38888
git config --global http.proxy http://16.171.230.104:38888
git config --global user.name "libp"
git config --global user.email "924701358@qq.com"
```


## clone repository
```
git clone https://github.com/yanruogu/ckad-exams.git
git clone https://github.com/libp/k8s.git
```

## kubectl exec
```
kubectl exec busybox -it -- /bin/sh
kubectl exec mypod -it -- ls -ltr /usr
kubectl exec mypod -c ruby-container -- date
```

## install metallb for Loadbalancer

```
#https://metallb.universe.tf/installation/
curl -x http://16.171.230.104:38888/ https://raw.githubusercontent.com/metallb/metallb/v0.13.12/config/manifests/metallb-native.yaml -o metallb-native.yaml

kubectl apply -f  metallb-native.yaml
kubectl get pods -n metallb-system

NAME                          READY   STATUS    RESTARTS   AGE
controller-786f9df989-chzxz   1/1     Running   0          2m42s
speaker-fhmwd                 1/1     Running   0          2m42s
speaker-q9h7z                 1/1     Running   0          2m42s
speaker-x99lk                 1/1     Running   0          2m42s
```

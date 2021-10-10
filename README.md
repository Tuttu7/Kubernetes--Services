#### To get how many Services exist on the system ?
```
root@controlplane:~# kubectl get services
NAME         TYPE        CLUSTER-IP   EXTERNAL-IP   PORT(S)   AGE
kubernetes   ClusterIP   10.96.0.1    <none>        443/TCP   7m6s
```

#### Identifying the target port configured on the kubernetis service 
```
root@controlplane:~# kubectl describe service
Name:              kubernetes
Namespace:         default
Labels:            component=apiserver
                   provider=kubernetes
Annotations:       <none>
Selector:          <none>
Type:              ClusterIP
IP Families:       <none>
IP:                10.96.0.1
IPs:               10.96.0.1
Port:              https  443/TCP
TargetPort:        6443/TCP
Endpoints:         10.7.189.9:6443
Session Affinity:  None
Events:            <none>

root@controlplane:~# kubectl describe service | grep -i targetport
TargetPort:        6443/TCP
```

#### Services connect group of pods
```
ClusterIP - Services create an virtual IP inside cluster to enable communication between as set of servers

Node port - Service make an internal port accesible on nodePort.
```


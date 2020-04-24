## [cAdvisor](./cAdvisor/)
* * *

참고 : [cAdvisor Github](https://github.com/google/cadvisor/tree/master/deploy/kubernetes)

쿠버네티스 클러스터 내부의 컨테이너들에 대한 매트릭 정보를 *(CPU 사용량, 메모리 사용량, 스토리지 사용량 등)*  ```/metrics``` 라는 HTTP 엔드포인트를 제공하여 외부에서(```Prometheus```) 수집할 수 있도록 기능을 제공하는 서비스이다.

[cAdvisor가 제공하는 매트릭 정보에 대한 리스트](https://github.com/google/cadvisor/blob/master/docs/storage/prometheus.md)


아래와 같이 적용한다.

```
$ kubectl apply -f ./cAdvisor/
``` 

<br> <br> <br> 


## [kube-state-metrics](./kube-state-metrics/)
* * *

참고 : [kube-state-metrics Github](https://github.com/kubernetes/kube-state-metrics)

이 서비스는 Kubernetes API와 통신하는 Pod를 만들어 쿠버네티스 클러스터에 대한 다양한 매트릭 정보를 수집하고 이를 ```/metrics```라는 HTTP 엔드포인트를 통해 외부에서(```Prometheus```)수집할 수 있도록 기능을 제공하는 서비스이다.

자세한 셋업 내용은 [여기를 참고](https://www.notion.so/bscnote/kube-state-metrics-b48da141bf7543359bed4ce64f8a0a23)

[kube-state-metrics가 제공하는 매트릭 정보에 대한 리스트](https://github.com/kubernetes/kube-state-metrics/tree/master/docs)


아래와 같이 적용한다.

```
$ kubectl apply -f ./kube-state-metrics/
```

<br> <br> <br> 


## [node-exporter](./node-exporter/)
* * *

참고 : 
- [node-exporter Github](https://github.com/prometheus/node_exporter)
- [coreos/kube-prometheus/node-exporter GitHub](https://github.com/coreos/kube-prometheus/blob/master/manifests/)

이 서비스는 하드웨어 및 OS의 매트릭 정보를 수집하는 Pod를 만들어 ```/metrics```라는 HTTP 엔드포인트를 통해 외부에서(```Prometheus```)수집할 수 있도록 기능을 제공하는 서비스이다.


아래와 같이 적용한다.

```
$ kubectl apply -f ./node-exporter/
```
# Task 2 - Affinity

### Affinity 설정으로 Pod 할당 제어
#

1. node에 Label 셋팅
```
kubectl label nodes k8s-worker1 color=blue
kubectl label nodes k8s-worker2 color=red
```
label 확인
```
kubectl get nodes --show-labels
```

2. hard Affinity 설정을 사용하는 Deployment yaml 확인 
```
cat Affinity-dp-hard.yaml
```

3. 생성
```
kubectl create -f Affinity-dp-hard.yaml
```

4. Pod의 배치 확인
```
kubectl get pod -o wide
```

5. soft Affinity 설정을 사용하는 Deployment yaml 확인 
```
cat Affinity-dp-soft.yaml
```

6. 생성
```
kubectl create -f Affinity-dp-soft.yaml
```

7. Pod의 배치 확인
```
kubectl get pod -o wide
```

8. Inter Pod Affinity 를 구현하기 위한 Pod 확인 및 배포
```
cat pod-affinity-pod.yaml
kubectl create -f pod-affinity-pod.yaml
```

9. Inter Pod Affinity 설정을 사용하는 Deployment yaml 확인 
```
cat Affinity-dp-pod.yaml
```

10. 생성
```
kubectl create -f Affinity-dp-pod.yaml
```

11. Pod 배치 확인
```
kubectl get pod -o wide
```

12. 리소스 삭제 
```
kubectl delete pod,deploy --all
```
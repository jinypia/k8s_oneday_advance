# Task 2 - LimitRange

### 개별 Pod 리소스 제한
#

1. yaml 확인
```
cat lr-ns.yaml lr.yaml
```

2. 리소스 생성
```
kubectl create -f lr-ns.yaml
kubectl create -f lr.yaml
```

3. 생성 확인
```
kubectl get ns
kubectl get limitrange -n lr-ns
```

4. 상세 정보 조회
```
kubectl describe limitrange -n lr-ns
```

5. pod 생성 yaml 확인
```
cat lr-pod.yaml
```

6. 리소스 생성
```
kubectl create -f lr-pod.yaml
```
`lr 제한에 위배되어 생성되지 않음을 확인`

7. 두번째 Pod yaml 확인 
```
cat lr-pod2.yaml
```

8. pod 생성
```
kubectl create -f lr-pod2.yaml
```

9. LimitRange 확인
```
kubectl describe limitrange -n lr-ns
```

10. ns 삭제
```
kubectl delete ns lr-ns
```

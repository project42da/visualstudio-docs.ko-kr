## <a name="create-a-kubernetes-development-environment-in-azure"></a>Azure에서 Kubernetes 개발 환경 만들기
연결된 환경을 사용하여 Azure에서 완벽히 관리되고 개발에 최적화된 Kubernetes 기반 환경을 만들 수 있습니다. 해당 명령은 `eastus`에서 `mydevenvironment`이라는 환경을 만듭니다.
```cmd
vsce env create --name mydevenvironment --location eastus
```

지원되는 위치: `eastus`, `westeurope`

> [!Note]
> 이 명령은 약 6분이 걸립니다. 대기하지 않고 이 가이드를 계속할 수 있습니다.

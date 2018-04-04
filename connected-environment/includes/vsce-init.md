## <a name="initialize-code-for-docker-and-kubernetes-development"></a>Docker 및 Kubernetes 개발을 위한 코드 초기화
로컬로 실행할 수 있는 기본 웹앱이 있습니다. 앱의 컨테이너 및 컨테이너가 Kubernetes에 배포되는 방법을 정의하는 자산을 만들어 이제 웹앱을 컨테이너화하게 됩니다. 이렇게 하면 연결된 환경과 작업하기가 수월합니다. 

1. VS Code를 시작하고 `webfrontend` 폴더를 엽니다. (디버그 자산을 추가하거나 프로젝트를 복원하는 모든 기본 프롬프트를 무시할 수 있습니다.)
1. VS Code(**보기 | 통합 터미널** 메뉴를 사용하여)에서 통합 터미널을 엽니다.
1. 이 명령을 실행합니다(**webfrontend**가 현재 폴더인지 확인).

```cmd
vsce init --public
```

연결된 환경 CLI의 ```init``` 명령은 기본 설정으로 Docker 및 Kubernetes 자산을 생성합니다.
* `./Dockerfile`은 앱의 컨테이너 이미지 및 소스 코드가 빌드되는 방법을 설명하고 컨테이너 내에서 실행됩니다.
* `./charts/webfrontend` 아래 [Helm 차트](https://docs.helm.sh)는 Kubernetes에 컨테이너를 배포하는 방법을 설명합니다.

지금은 이러한 파일의 전체 콘텐츠를 이해할 필요가 없습니다. 그러나 **코드 자산으로 동일한 Kubernetes 및 Docker 구성은 개발에서 생산까지 내내 사용될 수 있으므로 다른 환경에서 더 나은 일관성을 제공한다는 것**을 지적할 가치가 있습니다.
 
`./vsce.yaml`이라는 파일은 또한 `init` 명령으로 생성되며 해당 파일은 연결된 환경에 대한 구성 파일입니다. 이 파일은 Azure에서 반복 개발 환경을 사용할 수 있는 추가 구성을 통해 Docker 및 Kubernetes 아티팩트를 보완합니다. 예를 들어 기본 Helm 차트는 모든 공용 끝점을 노출하지 않습니다. 그러나 때때로 개발 동안 공용 끝점을 일지적으로 여는 것이 유용하므로 즉 모바일 장치 또는 웹후크 URL에서 코드를 테스트할 수 있습니다. `init --public`을 사용하여 만든 vsce.yaml 파일은 Helm 기본 매개 변수를 재정의하여 개발 시간 동안만 공용 끝점을 노출합니다.

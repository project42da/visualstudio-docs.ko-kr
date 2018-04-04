## <a name="build-and-run-code-in-kubernetes"></a>Kubernetes에서 코드 실행 및 빌드
코드를 실행해 봅시다! 터미널 창의 **루트 코드 폴더**에서 이 명령, webfrontend을 실행 합니다.

```cmd
vsce up
```

명령의 출력에 주시하면 출력이 진행되면서 몇 가지를 확인하게 됩니다.
1. 소스 코드는 Azure에서 개발 환경에 동기화됩니다.
1. 코드 폴더에서 Docker 자산이 지정한 대로 Azure에서 컨테이너 이미지가 빌드됩니다.
1. Kubernetes 개체는 코드 폴더의 Helm 차트에서 지정한 대로 컨테이너 이미지를 사용하도록 만들어집니다.
1. 컨테이너의 끝점에 대한 정보가 표시됩니다. 우리의 경우 공용 HTTPS URL을 예상하고 있습니다.
1. 위의 단계가 성공적으로 완료된 것으로 가정하면 컨테이너가 시작할 때 `stdout`(및 `stderr`)의 출력을 확인하기 시작합니다.

> [!Note]
> `up` 명령이 처음 실행될 때 이러한 단계는 더 오래 걸리지만 후속 실행은 더 빨리 진행돼야 합니다.

## <a name="test-the-web-app"></a>웹앱 테스트
`up` 명령으로 만들어진 공용 URL 정보에 대한 콘솔 출력을 검사합니다. 다음 양식으로 되어 있습니다. 

`Running at public URL: https://<servicename>-<environmentname>.vsce.io` 

브라우저 창에서 이 URL을 열고 웹앱 로드를 확인해야 합니다. 컨테이너가 실행될 때 `stdout` 및 `stderr` 출력은 터미널 창에 스트림됩니다.

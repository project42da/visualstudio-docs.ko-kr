## <a name="install-the-connected-environment-cli"></a>연결된 환경 CLI 설치
연결된 환경에는 최소한 로컬 컴퓨터 설치가 필요합니다. 대부분의 개발 환경의 구성은 클라우드에 저장되며 다른 사용자와 공유할 수 있습니다.

### <a name="install-on-mac"></a>Mac에 설치
연결된 환경 CLI를 다운로드하고 설치합니다.
```cmd
curl -L https://aka.ms/get-vsce-mac | bash
```

### <a name="install-on-windows"></a>Windows에 설치
1. [Git for Windows](https://git-scm.com/downloads)를 설치하고 기본 설치 옵션을 선택합니다. 
1. [이 링크](https://storage.googleapis.com/kubernetes-release/release/v1.9.0/bin/windows/amd64/kubectl.exe)에서 **kubectl.exe**를 다운로드하고 경로의 위치에 **저장**합니다.
1. [연결된 환경 CLI 설치관리자](https://aka.ms/get-vsce-windows)를 다운로드하고 실행합니다. 

### <a name="install-on-linux"></a>Linux에 설치
출시 예정...

## <a name="get-kubernetes-debugging-for-vs-code"></a>VS Code에 대한 Kubernetes 디버깅 가져오기
연결된 환경 CLI를 독립 실행형 도구로 사용할 수 있지만 VS Code를 사용하는 .NET Core 및 Node.js 개발자는 Kubernetes 디버깅 같은 다양한 기능을 사용할 수 있습니다.

1. 없을 경우 [VS Code](https://code.visualstudio.com/Download)를 설치합니다.
1. [VS 연결된 환경 확장](https://aka.ms/get-vsce-code)을 다운로드합니다.
1. 확장을 설치합니다. 

```cmd
code --install-extension path-to-downloaded-extension/vsce-0.1.0.vsix
```

## <a name="initialize-debug-assets-with-the-vs-code-extension"></a>VS Code 확장을 사용하여 디버그 자산 초기화
VS Code가 Azure에서 개발 환경과 통신할 수 있도록 먼저 코드 프로젝트를 구성해야 합니다. 연결된 환경에 대한 VS Code 확장은 디버그 구성을 설정하기 위한 도우미 명령을 제공합니다. 

**명령 팔레트**(**보기 | 명령 팔레트** 메뉴 사용하여)를 열고 이 명령 `Connected Environment: Create configuration files for connected development`를 선택하고 입력하려면 자동 완성 기능을 사용합니다. 

이렇게 하면 `.vscode` 폴더에서 연결된 환경에 대한 디버그 구성이 추가됩니다.

![](../media/vsce-command-palette.png)

> [!Note]
> **중요**: 버그로 인해 진행 전에 VS Code를 닫았다가 다시 시작하십시오.
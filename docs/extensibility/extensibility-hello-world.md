---
title: Hello World | Microsoft Docs
ms.custom: 
ms.date: 07/10/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f74e1ad1-1ee5-4360-9bd5-d82467b884ca
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 18a0e18589574c689ebbddbaf28448cf5539ad96
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="creating-your-first-extension-hello-world"></a>첫 번째 확장 프로그램을 만들기: Hello World

Hello World 예제에서는 Visual Studio에 대 한 첫 번째 확장 프로그램을 만드는 과정을 안내 합니다. 이 자습서에서는 Visual Studio에 새 명령을 추가 하는 방법을 보여줍니다.

프로세스에 설명 합니다 하는 방법:

* **[확장성 프로젝트 만들기](#create-an-extensibility-project)**
* **[사용자 지정 명령 추가](#add-a-custom-command)**
* **[소스 코드를 수정 합니다.](#modify-the-source-code)**
* **[실행](#run-it)**

이 예제에서는 여 사용 Visual C# 사용자 지정 메뉴 단추 "말 Hello World!" 라는 추가 하려면 다음과 같습니다.

![hello world 명령](media/hello-world-say-hello-world.png)

## <a name="prerequisites"></a>필수 구성 요소

시작 하기 전에 설치 했는지 확인는 **Visual Studio 확장 개발** VSIX 템플릿이 필요 하 고 예제 코드를 포함 하는 작업입니다.

참고: 모든 버전 (Community, Professional 또는 Enterprise) Visual Studio 확장성 프로젝트를 만들려면 Visual Studio의 사용할 수 있습니다.

## <a name="create-an-extensibility-project"></a>확장성 프로젝트 만들기

1단계: **파일** 메뉴를 클릭 하 여 **새 프로젝트**합니다. 화면 아래쪽에서 프로젝트의 이름을 입력할 수 있습니다.

2단계. **템플릿** 메뉴를 클릭 **Visual C#**, 클릭 **확장성**, 클릭 하 고 **VSIX 프로젝트**합니다.

![새 프로젝트](media/hello-world-new-project.png)

이제 시작 페이지 및 일부 샘플 리소스 나타납니다.

이 자습서를 유지 하 고에 다시 검토 해야 할 경우에 새 HelloWorld 프로젝트를 찾을 수 있습니다는 **시작 페이지** 에 **최근** 섹션.

## <a name="add-a-custom-command"></a>사용자 지정 명령 추가

1단계: 매니페스트를 선택 하면 인스턴스, 메타 데이터, 설명 및 버전에 대 한 변경할 수 있는 옵션과 각 옵션을 볼 수 있습니다.

2단계. 프로젝트 (솔루션 아님)를 마우스 오른쪽 단추로 클릭 합니다. 상황에 맞는 메뉴에서 클릭 **추가**, 클릭 하 고 **사용자 정의 컨트롤**합니다.

3단계. 로 돌아가기는 **확장성** 섹션을 선택한 다음 클릭 **사용자 지정 명령**합니다.

4단계. 에 **이름** 맨 아래에 필드, 예를 들어 Command.cs 이름을 지정 합니다.

![사용자 지정 명령](media/hello-world-custom-command.png)

새 명령에 표시 됩니다는 **솔루션 탐색기** 아래는 **리소스** 분기 합니다. 또한 이것이 PNG, ICO 파일 이미지를 수정 하려는 경우 등 명령에 관련 된 다른 파일을 찾을 수 있습니다.

## <a name="modify-the-source-code"></a>소스 코드를 수정 합니다.

이 시점에서 추가 하는 단추는 상당히 제네릭입니다. 변경 하려는 경우 VSCT 파일 및 CS 파일을 수정 해야 합니다.

* VSCT 파일은 여기서 있습니다 수 명령, 이름 바꾸기 물론 어디로 Visual Studio 명령 시스템에서을 정의 합니다. VSCT 파일을 탐색할 때 많은 코드 컨트롤의 각 섹션을 설명 하는 주석 처리 된 코드를 확인할 수 있습니다.

* CS 파일이 클릭 처리기 등의 작업을 정의할 수 있습니다.

1단계: **솔루션 탐색기**, 새 명령에 대 한 VSCT 파일을 찾습니다. 이 경우 CommandPackage.vsct 호출 됩니다.

![패키지 vsct 명령](media/hello-world-command-package-vsct.png)

2단계. 변경 된 `ButtonText` 를 "Hello World!" 매개 변수

```xml
  ...
  <Button guid="guidCommandPackageCmdSet" id="CommandId" priority="0x0100" type="Button">
     <Parent guid="guidCommandPackageCmdSet" id="MyMenuGroup" />
     <Icon guid="guidImages" id="bmpPic1" />
     <Strings>
        <ButtonText>Say Hello World!</ButtonText>
     </Strings>
  </Button>
  ...
```

3단계. 로 돌아가서 **솔루션 탐색기** Command.cs 파일을 찾습니다. 문자열을 변경 `message` 명령의 `string.Format(..)` "Hello World!"에

```csharp
  ...
  private void MenuItemCallback(object sender, EventArgs e)
  {
    string message = "Hello World!";
    string title = "Command1";

    // Show a message box to prove we were here
    VsShellUtilities.ShowMessageBox(
        this.ServiceProvider,
        message,
        title,
        OLEMSGICON.OLEMSGICON_INFO,
        OLEMSGBUTTON.OLEMSGBUTTON_OK,
        OLEMSGDEFBUTTON.OLEMSGDEFBUTTON_FIRST);
  }
  ...
```

각 파일에 변경 내용을 저장 해야 합니다.

## <a name="run-it"></a>실행

이제 Visual Studio 실험적 인스턴스에서 소스 코드를 실행할 수 있습니다.

1단계: 클릭 **시작** 도구 모음에서 합니다. 이 프로젝트를 빌드하고 라는 Visual Studio의 새 인스턴스를 시작 하 고 디버거를 시작 합니다는 **실험적 인스턴스**합니다.

단어 "실험적 인스턴스" Visual Studio 제목 표시줄에 표시 됩니다.

![실험적 인스턴스 제목 표시줄](media/hello-world-exp-instance.png)

2단계. 에 **도구** 의 메뉴는 **실험적 인스턴스**, 클릭 **Say Hello World!**합니다.

![최종 결과](media/hello-world-final-result.png)

이 경우 대화 상자 가운데에 "Hello World!"을 사용 하면 화면에 새 사용자 지정 명령에서 출력이 표시 됩니다. 반환됩니다.

## <a name="next-steps"></a>다음 단계

Visual Studio 확장성 작업의 기본 사항을 배웠으므로 같습니다 여기서 자세히 알아볼 수 있습니다.

* [Visual Studio 확장명 개발 하기 시작](starting-to-develop-visual-studio-extensions.md) -샘플, 자습서입니다. 및 확장 프로그램을 게시 합니다.
* [Visual Studio 2017 SDK의 새로운](what-s-new-in-the-visual-studio-2017-sdk.md) -Visual Studio 2017의 새로운 확장성 기능
* [Visual Studio SDK 내](internals/inside-the-visual-studio-sdk.md) -Visual Studio 확장성의 세부 정보
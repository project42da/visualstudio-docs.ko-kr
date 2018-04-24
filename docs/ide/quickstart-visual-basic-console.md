---
title: '빠른 시작: Visual Studio에서 Visual Basic을 사용하여 첫 번째 콘솔 앱 만들기 | Microsoft Docs'
ms.custom: ''
ms.date: 12/10/2017
ms.technology:
- vs-acquisition
ms.topic: quickstart
ms.devlang: vb
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- vb
ms.workload:
- multiple
ms.openlocfilehash: 39e7b9f03a5ef0a37594dad015084648eaa2bade
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="quickstart-create-your-first-console-app-in-visual-studio-with-visual-basic"></a>빠른 시작: Visual Studio에서 Visual Basic을 사용하여 첫 번째 콘솔 앱 만들기
Visual Studio IDE(통합 개발 환경)에 대한 소개는 이 5~10분 분량으로 여기서 콘솔에서 실행되는 간단한 Visual Basic 응용 프로그램을 만듭니다.

아직 Visual Studio를 설치하지 않은 경우 [Visual Studio 다운로드](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) 페이지로 이동하여 체험용으로 설치합니다.

## <a name="create-a-project"></a>프로젝트 만들기
먼저 Visual Basic 응용 프로그램 프로젝트를 만들어야 합니다. 아무 것도 추가하지 않아도 필요한 모든 템플릿 파일과 함께 프로젝트 형식이 제공됩니다.

1. Visual Studio 2017을 엽니다.

2. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트...** 를 차례로 선택합니다.

3. **새 프로젝트** 대화 상자의 왼쪽 창에서 **Visual Basic**을 확장한 후 **.NET Core**를 선택합니다. 가운데 창에서 **콘솔 앱(.NET Core)** 을 선택합니다. 프로젝트의 이름을 *HelloWorld*로 지정합니다.

   ![Visual Studio IDE의 새 프로젝트 대화 상자의 콘솔 앱(.NET Core) 프로젝트 템플릿](../ide/media/new-project-vb-dotnetcore-helloworld-console-app.png)

     **콘솔 앱(.NET Core)** 템플릿 프로젝트가 표시되지 않으면 **새 프로젝트** 대화 상자의 왼쪽 창에서 **Open Visual Studio 설치 관리자** 링크를 클릭합니다.

   ![새 프로젝트 대화 상자에서 Visual Studio 설치 관리자 열기 링크를 클릭합니다.](../ide/media/vb-open-visual-studio-installer-hello-world.png)

     Visual Studio 설치 관리자가 시작됩니다. **.NET Core 플랫폼 간 개발** 워크로드를 선택한 다음 **수정**을 선택합니다.

     ![Visual Studio 설치 관리자의 .NET Core 플랫폼 간 개발 워크로드](../ide/media/dot-net-core-xplat-dev-workload.png)

## <a name="create-the-application"></a>응용 프로그램 만들기
Visual Basic 프로젝트 템플릿을 선택하고 프로젝트 이름을 지정한 후에 Visual Studio에서 간단한 "Hello World" 응용 프로그램을 만듭니다. <xref:System.Console.WriteLine%2A> 메서드를 호출하여 리터럴 문자열 "Hello World!"를 콘솔 창에 표시합니다.

![템플릿에서 기본 Hello World 코드 보기](../ide/media/vb-console-helloworld-template.png)

IDE에서 **HelloWorld** 단추를 클릭하면 디버그 모드에서 프로그램을 실행할 수 있습니다.

  ![Hello World 단추를 클릭하여 디버그 모드에서 프로그램을 실행합니다.](../ide/media/vb-console-hello-world-button.png)

이렇게 하면 콘솔 창이 잠깐만 표시되었다가 닫힙니다. 단일 문을 실행한 후에 응용 프로그램이 종료되도록 `Main` 메서드가 종료되기 때문에 이런 결과가 발생합니다.

### <a name="add-some-code"></a>일부 코드를 추가합니다.
응용 프로그램을 일시 중지하고 사용자 입력을 요청하는 코드를 추가해 보겠습니다.

1. <xref:System.Console.WriteLine%2A> 메서드 호출 바로 다음에 아래 코드를 추가합니다.

   ```vb
   Console.Write("Press any key to continue...")
   Console.ReadKey(true)
   ```
   이 키를 누를 때까지 프로그램을 일시 중지합니다.

2. 메뉴 모음에서 **빌드** > **솔루션 빌드**를 선택합니다.

   이렇게 하면 프로그램이 IL(중간 언어)로 컴파일됩니다. 이 컴파일 결과는 JIT(Just-In-Time) 컴파일러에 의해 이진 코드로 변환됩니다.

## <a name="run-the-application"></a>응용 프로그램 실행
1. 도구 모음에서 **HelloWorld** 단추를 클릭합니다.

   ![Hello World 단추를 클릭하여 도구 모음에서 프로그램을 실행합니다.](../ide/media/vb-console-hello-world-button.png)

2. 콘솔 창을 닫으려면 아무 키나 누릅니다.

   ![Hello World 및 계속하려면 아무 키나 누르세요.를 표시하는 콘솔 창](../ide/media/vb-console-hello-world-press-any-key.png)

## <a name="next-steps"></a>다음 단계
이 빠른 시작을 완료한 것을 축하 드립니다! Visual Basic 및 Visual Studio IDE를 이해하는 데 도움이 되었기를 바랍니다. 자세히 알아보려면 계속 다음 자습서를 사용하세요.

> [!div class="nextstepaction"]
> [Visual Studio에서 Visual Basic 시작](tutorial-visual-basic-console.md)

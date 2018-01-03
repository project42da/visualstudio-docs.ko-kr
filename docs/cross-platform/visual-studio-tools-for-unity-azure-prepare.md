---
title: "Visual Studio Tools for Unity Azure Walkthrough 준비 | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: B921C2AC-B5D6-4B24-918E-511F83D57275
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: 7554380435c77750eb48a5ce261cc0a2b3885ccd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="prepare-the-development-environment"></a>개발 환경 준비

Unity에서 Azure Mobile Client SDK를 사용하기 위한 몇 가지 	필수 구성 요소가 있습니다.

## <a name="download-and-install-unity-2017"></a>Unity 2017 다운로드 및 설치

Unity 2017.1 이상이 필요합니다. 무료 개인 계획을 포함해 모든 Unity 계획을 연습에 사용할 수 있습니다. https://store.unity.com/에서 Unity를 다운로드합니다.

## <a name="download-and-install-visual-studio-2017"></a>Visual Studio 2017 다운로드 및 설치

연습에는 Unity를 사용한 게임 개발 워크로드와 함께 Visual Studio 2017 15.3 이상이 필요합니다. 무료 커뮤니티 에디션을 포함한 Visual Studio 2017의 모든 에디션을 연습에 사용할 수 있습니다.

1. https://www.visualstudio.com/에서 Visual Studio 2017을 다운로드합니다.

2. Visual Studio 2017을 설치하고 **Unity를 사용한 게임 개발** 워크로드가 활성화되어 있는지 확인합니다.

 ![Unity 워크로드 선택](media/vstu_azure-prepare-dev-environment-image0.png)

 > [!NOTE]
 > Visual Studio 2017이 이미 설치되어 있는 경우 Visual Studio 설치 관리자를 실행하여 워크로드를 보고 수정할 수 있습니다.

## <a name="create-a-new-3d-unity-project"></a>새 3D Unity 프로젝트 만들기

Unity 실행 및 새로운 3D 프로젝트 만들기

![새 Unity 프로젝트 만들기](media/vstu_azure-prepare-dev-environment-image1.png)

## <a name="set-the-script-editor-to-visual-studio-preview-2017"></a>스크립트 편집기를 Visual Studio Preview 2017로 설정

Visual Studio 2017이 이미 Unity의 외부 스크립트 편집기로 설정되어 있을 수 있지만, 15.3 Preview 버전을 선택하는 것이 중요합니다.

1. Unity **편집** 메뉴에서 **편집 > 기본 설정...**을 선택합니다.

  ![기본 설정 메뉴 열기](media/vstu_azure-prepare-dev-environment-image1.2.png)

2. Unity 기본 설정 창이 팝업되면 왼쪽에서 **외부 도구** 탭을 선택합니다.

3. **외부 스크립트 편집기** 드롭다운 메뉴에서 **Visual Studio 2017**을 선택합니다.

  ![외부 스크립트 편집기 설정](media/vstu_azure-prepare-dev-environment-image3.png)

## <a name="change-the-unity-scripting-runtime-to-net-46"></a>Unity 스크립팅 런타임을 .NET 4.6으로 변경
연습에서 Azure Mobile Client SDK 및 종속 항목을 사용하려면 NET 4.6이 필요합니다.

1. Unity **파일** 메뉴에서 **파일 > 빌드 설정...**을 선택합니다.

  ![빌드 설정 열기](media/vstu_azure-prepare-dev-environment-image4.png)

2. **플레이어 설정...** 단추를 클릭합니다.

  ![플레이어 설정 열기](media/vstu_azure-prepare-dev-environment-image5.png)

3. 플레이어 설정은 Unity Inspector 창에서 열립니다. **구성** 제목에서 **스크립팅 런타임 버전** 드롭다운을 클릭하고 **실험적(.NET 4.6 동등)**을 선택합니다. 그러면 Unity를 다시 시작하라는 대화 상자가 나타납니다. **다시 시작**을 선택합니다.

  ![.NET 4.6 선택](media/vstu_azure-prepare-dev-environment-image6.png)

## <a name="add-a-reference-to-systemnethttpdll"></a>System.Net.Http.dll에 참조 추가

Unity .NET 4.6 동등 스크립팅 런타임을 통해 Azure Mobile Client SDK에서 필요한 System.Net.Http 패키지를 사용할 수 있습니다. DLL 파일은 Unity에 포함되어 있지만, 사용하려면 참조를 추가해야 합니다.

1. Unity 편집기 프로젝트 창에서 **자산** 폴더를 **마우스 오른쪽 단추로 클릭**하고 **탐색기에서 표시**

  ![탐색기에서 자산 폴더 표시](media/vstu_azure-prepare-dev-environment-image7.png)

2. 팝업되는 탐색기 창에서 **자산** 디렉터리를 두 번 클릭하여 엽니다.

3. 자산 디렉터리 안에서 **마우스 오른쪽 단추로 클릭**하고 **새로 만들기 > 텍스트 문서**를 선택합니다.

4. 텍스트 편집기에서 새 텍스트 문서를 열고 라인: `-r:System.Net.Http.dll`을 추가합니다.

5. 문서를 저장하고 닫습니다.

4. 새 텍스트 문서의 이름을 "**mcs.rsp**"로 바꾸고 .txt 파일 확장자를 삭제합니다.

  * 파일 확장자가 숨겨져 있는 경우에는 표시하도록 폴더 보기 옵션을 변경해야 합니다.
  * 시작 메뉴를 열고 "folder options"를 입력하여 검색합니다. "**파일 탐색기 옵션**"을 선택합니다.
  * **보기** 탭을 선택하고 고급 설정에서 "**알려진 파일 형식의 파일 확장명 숨기기**”가 선택 취소되어 있는지 확인합니다.

    ![탐색기에서 자산 폴더 표시](media/vstu_azure-prepare-dev-environment-image8.png)

이 단계를 완료하면 Unity 프로젝트의 루트 **자산** 디렉터리에 라인 `r:System.Net.Http.dll`가 포함된 **mcs.rsp**라는 파일이 만들어집니다.

>[!NOTE]
> 참조가 기능하려면 Visual Studio 15.3+ Unity 워크로드에 포함되어 있는 Visual Studio Tools for Unity 3.3 이상이 필요합니다. 이 단계가 제대로 실행되지 않는다면 올바른 버전의 VSTU가 설치되어 있는지 확인하십시오.

## <a name="add-the-newtonsoftjson-nuget-package-to-your-project"></a>프로젝트에 Newtonsoft.Json NuGet 패키지 추가

Azure Mobile Client SDK는 Newtonsoft.Json 패키지가 필요합니다. 죄송합니다. Unity는 NuGet을 지원하지 않습니다. Visual Studio에서 Unity 프로젝트를 열고 NuGet이 포함된 패키지를 추가하면 Unity는 다음 번에 Unity 편집기에서 프로젝트를 열 때 이를 삭제합니다. 하지만, NuGet의 패키지는 Unity 프로젝트에 수동으로 추가할 수 있습니다.

1. Unity 프로젝트의 자산 디렉터리에 "**NuGet Packages**"라고 하는 새 폴더를 만듭니다. 단지 구성을 위한 것입니다.

2. https://www.nuget.org/packages/Newtonsoft.Json/으로 이동하여 **수동 다운로드** 단추를 클릭합니다. .nupkg 파일을 다운로드합니다.

  ![탐색기에서 자산 폴더 표시](media/vstu_azure-prepare-dev-environment-image9.png)

3. 새로 다운로드한 파일을 찾고 파일 확장자를 .nupkg에서 **.zip**으로 바꿉니다. 그러면 다른 zip 파일과 마찬가지로 포함된 파일을 보고 압축을 풀 수 있습니다.

4. zip 디렉터리를 열거나 압축을 해제하고 **\lib\net45**로 이동합니다.

5. **Newtonsoft.Json.dll** 파일을 Unity 프로젝트의 **Assets\NuGet Packages** 디렉터리에 복사합니다.

## <a name="add-the-azure-mobile-client-sdk-nuget-package-to-your-project"></a>Azure Mobile Client SDK NuGet 패키지를 프로젝트에 추가합니다.

Azure Mobile Client SDK에는 Azure의 간편한 테이블로 쉽게 읽고 쓸 수 있는 함수가 포함되어 있습니다.

1. https://www.nuget.org/packages/Microsoft.Azure.Mobile.Client/로 이동하여 **수동 다운로드** 단추를 클릭합니다. .nupkg 파일을 다운로드합니다.

2. 새로 다운로드한 파일을 찾고 파일 확장자를 .nupkg에서 **.zip**으로 바꿉니다. 그러면 다른 zip 파일과 마찬가지로 포함된 파일을 보고 압축을 풀 수 있습니다.

3. zip 디렉터리를 열거나 압축을 해제하고 **\lib\net45**로 이동합니다.

4. **Microsoft.Azure.Mobile.Client.dll** 파일을 Unity 프로젝트의 **Assets\NuGet Packages** 디렉터리에 복사합니다.

>[!WARNING]
> 위의 단계를 완료한 후 Unity를 다시 시작해야 합니다. Visual Studio 또는 InteliSense가 새로 추가된 패키지를 인식하지 않을 수 있습니다.

## <a name="conclusion"></a>결론

위의 단계를 완료한 후 Azure Mobile Client SDK를 사용하도록 Unity 프로젝트를 설정해야 합니다. Unity 프로젝트에서 새로운 C# 스크립트를 만들고 Visual Studio에서 연 다음 맨 위에 다음 using 문을 입력하여 개발 환경을 테스트할 수 있습니다.
```
using System.Net.Http;
using Newtonsoft.Json;
using Microsoft.WindowsAzure.MobileServices;
```

InteliSense가 이러한 using 문을 감지하면 설정이 제대로 완료된 것입니다. 오류가 있거나 InteliSense에서 이러한 패키지를 인식하지 못할 경우 Unity 및 Visual Studio를 다시 시작해 보세요. 그래도 작동하지 않으면 위의 단계를 다시 수행하세요.

## <a name="next-step"></a>다음 단계

* [데이터 모델 클래스 만들기](visual-studio-tools-for-unity-azure-data.md)

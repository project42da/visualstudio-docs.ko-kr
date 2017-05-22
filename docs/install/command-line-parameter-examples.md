---
title: "Visual Studio 설치에 대한 명령줄 매개 변수 예 | Microsoft Docs"
ms.custom: 
ms.date: 05/06/2017
ms.reviewer: tims
ms.suite: 
ms.technology:
- vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 837F31AA-F121-46e9-9996-F8BCE768E579
author: timsneath
ms.author: tims
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 85576806818a6ed289c2f660f87b5c419016c600
ms.openlocfilehash: 0f07824b29e7851e353d472838a897853e227d6c
ms.contentlocale: ko-kr
ms.lasthandoff: 05/09/2017

---
# <a name="command-line-parameter-examples-for-visual-studio-2017-installation"></a>Visual Studio 2017 설치에 대한 명령줄 매개 변수 예
[명령줄 매개 변수를 사용하여 Visual Studio를 설치](use-command-line-parameters-to-install-visual-studio.md)하는 방법을 보여 주기 위해 사용자의 요구에 맞게 사용자 지정할 수 있는 몇 가지 예를 제공합니다.

각 예에서 `vs_enterprise.exe`, `vs_professional.exe` 및 `vs_community.exe`는 다운로드 프로세스를 시작하는 1MB 정도 크기의 작은 파일인 Visual Studio 부트스트래퍼의 해당 버전을 나타냅니다. 다른 버전을 사용하는 경우에는 적절한 부트스트래퍼 이름으로 대체합니다.

> [!NOTE]
> 모든 명령에는 관리자 권한 상승이 필요하며 상승된 프롬프트에서 프로세스가 시작되지 않는 경우 사용자 계정 컨트롤 프롬프트가 표시됩니다.

> [!NOTE]
>  명령줄의 끝에 `^` 문자를 사용하여 여러 줄을 하나의 명령으로 연결할 수 있습니다. 또는 이러한 줄을 한꺼번에 단일 행에 배치할 수도 있습니다. PowerShell에서 일치하는 항목은 억음 악센트(`` ` ``) 문자입니다. 

* 대화형 프롬프트 없이 진행률이 표시되는 Visual Studio의 최소 인스턴스를 설치합니다.
```
vs_enterprise.exe --installPath C:\minVS ^
   --add Microsoft.VisualStudio.Workload.CoreEditor ^
   --passive --norestart
```

* 제품을 설치해야만 반환되는 프랑스어 언어 팩을 포함한 Visual Studio의 데스크톱 인스턴스를 자동으로 설치합니다.
```
vs_enterprise.exe --installPath C:\desktopVS ^
   --addProductLang fr-FR ^
   --add Microsoft.VisualStudio.Workload.ManagedDesktop ^
   --includeRecommended --quiet --wait
```

> [!NOTE]
>  `--wait` 매개 변수는 배치 파일에서 사용하도록 설계되었습니다. 배치 파일에서 다음 명령의 실행은 설치가 완료될 때까지 계속되지 않습니다. `%ERRORLEVEL%` 환경 변수는 [명령줄 매개 변수를 사용하여 Visual Studio 설치](use-command-line-parameters-to-install-visual-studio.md) 페이지에 나오는 대로 명령의 반환 값을 포함합니다.

* Visual Studio 핵심 편집기를 다운로드합니다(최소한의 Visual Studio 구성). 영어 언어 팩만 포함:

```cmd
vs_community.exe --layout C:\VS2017
   --lang en-US ^
   --add Microsoft.VisualStudio.Workload.CoreEditor
```

* .NET 데스크톱 및 .NET 웹 워크로드를 모든 권장 구성 요소 및 GitHub 확장명과 함께 다운로드합니다. 영어 언어 팩만 포함:
```
vs_community.exe --layout C:\VS2017 ^
   --lang en-US ^
   --add Microsoft.VisualStudio.Workload.NetWeb ^
   --add Microsoft.VisualStudio.Workload.ManagedDesktop ^
   --add Component.GitHub.VisualStudio ^
   --includeRecommended
```

* Visual Studio 2017 Enterprise Edition에서 사용할 수 있는 모든 워크로드 및 구성 요소의 대화형 설치를 시작합니다.
```
vs_enterprise.exe --all --includeRecommended --includeOptional
```

* Node.js 개발 지원을 통해 Visual Studio 2017 Community Edition이 이미 설치된 컴퓨터에 Visual Studio 2017 Professional의 두 번째 명명된 인스턴스를 설치합니다.
```
vs_professional.exe --installPath C:\VSforNode ^
   --add Microsoft.VisualStudio.Workload.Node --includeRecommended --nickname VSforNode
```

* 기본 설치된 Visual Studio 인스턴스에서 프로파일링 도구 구성 요소를 제거합니다.
```
vs_enterprise.exe modify ^
   --installPath "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise" ^
   --remove Microsoft.VisualStudio.Component.DiagnosticTools ^
   --passive
```

## <a name="see-also"></a>참고 항목

 * [Visual Studio 관리자 가이드](visual-studio-administrator-guide.md)
 * [명령줄 매개 변수를 사용하여 Visual Studio 설치](use-command-line-parameters-to-install-visual-studio.md)
 * [Visual Studio 2017의 오프라인 설치 만들기](create-an-offline-installation-of-visual-studio.md)


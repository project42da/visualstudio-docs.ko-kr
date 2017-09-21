---
title: "낮은 대역폭 또는 불안정한 네트워크 환경에 설치 | Microsoft Docs"
description: "불안정한 네트워크 조건에서 Visual Studio 설치 관리자가 어떻게 작동하는지 설명하고 설치를 시작하기 전에 설치 파일을 다운로드하는 방법을 설명합니다."
ms.date: 04/14/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 44DB1998-68CD-4560-870A-EE5B993DCF6E
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
ms.openlocfilehash: 9dbe70bce6c246416df64de304b06cd211320f2a
ms.contentlocale: ko-kr
ms.lasthandoff: 05/09/2017

---

# <a name="install-visual-studio-2017-on-low-bandwidth-or-unreliable-network-environments"></a>낮은 대역폭 또는 불안정한 네트워크 환경에 Visual Studio 2017 설치
새로운 Visual Studio 2017 설치 관리자는 매우 다양한 네트워크 및 컴퓨터 조건에서 제대로 작동하도록 구성되어 있습니다.

- Visual Studio 설치에 필요한 파일은 전역 배달 네트워크에 배포되므로 로컬 서버에서 해당 파일을 가져올 수 있습니다.
- 설치하는 동안 바이러스 백신 및 프록시 소프트웨어의 간섭을 최소화하기 위해 세 가지 다운로드 기술(WebClient, BITS 및 WinInet)이 시도됩니다.
- 새 워크로드 기반 모델에서는 Visual Studio의 이전 버전을 포함한 것보다 적게 설치해야 합니다.

따라서 새 웹 설치 관리자를 시도하는 것이 좋습니다. 좋은 경험이 될 것입니다. 하지만 Visual Studio 설치를 시작하기 전에 설치 파일을 성공적으로 다운로드했는지 확인하려는 경우 쉽게 확인할 수 있습니다. 명령줄을 사용하여 설치를 시작하기 전에 필요한 파일의 로컬 캐시를 만들 수 있습니다.

방법은 다음과 같습니다.

## <a name="download-the-visual-studio-bootstrapper"></a>Visual Studio 부트스트래퍼 다운로드
먼저 선택한 Visual Studio 버전에 대한 Visual Studio 부트스트래퍼를 다운로드합니다.

설치 파일&mdash;또는 더 구체적으로 부트스트래퍼 파일&mdash;다음 중 하나와 일치하거나 비슷합니다.

| 버전                    | 파일                                                                    |
|----------------------------|-------------------------------------------------------------------------|
| Visual Studio 커뮤니티    | [vs_community.exe](https://aka.ms/vs/15/release/vs_community.exe)       |
| Visual Studio Professional | [vs_professional.exe](https://aka.ms/vs/15/release/vs_professional.exe) |
| Visual Studio Enterprise   | [vs_enterprise.exe](https://aka.ms/vs/15/release/vs_enterprise.exe)     |

## <a name="create-a-local-install-cache"></a>로컬 설치 캐시 만들기
로컬 레이아웃을 만들려면 명령 프롬프트를 열고 다음 예제의 명령 중 하나를 사용합니다. 이 문서의 예제에서는 Visual Studio Community 부트스트래퍼를 다운로드했다고 가정합니다. 사용 주인 버전에 맞게 명령을 조정하세요.

- .NET 웹 및 .NET 데스크톱 개발의 경우 다음을 실행합니다.
  ```
  vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US
  ```
- .NET 데스크톱 및 Office 개발의 경우 다음을 실행합니다.
  ```
  vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.Office --includeOptional --lang en-US
  ```
- C++ 데스크톱 개발의 경우 다음을 실행합니다.
  ```
  vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.NativeDesktop --includeRecommended --lang en-US
  ```

- 모든 기능이 포함된 전체 로컬 레이아웃을 만들려면(_수많은_ 기능이 있어서 오래 걸릴 수 있음) 다음을 실행합니다.
  ```
  vs_community.exe --layout c:\vs2017layout --lang en-US
  ```

영어 이외의 언어를 설치하려면 이 페이지 아래쪽에 있는 목록에서 `en-US`를 로캘로 변경합니다. 이 [사용 가능한 구성 요소 및 워크로드 목록](workload-and-component-ids.md)을 사용하여 필요에 따라 설치 캐시를 추가로 사용자 지정합니다.

## <a name="install-from-the-local-cache"></a>로컬 캐시에서 설치
로컬 설치 캐시에서 실행할 경우 이러한 각 파일의 로컬 버전을 사용하게 됩니다. 하지만 설치하는 동안 캐시에 없는 구성 요소를 선택하면 인터넷에서 해당 구성 요소를 다운로드하려고 시도합니다.

다운로드한 파일만 설치하려면 레이아웃 캐시를 만드는 데 사용한 것과 같은 명령줄 옵션을 사용하세요. 예를 들어 다음 명령으로 레이아웃 캐시를 만든 경우

```
vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US
```

이 명령을 사용하여 설치를 실행합니다.

```
c:\vs2017layout\vs_community.exe --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional
```

## <a name="list-of-language-locales"></a>언어 로캘 목록
| **언어 로캘** | **언어** |
| ----------------------- | --------------- |  
| cs-CZ | 체코어 |
| de-DE | 독일어 |
| ko-KR | 영어 |
| es-ES | 스페인어 |
| fr-FR | 프랑스어 |
| it-IT | 이탈리아어 |
| ja-JP | 일본어 |
| ko-KR | 한국어 |
| pl-PL | 폴란드어 |
| pt-BR | 포르투갈어 - 브라질 |
| ru-RU | 러시아어 |
| tr-TR | 터키어 |
| zh-CN | 중국어 - 간체 |
| zh-TW | 중국어 - 번체 |

## <a name="see-also"></a>참고 항목
* [Visual Studio 설치](install-visual-studio.md)
* [Visual Studio 관리자 가이드](visual-studio-administrator-guide.md)
* [명령줄 매개 변수를 사용하여 Visual Studio 설치](use-command-line-parameters-to-install-visual-studio.md)


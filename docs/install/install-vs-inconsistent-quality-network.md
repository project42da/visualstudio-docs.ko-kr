---
title: 낮은 대역폭 또는 불안정한 네트워크 환경에 설치 | Microsoft Docs
description: 불안정한 네트워크 조건에서 Visual Studio 설치 관리자가 어떻게 작동하는지 설명하고 설치를 시작하기 전에 설치 파일을 다운로드하는 방법을 설명합니다.
ms.date: 01/17/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- installing Visual Studio
- no internet connection
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3a9a0263c79e1dd2c7d0aacc5f405185cad3c3e7
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2018
---
# <a name="install-visual-studio-2017-on-low-bandwidth-or-unreliable-network-environments"></a>낮은 대역폭 또는 불안정한 네트워크 환경에 Visual Studio 2017 설치

따라서 Visual Studio 웹 설치 관리자를 시도하는 것이 좋습니다.&mdash;대부분 좋은 경험이 될 것입니다.

 > [!div class="button"]
 > [Visual Studio 2017 다운로드](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocsOL)
<br/>

그러나 인터넷 연결을 찾을 수 없거나 안정적이지 않다면 명령줄을 사용하여 오프라인 설치를 완료하기 필요한 파일의 로컬 캐시를 만들 수 있습니다. 방법은 다음과 같습니다.

> [!NOTE]
> 인터넷에서 방화벽이 사용되는 클라이언트 워크스테이션의 네트워크에 대해 Visual Studio 2017의 배포를 수행하려고 하는 엔터프라이즈 관리자인 경우 [Visual Studio 2017의 네트워크 설치 만들기](../install/create-a-network-installation-of-visual-studio.md) 및 [Visual Studio 오프라인 설치에 필요한 인증서 설치](../install/install-certificates-for-visual-studio-offline.md) 페이지를 참조하세요.

## <a name="step-1---download-the-visual-studio-bootstrapper"></a>1단계 - Visual Studio 부트스트래퍼 다운로드

먼저 선택한 Visual Studio 버전에 대한 Visual Studio 부트스트래퍼를 다운로드합니다.

설치 파일&mdash;또는 더 구체적으로 부트스트래퍼 파일&mdash;다음 중 하나와 일치하거나 비슷합니다.

| 버전                    | 파일                                                                    |
|----------------------------|-------------------------------------------------------------------------|
| Visual Studio 커뮤니티    | [vs_community.exe](https://aka.ms/vs/15/release/vs_community.exe)       |
| Visual Studio Professional | [vs_professional.exe](https://aka.ms/vs/15/release/vs_professional.exe) |
| Visual Studio Enterprise   | [vs_enterprise.exe](https://aka.ms/vs/15/release/vs_enterprise.exe)     |

## <a name="step-2---create-a-local-install-cache"></a>2다계 - 로컬 설치 캐시 만들기

이 단계를 완료하려면 인터넷 연결이 있어야 합니다. 로컬 레이아웃을 만들려면 명령 프롬프트를 열고 다음 예제에 나오는 명령 중 하나를 사용합니다(여기에 있는 예제는 Visual Studio의 커뮤니티 에디션을 사용하고 있는 것으로 가정하고, 에디션에 적절하게 명령을 조정합니다).

- .NET 웹 및 .NET 데스크톱 개발의 경우 다음을 실행합니다.

   ```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US```

- .NET 데스크톱 및 Office 개발의 경우 다음을 실행합니다.

   ```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.Office --includeOptional --lang en-US```

- C++ 데스크톱 개발의 경우 다음을 실행합니다.

   ```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.NativeDesktop --includeRecommended --lang en-US```

- 모든 기능이 포함된 전체 로컬 레이아웃을 만들려면(&mdash;_수많은_ 기능이 있어서 오래 걸릴 수 있음) 다음을 실행합니다.

   ```vs_community.exe --layout c:\vs2017layout --lang en-US```

영어 이외의 언어를 설치하려면 이 페이지 아래쪽에 있는 목록에서 `en-US`를 로캘로 변경합니다. 이 [사용 가능한 구성 요소 및 워크로드 목록](workload-and-component-ids.md)을 사용하여 필요에 따라 설치 캐시를 추가로 사용자 지정합니다.

> [!IMPORTANT]
> 전체 Visual Studio 2017 레이아웃에는 35GB 이상의 디스크 공간이 필요하며 다운로드하는 데 다소 시간이 걸릴 수 있습니다. 설치하려는 구성 요소로만 레이아웃을 만드는 방법에 대한 자세한 내용은 [명령줄 매개 변수를 사용하여 Visual Studio 2017 설치](use-command-line-parameters-to-install-visual-studio.md)를 참조하세요.

## <a name="step-3---install-visual-studio-from-the-local-cache"></a>3단계 - 로컬 캐시에서 Visual Studio 설치

> [!TIP]
> 로컬 설치 캐시에서 실행할 경우 설치 시 이러한 각 파일의 로컬 버전을 사용하게 됩니다. 하지만 설치하는 동안 캐시에 없는 구성 요소를 선택하면 인터넷에서 해당 구성 요소를 다운로드하려고 시도합니다.

다운로드한 파일만 설치하려면 레이아웃 캐시를 만드는 데 사용한 것과 같은 명령줄 옵션을 사용하세요. 예를 들어 다음 명령으로 레이아웃 캐시를 만든 경우

```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US```

이 명령을 사용하여 설치를 실행합니다.

```c:\vs2017layout\vs_community.exe --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional```

> [!NOTE]
> 서명이 올바르지 않다는 오류가 발생하면 업데이트된 인증서를 설치해야 합니다. 오프라인 캐시에서 인증서 폴더를 엽니다. 각 인증서 파일을 두 번 클릭하고 인증서 관리자 마법사를 클릭합니다. 암호를 묻는 메시지가 표시되면 비워 두세요.

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

## <a name="get-support"></a>지원 받기
때로는 무엇인가 잘못될 수도 있습니다. Visual Studio 설치에 실패하는 경우에는 [Visual Studio 2017 설치 및 업그레이드 문제 해결](troubleshooting-installation-issues.md) 페이지를 참조하세요. 문제 해결 단계가 도움이 되지 않는 경우 라이브 채팅을 통해 Microsoft에 설치 지원을 문의할 수 있습니다(영어만 가능). 자세한 내용은 [Visual Studio 지원 페이지](https://www.visualstudio.com/vs/support/#talktous)를 참조하세요.

몇 가지 추가 지원 옵션은 다음과 같습니다.
* Visual Studio 설치 관리자와 Visual Studio IDE에 모두 표시되는 [문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md) 도구를 통해 Microsoft에 제품 문제를 보고할 수 있습니다.
* [UserVoice](https://visualstudio.uservoice.com/forums/121579)에서 Microsoft와 제품 제안을 공유할 수 있습니다.
* [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/)에서 제품 문제를 추적하고 질문을 하고 답을 찾을 수 있습니다.
* [Gitter 커뮤니티의 Visual Studio 관련 대화](https://gitter.im/Microsoft/VisualStudio)를 통해 Microsoft 및 다른 Visual Studio 개발자와 소통할 수도 있습니다.  (이 옵션을 사용하려면 [GitHub](https://github.com/) 계정이 필요합니다.)

## <a name="see-also"></a>참고 항목
* [Visual Studio 설치](install-visual-studio.md)
* [Visual Studio 관리자 가이드](visual-studio-administrator-guide.md)
* [명령줄 매개 변수를 사용하여 Visual Studio 설치](use-command-line-parameters-to-install-visual-studio.md)

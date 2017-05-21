---
title: "설치 문제 해결 | Microsoft Docs"
description: '{{PLACEHOLDER}}'
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
ms.assetid: 556EDD3F-E365-43EE-B3DD-03AA4353F75B
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
ms.openlocfilehash: d8125873ab5a92d9af26c556cb2f953a606c28d9
ms.contentlocale: ko-kr
ms.lasthandoff: 05/09/2017

---
# <a name="troubleshooting-visual-studio-2017-installation-and-upgrade-failures"></a>Visual Studio 2017 설치 및 업그레이드 실패 문제 해결

## <a name="symptoms"></a>증상
Microsoft Visual Studio 2017을 설치 또는 업데이트할 때 작업이 실패합니다.

## <a name="workaround"></a>해결 방법
이 문제를 해결하려면 아래 단계를 수행합니다.

### <a name="step-1---check-whether-this-problem-is-a-known-issue"></a>1단계 - 이 문제가 알려진 문제인지 확인
Microsoft에서 수정을 진행하고 있는 Visual Studio 설치 관리자에 관련된 몇 가지 알려진 문제가 있습니다. [릴리스 정보의 알려진 문제 섹션](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-relnotes#KIinstall)을 확인하여 문제에 대한 해결 방법이 있는지 확인하세요.

### <a name="step-2---check-with-the-developer-community"></a>2단계 - 개발자 커뮤니티에서 확인
[Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/spaces/8/index.html에서 오류 메시지를 검색합니다. 커뮤니티의 다른 멤버가 문제에 대한 해결책을 문서화했을 수 있습니다.

### <a name="step-3---delete-the-visual-studio-installer-directory-to-fix-upgrade-problems"></a>3단계 - Visual Studio 설치 관리자 디렉터리를 삭제하여 업그레이드 문제 해결
Visual Studio 설치 관리자 부트스트래퍼는 나머지 Visual Studio 설치 관리자를 설치하는 최소한의 간단한 실행 파일입니다. Visual Studio 설치 관리자 파일을 삭제하고 부트스트래퍼를 다시 실행하면 몇 가지 업데이트 실패가 해결될 수 있습니다. 이를 수행하려면 다음 단계를 따르십시오.

1. Visual Studio 설치 관리자를 닫습니다.
2. Visual Studio 설치 관리자 디렉터리를 삭제합니다. 일반적으로 디렉터리는 C:\Program Files (x86)\Microsoft Visual Studio\Installer입니다.
3. Visual Studio 설치 관리자 부트스트래퍼를 실행합니다. Downloads 폴더에서 ```vs_[Visual Studio edition]__*.exe``` 패턴을 따르는 파일 이름을 사용하는 부트스트래퍼를 찾을 수 있습니다. 해당 응용 프로그램을 찾을 수 없으면 [Visual Studio Downloads](https://www.visualstudio.com/downloads/)(Visual Studio 다운로드) 페이지로 이동하고 해당 버전의 Visual Studio에 대한 **download**(다운로드)를 클릭하여 부트스트래퍼를 다운로드할 수 있습니다. 이 실행 파일을 실행하여 설치 메타데이터를 다시 설정합니다.
4. Visual Studio를 다시 설치하거나 업데이트해 보세요. 설치 관리자가 계속 실패하면 바로 아래 4단계로 이동합니다.
<br/>**참고:** 이 단계에서는 Visual Studio 설치 관리자 파일을 다시 설치하고 설치 메타데이터를 다시 설정합니다. 

### <a name="step-4---report-a-problem"></a>4단계 - 문제 보고
경우에 따라 손상된 파일에 관련된 문제인 경우 문제를 사례별로 확인해야 할 수 있습니다.

1. [Microsoft Visual Studio 및 .NET Framework 로그 수집 도구](https://www.microsoft.com/en-us/download/details.aspx?id=12493)를 다운로드하고 실행합니다. 이 도구는 Visual Studio, .NET Framework 및 SQL Server 설치에 대한 사용 가능한 설치 로그를 수집하여 컴파일합니다.
2. Visual Studio 설치 관리자를 열고 **문제 보고**를 클릭하여 Visual Studio 피드백 도구를 엽니다.
![[피드백 제공] 단추를 탭하여 피드백 도구를 열 수 있음](media/report-a-problem.png)
3. 문제 보고서의 제목을 지정하고 관련 세부 정보를 제공합니다. **다음**을 클릭하여 **첨부 파일** 섹션으로 이동하고 생성된 로그 파일을 첨부합니다. 일반적으로 파일은 %TEMP%\vslogs.zip에 있습니다.
![[새로운 문제 보고] 단추를 탭하여 단계 진행](media/problem-report-details.png)
4. **다음**을 클릭하여 문제 보고서를 검토하고 **제출**을 클릭합니다.

### <a name="step-5---run-installcleanupexe-to-clean-up-installation-files"></a>5단계 - InstallCleanup.exe를 실행하여 설치 파일 정리
마지막 수단으로 InstallCleanup.exe를 실행할 수 있습니다. InstallCleanup.exe는 Visual Studio 설치 관리자와 함께 패키지된 유틸리티로서, 설치 파일을 정리합니다. 이는 전체 다시 설치가 아닙니다. 이 유틸리티는 Visual Studio 2017에 대한 캐시 및 인스턴스 데이터를 삭제합니다.

1. Visual Studio 설치 관리자를 닫습니다.
2. 관리자 명령 프롬프트를 엽니다. 이를 수행하려면 다음 단계를 따르십시오.
   * **시작** 메뉴에서 **실행**을 클릭합니다([시작] + R).
   * **cmd**를 입력합니다.
   * **명령 프롬프트**를 마우스 오른쪽 단추로 클릭하고 **관리자 권한으로 실행**을 선택합니다.
3. InstallCleanup.exe 유틸리티의 전체 경로를 입력하고 명령줄 스위치 -f를 전달합니다. 기본적으로 유틸리티 경로는 다음과 같습니다.
   ```
   C:\Program Files (x86)\Microsoft Visual Studio\Installer\resources\app\layout\InstallCleanup.exe
   ```
4. 3단계에서 설명된 부트스트래퍼를 다시 실행합니다.
5. Visual Studio를 다시 설치하거나 업데이트해 보세요.

## <a name="how-to-troubleshoot-an-offline-installer"></a>오프라인 설치 관리자 문제를 해결하는 방법
다음 표에서는 로컬 레이아웃에서 설치할 경우 알려진 문제 및 도움이 되는 몇 가지 해결 방법을 보여 줍니다.

| 문제       | 항목                   | 솔루션 |
| ----------- | ---------------------- | -------- |
| 사용자에게 파일에 액세스할 수 있는 권한이 없습니다. | 권한(ACL) | 오프라인 설치를 공유하기 *전에* 먼저 다른 사용자에게 읽기 액세스 권한을 부여하도록 권한(ACL)을 조정해야 합니다. |
| 새 작업, 구성 요소 또는 언어가 설치되지 않습니다.  | `--layout`  | 부분 레이아웃에서 설치하고 이전 레이아웃에서 사용할 수 없는 작업, 구성 요소 또는 언어를 선택하는 경우 인터넷에 액세스할 수 있는지 확인합니다. |




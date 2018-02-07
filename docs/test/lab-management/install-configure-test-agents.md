---
title: "테스트 에이전트 설치 및 구성 | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configure test agents, test lab
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 5caa566e15f7f3c4c69f8d33a6c7dd0eead38785
ms.sourcegitcommit: d6327b978661c0a745bf4b59f32d8171607803a3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2018
---
# <a name="install-and-configure-test-agents"></a>테스트 에이전트 설치 및 구성

Visual Studio 및 Visual Studio Team Services 또는 TFS(Team Foundation Server)를 사용하는 테스트 시나리오의 경우 Agents for Microsoft Visual Studio가 Team Services 또는 TFS와 통신하여 오케스트레이션을 처리하기 때문에 테스트 컨트롤러가 필요하지 않습니다. 예를 들어 Team Services 또는 TFS에서 빌드 및 릴리스 워크플로에 대한 연속 테스트를 실행하고 있습니다.

TFS 2013에서 사용할 테스트 에이전트나 테스트 컨트롤러가 필요한 경우 Agents for Microsoft Visual Studio 2013 업데이트 5를 사용하여 테스트 컨트롤러를 구성합니다.

또한 [Build 또는 Release Management를 대신 사용](use-build-or-rm-instead-of-lab-management.md)하는 것이 더 간편할지 고려해 보세요.

## <a name="what-do-i-need"></a>무엇이 필요한가요?

**테스트 컨트롤러 및 테스트 에이전트를 어디에서 얻을 수 있나요?**

* vNext 빌드 작업을 사용하여 테스트를 실행 중이고 로컬 디렉터리에서 에이전트를 설치하려는 경우 - 

  * [Agents for Microsoft Visual Studio 2015 RTM 및 업데이트 1 다운로드](http://go.microsoft.com/fwlink/p/?LinkId=619266). 

  * [Agents for Microsoft Visual Studio 2017 및 Visual Studio 2015 업데이트 2 다운로드](https://www.visualstudio.com/downloads/download-visual-studio-vs) - **Tools for Visual Studio 2015**를 선택하고 왼쪽 탐색 모음에서 **Agents for Visual Studio 2015**를 선택합니다.

* [Agents for Microsoft Visual Studio 2013 업데이트 5 다운로드](http://go.microsoft.com/fwlink/p/?LinkId=619264) - 다음을 실행하려는 경우:

  * 온-프레미스 원격 컴퓨터를 사용하여 부하 테스트를 실행합니다.

  * Microsoft Test Manager 또는 랩 환경에 대한 MSTest 및 테스트 설정을 사용하여 원격으로 연속 테스트를 실행합니다.

  * TFS 2013을 사용하여 연속 테스트를 실행합니다.

이러한 설치 관리자는 가상 컴퓨터에 쉽게 설치하도록 ISO 파일(가상 CD)로 사용 가능합니다. 

[TFS, Microsoft Test Manager, 테스트 컨트롤러 및 테스트 에이전트의 버전을 혼합할 수 있나요?](#MixedVersions)

**내 테스트 컨트롤러와 테스트 에이전트를 설치하는 데 필요한 시스템 요구 사항은 무엇인가요?**

| 항목 | 요구 사항 |
| ---- | ------------ |
| **에이전트** | Windows 10<br />Windows 8, Windows 8.1<br />Windows 7 서비스 팩 1<br />Windows XP 서비스 팩 3<br />Windows Server 2012, Windows Server 2012 R2<br />Windows Server 2008 릴리스 2, 서비스 팩 1 |
| **컨트롤러** | Windows 10<br />Windows 8, Windows 8.1<br />Windows 7 서비스 팩 1<br />Windows Server 2012, Windows Server 2012 R2<br />Windows Server 2008 릴리스 2, 서비스 팩 1 |
| **.NET Framework** | .NET Framework 4.5 |

## <a name="q--a"></a>Q&A

<!-- BEGINSECTION class="m-qanda" -->

<a name="MixedVersions"></a>

####<a name="q-can-i-mix-versions-of-tfs-microsoft-test-manager-the-test-controller-and-test-agent"></a>Q: TFS, Microsoft Test Manager, 테스트 컨트롤러 및 테스트 에이전트의 버전을 혼합할 수 있나요?

A: 예. 호환 가능하고 지원되는 조합은 다음과 같습니다.

| TFS | Microsoft Test Manager 및 랩 센터 | 컨트롤러 | 에이전트 |
| --- | -------------------------------------- | ---------- | ----- |
| 2015: 2013에서 업그레이드 | 2013 | 2013 |2013 |
| 2015: 새로 설치 | 2013 | 2013 | 2013 |
| 2015: 2013 이상 설치에서 업그레이드 | 2015 | 2013 | 2013 |
| 2013 | 2015 | 2013 | 2013 |

####<a name="q-will-the-test-agent-2015-support-all-the-scenarios-supported-by-test-controller-and-test-agent-of-visual-studio-2013"></a>Q: Test Agent 2015는 Visual Studio 2013의 Test Controller 및 Test Agent에서 지원되는 모든 시나리오를 지원하나요?

A: 모든 새로운 자동화된 테스트 시나리오에서는 Agents for Visual Studio를 사용하는 것이 좋습니다. 빌드 정의에서 테스트 에이전트 배포 작업을 사용하여 컴퓨터에 테스트 에이전트를 다운로드하고 설치할 수 있습니다.
다음 표에서는 Agents for Visual Studio 2013에서 지원되는 시나리오와 TFS(Team Foundation Server) 2015 및 TS(Team Services)에 대한 대체 방법을 보여 줍니다.

| Agents for Visual Studio 2013에서 지원되는 시나리오 | TFS 및 TS의 대체 방법 |
| --- | --- |
| Visual Studio의 빌드-배포-테스트 워크플로 | 사용자는 TFS의 빌드, 배포 및 테스트 시나리오에 [빌드 정의](https://www.visualstudio.com/team-services/continuous-integration/)(XAML 빌드가 아님)를 사용할 수 있습니다. |
| 온-프레미스 원격 컴퓨터를 사용한 부하 테스트(성능 테스트) | Test Controller/Test Agents 2013 업데이트 5를 사용하여 온-프레미스로 부하 테스트를 실행합니다. [추가 정보](https://msdn.microsoft.com/library/ff400223.aspx). |
| 랩 환경을 사용하여 Microsoft Test Manager에서 자동화된 테스트 원격 실행 | 지금은 이 시나리오에 대한 대체 방법이 없습니다. 빌드 및 릴리스 정의(XAML 빌드가 아님)에서 기능 테스트 실행 작업을 사용하여 테스트를 원격으로 실행하는 것이 좋습니다. |
| Visual Studio에서 원격 테스트를 실행하는 개발자 | 더 이상 지원되지 않습니다. |

<!-- ENDSECTION -->

## <a name="see-also"></a>참고 항목

* [테스트 설정을 사용하여 컴퓨터 설정 및 진단 정보 수집](https://msdn.microsoft.com/library/dd286743%28v=vs.140%29.aspx)

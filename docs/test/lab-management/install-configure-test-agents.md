---
title: "Visual Studio에서 테스트 에이전트 설치 및 구성 | Microsoft Docs"
ms.date: 03/02/2018
ms.technology: vs-devops-test
ms.topic: article
helpviewer_keywords:
- configure test agents, test lab
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 16e29676ec67bc3fd22313debe70ba8dbcd7fd76
ms.sourcegitcommit: 39c525ec200c6c4ea94815567b3fad7ab14fb7b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2018
---
# <a name="install-and-configure-test-agents"></a>테스트 에이전트 설치 및 구성

Visual Studio 및 VSTS(Visual Studio Team Services) 또는 TFS(Team Foundation Server)를 사용하는 테스트 시나리오의 경우 테스트 컨트롤러가 필요하지 않습니다. Visual Studio용 에이전트가 VSTS 또는 TFS와 통신하여 오케스트레이션을 처리합니다. VSTS 또는 TFS에서 빌드 및 릴리스 워크플로에 대해 연속 테스트를 실행하는 시나리오가 가능합니다.

Lab Management 대신 [Build 또는 Release Management](use-build-or-rm-instead-of-lab-management.md)를 사용하는 것이 더 좋을 수도 있습니다.

## <a name="system-requirements"></a>시스템 요구 사항

| 항목 | 요구 사항 |
| ---- | ------------ |
| **에이전트** | Windows 10<br />Windows 8, Windows 8.1<br />Windows 7 서비스 팩 1<br />Windows XP 서비스 팩 3<br />Windows Server 2012, Windows Server 2012 R2<br />Windows Server 2008 릴리스 2, 서비스 팩 1 |
| **컨트롤러** | Windows 10<br />Windows 8, Windows 8.1<br />Windows 7 서비스 팩 1<br />Windows Server 2012, Windows Server 2012 R2<br />Windows Server 2008 릴리스 2, 서비스 팩 1 |
| **.NET Framework** | .NET Framework 4.5 |

## <a name="install-the-test-controller-and-test-agents"></a>테스트 컨트롤러 및 테스트 에이전트 설치

[visualstudio.com](https://www.visualstudio.com/downloads/?q=agents)에서 Agents for Visual Studio 2017을 다운로드할 수 있습니다. *Agents for Visual Studio 2017*을 찾은 다음, *에이전트* 또는 *컨트롤러*를 선택합니다. [이전 다운로드](https://www.visualstudio.com/vs/older-downloads/) 페이지에서 Agents for Visual Studio 2015 및 Agents for Visual Studio 2013을 다운로드할 수 있습니다.

이러한 설치 관리자는 가상 머신에 쉽게 설치할 수 있도록 ISO 파일로 제공됩니다.

## <a name="compatible-versions-of-tfs-microsoft-test-manager-the-test-controller-and-test-agent"></a>TFS, Microsoft Test Manager, 테스트 컨트롤러 및 테스트 에이전트의 호환되는 버전

다음 표에 따라 서로 다른 버전의 TFS, MTM(Microsoft Test Manager), 테스트 컨트롤러 및 테스트 에이전트를 함께 사용할 수 있습니다.

| TFS | MTM(랩 센터 포함) | 컨트롤러 | 에이전트 |
| --- | -------------------------------------- | ---------- | ----- |
| 2017: 2015 이상 설치에서 업그레이드 | 2017 | 2017 | 2017 |
| 2017: 2015 이상 설치에서 업그레이드 | 2017 | 2013 업데이트 5 | 2013 업데이트 5 |
| 2017: 2015 이상 설치에서 업그레이드 | 2015 | 2013 업데이트 5 | 2013 업데이트 5 |
| 2015: 2013에서 업그레이드 | 2013 | 2013 |2013 |
| 2015: 새로 설치 | 2013 | 2013 | 2013 |
| 2015: 2013 이상 설치에서 업그레이드 | 2015 | 2013 | 2013 |
| 2013 | 2015 | 2013 | 2013 |

## <a name="upgrade-from-visual-studio-2013-test-agents"></a>Visual Studio 2013 테스트 에이전트에서 업그레이드

자동화된 모든 새 테스트 시나리오에서 Agents for Visual Studio를 사용하는 것이 좋습니다. 빌드 정의에서 ‘테스트 에이전트 배포’ 작업을 사용하여 컴퓨터에 테스트 에이전트를 다운로드하고 설치할 수 있습니다.

다음 표에서는 Agents for Visual Studio 2013에서 지원되는 시나리오와 TFS(Team Foundation Server) 2015 및 VSTS에 대한 대체 방법을 보여줍니다.

| Agents for Visual Studio 2013에서 지원되는 시나리오 | TFS 및 VSTS의 대체 방법 |
| --- | --- |
| Visual Studio의 빌드-배포-테스트 워크플로 | 사용자는 TFS의 빌드, 배포 및 테스트 시나리오에 [빌드 정의](/vsts/build-release/)(XAML 빌드가 아님)를 사용할 수 있습니다. |
| 온-프레미스 원격 컴퓨터를 사용한 부하 테스트(성능 테스트) | Test Controller 및 Test Agents 2013 업데이트 5를 사용하여 온-프레미스로 부하 테스트를 실행할 수 있습니다. 자세한 내용은 [부하 테스트에서 테스트 컨트롤러 및 테스트 에이전트 사용](https://msdn.microsoft.com/library/ff400223.aspx)을 참조하세요. |
| 랩 환경을 사용하여 Microsoft Test Manager에서 자동화된 테스트 원격 실행 | 지금은 이 시나리오에 대한 대체 방법이 없습니다. 빌드 및 릴리스 정의(XAML 빌드가 아님)에서 기능 테스트 실행 작업을 사용하여 테스트를 원격으로 실행하는 것이 좋습니다. |
| Visual Studio에서 원격 테스트를 실행하는 개발자 | 더 이상 지원되지 않습니다. |

## <a name="see-also"></a>참고 항목

* [컴퓨터 설정 및 진단 정보 수집](https://msdn.microsoft.com/library/dd286743%28v=vs.140%29.aspx)

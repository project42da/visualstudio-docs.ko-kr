---
title: "Devops에 랩 환경 사용 | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- lab environment, test lab
ms.assetid: b435eb39-dc7c-46fa-a91b-6e6dd614f01c
caps.latest.revision: 56
ms.author: douge
manager: douge
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 45d36934cf1c46902cac566203cddf4a118b7fe4
ms.openlocfilehash: 29b1343159cb91d3d5e4b9769c4103cc3565f986
ms.contentlocale: ko-kr
ms.lasthandoff: 06/02/2017

---
# <a name="use-a-lab-environment-for-your-devops"></a>Devops에 랩 환경 사용

랩 환경은 응용 프로그램을 개발하고 테스트하는 데 사용할 수 있는 가상 및 물리적 컴퓨터의 컬렉션입니다. 랩 환경은 워크스테이션, 웹 서버 및 데이터베이스 서버 같은 다중 계층 응용 프로그램을 테스트하는 데 필요한 여러 역할을 포함할 수 있습니다. 또한 랩 환경에서 빌드-배포-테스트 워크플로를 사용하여 응용 프로그램에 자동화된 테스트를 빌드, 배포 및 실행하는 프로세스를 자동화할 수 있습니다.

* **테스트 계획을 사용하여 자동화된 테스트 실행** − *테스트 계획*이라는 자동화된 테스트 컬렉션을 실행하고 진행률을 확인할 수 있습니다.  
  
* **빌드-배포-테스트 워크플로 사용** − 빌드-배포-테스트 워크플로를 사용하여 다계층 응용 프로그램을 자동으로 테스트할 수 있습니다. 예를 들어 빌드를 시작하고 빌드 파일을 랩 환경의 적절한 컴퓨터에 배포한 다음 자동화된 테스트를 수행하는 것이 일반적인 워크플로입니다. 또한 워크플로를 특정 간격마다 실행되도록 예약할 수 있습니다.  
  
* **수동 테스트 중에도 모든 컴퓨터의 진단 데이터 수집** − 여러 컴퓨터에서 진단 데이터를 동시에 수집할 수 있습니다. 예를 들어 단일 테스트 실행 도중 웹 서버, 데이터베이스 서버 및 클라이언트에서 IntelliTrace, 테스트 영향 및 다양한 형태의 데이터를 수집할 수 있습니다.  
  
다음은 랩 환경의 일반적인 형식 예입니다.  
  
| 토폴로지 | 설명 |  
|---|---|  
|![서버 전용 토폴로지](../media/topology_backend.png)| 이 랩 환경에는 서버 응용 프로그램에 대한 수동 테스트를 실행하는 데 주로 사용되는 *서버 토폴로지*가 있습니다. 이 토폴로지에서는 테스터가 자체 클라이언트 컴퓨터를 사용하여 환경의 버그를 확인할 수 있습니다. 백 엔드 토폴로지의 랩 환경에는 서버만 포함됩니다. 이 형식의 토폴로지를 사용할 경우에는 일반적으로, 환경에 포함되어 있지 않은 클라이언트 컴퓨터를 사용하여 랩 환경의 서버와 연결합니다.|  
|![클라우드 랩 환경](../media/topology_cloud.png)| 이 랩 환경에서는 _서버 토폴로지_와 비슷한 기능과 특징을 제공하지만 로컬 환경에서 실행되는 실제 또는 가상 컴퓨터에 대한 요구 사항이 제거되므로 설정 시간이 단축되고, 유지 관리가 간소화되고, 비용이 최소화됩니다. Microsoft Azure와 같은 클라우드 환경에서는 여러 웹 사이트와 가상 컴퓨터를 사용자 지정 네트워킹과 함께 설정하는 것이 빠르고 간편합니다. [자세한 내용](#usebandrm).|  
|![클라이언트 서버 랩 환경](../media/topology_clientserver.png)| 이 랩 환경에는 서버 및 클라이언트 구성 요소를 갖는 응용 프로그램을 테스트하는 데 주로 사용되는 *클라이언트-서버 토폴로지*가 있습니다. 클라이언트/서버 토폴로지에서는 응용 프로그램을 테스트하는 데 사용되는 모든 서버 및 클라이언트 컴퓨터가 랩 환경에 있습니다. 이 토폴로지를 사용하면 테스트에 영향을 주는 모든 컴퓨터에서 테스트 데이터를 수집할 수 있습니다.|  
  
[Video: Managing lab environments for testing](http://go.microsoft.com/fwlink/?LinkID=252614)(비디오: 테스트를 위한 랩 환경 관리)을 참조하세요.  
  
랩 환경을 설정하는 일반적인 방법은 다음과 같습니다. 
  
* **[Team Services 또는 Team Foundation Server의 빌드 &amp; 릴리스](#usebandrm)와 함께 클라우드 사용**

* **[Microsoft Test Manager의 Visual Studio Lab Management 기능 사용](#usemtmlm)**

<a name="usebandrm"></a>
## <a name="use-the-cloud-with-team-services-or-team-foundation-server-build-amp-release"></a>Team Services 또는 Team Foundation Server의 빌드 &amp; 릴리스와 함께 클라우드 사용

Visual Studio Team Services 및 TFS(Team Foundation Server)의 [빌드 &amp; 릴리스](https://www.visualstudio.com/team-services/continuous-integration/) 기능을 사용하여 자동화된 테스트 및 빌드-배포-테스트 자동화를 수행할 수 있습니다. 몇 가지 이점은 다음과 같습니다.

* 빌드 컨트롤러 또는 테스트 컨트롤러가 필요하지 않습니다.
* 테스트 에이전트는 빌드 또는 릴리스에 포함된 작업을 통해 설치됩니다.
* 배포 단계를 쉽게 사용자 지정할 수 있습니다. 더 이상 단일 스크립트를 사용하도록 제한되지 않습니다. Visual Studio Marketplace 및 제품에서 제공되는 많은 작업을 활용할 수도 있습니다.
* 테스트 도구 모음을 유지 관리할 필요가 없습니다. 이진 파일에서 직접 테스트를 실행할 수 있습니다.
* 각 빌드 또는 릴리스 내에서 실행된 테스트에 대한 더 풍부한 인라인 보고 환경을 얻을 수 있습니다.
* 각 환경에서 현재 배포 및 테스트되는 자산(릴리스, 빌드, 작업 항목, 커밋)을 추적할 수 있습니다.
* 자동화를 사용자 지정하고 확장하여 여러 테스트 환경뿐 아니라 프로덕션 환경에도 쉽게 배포할 수 있습니다.
* 체크 인 또는 커밋이 있을 때마다 또는 매일 특정 시간에 발생하도록 자동화를 예약할 수 있습니다.

[추가 정보](use-build-or-rm-instead-of-lab-management.md).

<a name="usemtmlm"></a>
## <a name="use-the-visual-studio-lab-management-features-of-microsoft-test-manager"></a>Microsoft Test Manager의 Visual Studio Lab Management 기능 사용

Visual Studio Enterprise 또는 Visual Studio Test Professional을 사용할 때 Microsoft Test Manager의 Visual Studio Lab Management 기능을 사용하여 랩 환경을 만들고 관리할 수 있습니다.

Lab Management는 환경의 각 컴퓨터에 테스트 에이전트를 자동으로 설치합니다.  
  
Lab Management를 SCVMM(System Center Virtual Machine Manager)과 함께 사용할 경우 랩 환경을 통해 다음과 같은 혜택도 누릴 수 있습니다.  
  
* **컴퓨터 구성 신속 재현** − 일반적인 프로덕션 환경을 다시 만들도록 구성되어 있는 가상 컴퓨터의 컬렉션을 저장할 수 있습니다. 그런 다음 저장 환경의 새 복사본에서 각 테스트 실행을 수행할 수 있습니다.  
  
* **정확한 버그 상태 재현** – 테스트 실행에 실패하면 랩 환경 상태의 복사본을 저장한 다음 빌드 결과나 작업 항목을 통해 액세스할 수 있습니다.  
  
* **여러 랩 환경 복사본을 동시에 실행** – 이름 충돌 없이, 여러 랩 환경 복사본을 동시에 실행할 수 있습니다.  
  
### <a name="standard-environments-and-scvmm-environments"></a>표준 환경 및 SCVMM 환경

Visual Studio Lab Management를 사용하여 만들 수 있는 랩 환경에는 **표준 환경**과 **SCVMM 환경** 두 가지가 있습니다.
하지만 이러한 환경의 기능은 각각 다릅니다.  
  
> **참고**: Lab Management는 SCVMM 2016을 지원하지 **않습니다**. SCVMM에 대한 자세한 내용은 [Virtual Machine Manager](http://go.microsoft.com/fwlink/?LinkId=226332)를 참조하세요. 
  
**표준 환경:** 가상 컴퓨터와 물리적 컴퓨터가 혼합되어 포함될 수 있습니다. 타사 가상화 프레임워크에서 관리되는 표준 환경에 가상 컴퓨터를 추가할 수도 있습니다. 또한 표준 환경에는 SCVMM 서버와 같은 추가 서버 리소스가 필요하지 않습니다.  
  
**SCVMM 환경:** SCVMM(System Center Virtual Machine Manager)이 관리하는 가상 컴퓨터만 포함될 수 있으므로 SCVMM 환경의 가상 컴퓨터는 Hyper-V 가상화 프레임워크에서만 실행할 수 있습니다. 하지만 SCVMM 환경은 표준 환경에서는 지원되지 않는 다음과 같은 자동화 및 관리 기능을 제공합니다.  
  
- **환경 스냅숏:** 환경 스냅숏에는 랩 환경의 상태가 포함되어 있으므로 새로운 환경을 신속하게 복원하거나 수정된 환경의 상태를 저장할 수 있습니다. 또한 빌드-배포-테스트 워크플로를 사용하여 환경 스냅숏에 대한 저장 및 복원 프로세스를 자동화할 수 있습니다.  
  
- **저장 환경:** SCVMM 환경의 복사본을 저장한 다음 해당 환경의 복사본 여러 개를 배포할 수 있습니다.  
  
- **네트워크 격리:** 네트워크 격리를 사용하면 SCVMM 환경에 대한 동일한 복사본 여러 개를 컴퓨터 이름 충돌 없이 동시에 실행할 수 있습니다.  
  
- **가상 컴퓨터 템플릿:** 가상 컴퓨터 템플릿은 이름과 기타 식별자가 제거된 가상 컴퓨터입니다. VM 템플릿이 SCVMM 환경에 배포될 때 Microsoft Test Manager가 새 식별자를 생성합니다. 이를 통해, 여러 가상 컴퓨터 복사본을 동일한 환경 또는 여러 환경에 배포한 다음 동시에 실행할 수 있습니다.  
  
- **저장된 가상 컴퓨터:** 팀 프로젝트 라이브러리에 저장되고 고유한 식별자를 포함하는 가상 컴퓨터입니다.  
  
이러한 기능에 대한 자세한 내용은 [SCVMM 환경을 만들고 관리하기 위한 지침](https://msdn.microsoft.com/en-gb/library/ee830480.aspx)을 참조하세요.  
  
표준 환경과 SCVMM 환경에서는 여러 가지 동일한 기능이 지원됩니다. 하지만 고려해야 할 몇 가지 중요한 차이점이 있습니다. 다음 테이블에서는 표준 환경과 SCVMM 환경에서 지원되는 기능을 비교할 수 있습니다.  
  
|기능|SCVMM 환경|표준 환경|  
|----------------|------------------------|---------------------------|  
|**테스트**|||  
|수동 테스트 실행|지원됨|지원됨|  
|코딩된 UI 및 기타 자동화된 테스트 실행|지원됨|지원됨|  
|진단 어댑터를 사용하여 다양한 버그를 파일에 기록|지원됨|지원됨|  
|**빌드 배포**|||  
|자동화된 빌드-배포-테스트 워크플로|지원됨|지원됨|  
|**환경 만들기 및 관리**|||  
|가상 컴퓨터 이외에 물리적 컴퓨터 사용|지원 안 함|지원됨|  
|타사 가상 컴퓨터 사용|지원 안 함|지원됨|  
|랩 환경의 컴퓨터에 테스트 에이전트 자동 설치|지원됨|지원됨|  
|환경 스냅숏을 사용하여 랩 환경의 상태를 저장 및 배포|지원됨|지원 안 함|  
|VM 템플릿을 통해 랩 환경 만들기|지원됨|지원 안 함|  
|환경 시작/중지/스냅숏|지원됨|지원 안 함|  
|환경 뷰어를 사용하여 환경에 연결|지원됨|지원됨|  
|네트워크 격리를 사용하여 여러 환경 복사본을 동시에 실행|지원됨|지원 안 함|  
  
### <a name="lab-management-concepts"></a>Lab Management 개념

계속하기 전에 숙지하고 있어야 할 몇 가지 개념이 다음에 나와 있습니다.  
  
|용어|설명|  
|----------|-----------------|  
|랩 센터|랩 환경을 만들고 관리하는 Microsoft Test Manager 영역입니다.|  
|팀 프로젝트 랩|이 환경에 연결하여 가상 컴퓨터를 실행할 수 있도록 설정되어 있는 랩 환경 컬렉션입니다.|  
|팀 프로젝트 라이브러리|팀 프로젝트의 호스트 그룹에 가져온 저장된 가상 컴퓨터, 템플릿 및 저장된 랩 환경의 저장소입니다. 라이브러리의 항목은 SCVMM 환경에 사용할 수 있지만 표준 환경에 직접 추가할 수 없습니다. 라이브러리의 항목을 실행할 수 없으며 대신, 새 환경을 배포하는 데 사용할 수 있습니다.|  
|배포된 환경|팀 프로젝트 랩에 배포되어 있는 랩 환경으로서 이 환경에 연결하여 해당 환경의 컴퓨터를 실행할 수 있습니다.|  

#### <a name="related-topics"></a>관련 항목

* [랩 계획](https://msdn.microsoft.com/library/ff756575%28v=vs.140%29.aspx) 
* [Lab Management 구성 및 관리](https://msdn.microsoft.com/library/dd936084%28v=vs.140%29.aspx) 
* [SCVMM 환경에 대한 Lab Management 구성](https://msdn.microsoft.com/library/dd380687%28v=vs.140%29.aspx) 
* [SCVMM 2008 R2를 SCVMM 2012로 업그레이드](upgrade-scvmm-2008-r2-scvmm-2012.md) 
* [사용 권한 관리](https://msdn.microsoft.com/library/dd380760%28v=vs.140%29.aspx) 
* [설정 변경](https://msdn.microsoft.com/library/ee704508%28v=vs.140%29.aspx) 
* [문제 해결](https://msdn.microsoft.com/library/ee853230%28v=vs.140%29.aspx)
  
### <a name="set-up-environments"></a>환경 설정

* [빌드 &amp; 릴리스 클라우드 환경](use-build-or-rm-instead-of-lab-management.md)
* [표준 랩 환경](https://msdn.microsoft.com/en-gb/library/ee390842.aspx)
* [SCVMM(가상) 환경](https://msdn.microsoft.com/en-gb/library/ee943322.aspx)
* [네트워크 격리 환경 만들기 및 사용](https://msdn.microsoft.com/en-gb/library/ee518924.aspx)
  
## <a name="see-also"></a>참고 항목
  
* [테스트 에이전트 설치 및 구성](install-configure-test-agents.md)
* [Visual Studio Lab Management Guide](http://go.microsoft.com/fwlink/?LinkID=230951)(Visual Studio Lab Management 가이드)  
* [Managing lab environments for testing](http://go.microsoft.com/fwlink/?LinkID=252614)(테스트를 위한 랩 환경 관리)  
* [Visual Studio devops + Team Foundation Server 블로그](http://go.microsoft.com/fwlink/?LinkID=254496)  

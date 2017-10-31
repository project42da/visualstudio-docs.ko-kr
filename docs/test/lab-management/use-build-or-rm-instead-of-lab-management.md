---
title: "자동화된 테스트를 위해 Build 또는 Release Management 사용 | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- automated testing, lab management, test lab
ms.assetid: F34B0D19-B430-4C01-B402-62A861007E71
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
ms.openlocfilehash: 77a0339e1aae3036990f0d9d133a1fcb68844486
ms.contentlocale: ko-kr
ms.lasthandoff: 06/02/2017

---
# <a name="use-build-and-release-management-instead-of-lab-management-for-automated-testing"></a>자동화된 테스트를 위해 Lab Management 대신 Build 및 Release Management 사용

자동화된 테스트 또는 빌드-배포-테스트 자동화에 MTM(Microsoft Test Manager) 및 Lab Management를 사용할 경우 이 항목에서는 Visual Studio Team Services 및 TFS(Team Foundation Server)의 [빌드 &amp; 릴리스](https://www.visualstudio.com/team-services/continuous-integration/) 기능을 사용하여 동일한 목표를 달성하는 방법을 설명합니다.

* [빌드-배포-테스트 자동화](#bdtautomation)

* [SCVMM 환경의 셀프 서비스 관리](#managescvmm)

Build 및 Release Management는 네트워크 격리 SCVMM 환경의 셀프 서비스 만들기를 지원하지 않고 이후에도 이 지원을 제공할 계획이 없습니다. 그러나 몇 가지 [제안된 대체 방법](#isolatedenvir)이 있습니다.

<a name="bdtautomation"></a>
## <a name="build-deploy-test-automation"></a>빌드-배포-테스트 자동화

MTM 및 Lab Management는 XAML 빌드 정의를 사용하여 응용 프로그램의 빌드, 배포 및 테스트를 자동화합니다.
XAML 빌드는 랩 환경, 테스트 도구 모음 및 테스트 설정과 같이 MTM에서 만들어진 다양한 생성자와 빌드 컨트롤러, 빌드 에이전트, 테스트 컨트롤러, 테스트 에이전트 등의 다양한 인프라를 사용하여 이 목표를 달성합니다. TFS 및 Team Services의 Build 또는 Release Management를 사용하여 몇 가지 추가 단계로 동일한 목적을 달성할 수 있습니다.

| 단계 | XAML 빌드 사용 | Build 또는 Release Management 사용 |
|-------|----------------------|-----------------|
| 빌드를 배포하고 테스트를 실행할 컴퓨터를 식별합니다. | 해당 컴퓨터가 포함된 MTM의 표준 랩 환경을 만듭니다. | N/A |
| 실행할 테스트를 식별합니다. | MTM에서 테스트 도구 모음을 만들고, 테스트 사례를 만들고, 각 테스트 사례와 자동화를 연결합니다. 테스트를 실행할 랩 환경에서 컴퓨터의 역할을 식별하는 테스트 설정을 MTM에서 만듭니다. | 테스트 계획을 통해 테스트를 관리하려면 같은 방식으로 MTM에서 자동화된 테스트 도구 모음을 만듭니다. 또는 빌드에서 생성된 테스트 이진 파일에서 직접 테스트를 실행하려면 이 단계를 건너뛸 수 있습니다. 어느 경우에도 테스트 설정을 만들 필요가 없습니다. |
| 배포 및 테스트를 자동화합니다. | LabDefaultTemplate.*.xaml을 사용하여 XAML 빌드 정의를 만듭니다. 빌드 정의에서 빌드, 테스트 도구 모음 및 랩 환경을 지정합니다. | 단일 환경을 사용하여 [빌드 정의 또는 릴리스 정의](https://www.visualstudio.com/team-services/continuous-integration/)를 만듭니다. 명령줄 작업을 사용하여 XAML 빌드 정의에서 동일한 배포 스크립트를 실행하고 테스트 에이전트 배포 및 기능 테스트 실행 작업을 사용하여 자동화된 테스트를 실행합니다. 컴퓨터 및 해당 자격 증명 목록을 이러한 작업의 입력으로 지정합니다. |

이 시나리오에 Build 또는 Release Management를 사용해서 얻는 몇 가지 이점은 다음과 같습니다.

* 빌드 컨트롤러 또는 테스트 컨트롤러가 필요하지 않습니다.
* 테스트 에이전트는 빌드 또는 릴리스에 포함된 작업을 통해 설치됩니다.
* 배포 단계를 쉽게 사용자 지정할 수 있습니다. 더 이상 단일 스크립트를 사용하도록 제한되지 않습니다. Visual Studio Marketplace 및 제품에서 제공되는 많은 작업을 활용할 수도 있습니다.
* 테스트 도구 모음을 유지 관리할 필요가 없습니다. 이진 파일에서 직접 테스트를 실행할 수 있습니다.
* 각 빌드 또는 릴리스 내에서 실행된 테스트에 대한 더 풍부한 인라인 보고 환경을 얻을 수 있습니다.
* 각 환경에서 현재 배포 및 테스트되는 자산(릴리스, 빌드, 작업 항목, 커밋)을 추적할 수 있습니다.
* 자동화를 사용자 지정하고 확장하여 여러 테스트 환경뿐 아니라 프로덕션 환경에도 쉽게 배포할 수 있습니다.
* 체크 인 또는 커밋이 있을 때마다 또는 매일 특정 시간에 발생하도록 자동화를 예약할 수 있습니다.

<a name="managescvmm"></a>
## <a name="self-service-management-of-scvmm-environments"></a>SCVMM 환경의 셀프 서비스 관리

[Microsoft Test Manager의 Lab Center](https://msdn.microsoft.com/library/dd997438.aspx)는 [SCVMM 서버](https://technet.microsoft.com/system-center-docs/vmm/vmm)를 사용하여 요청 시 환경을 프로비저닝하고 환경 템플릿의 라이브러리를 관리하는 기능을 지원합니다.

Lab Center의 셀프 서비스 프로비전 기능에는 두 가지 목표가 있습니다.

* 인프라를 관리하는 더 간단한 방법을 제공합니다. 예를 들어 인프라 관리를 위해 VM 및 환경 템플릿을 관리하고 서로 환경 복제본을 격리하는 개인 네트워크를 자동으로 만들었습니다.

* 팀이 테스트 및 배포 활동에서 가상 컴퓨터를 사용할 수 있는 더 간단한 방법을 제공합니다. 예를 들어 간편한 사용을 위해 팀 프로젝트 보안 모델을 통해 랩 환경에 액세스할 수 있고 테스트 시나리오에서 해당 가상 컴퓨터를 통합 사용하도록 했습니다.

그러나 [Microsoft Azure](https://azure.microsoft.com/) 및 [Microsoft Azure Stack](https://azure.microsoft.com/overview/azure-stack/)과 같은 더 다양한 공용 및 사설 클라우드 관리 시스템의 발전을 고려한다면 TFS 2017 이상에는 인프라 관리 기능의 발전이 없습니다. 대신에 해당 클라우드 인프라를 통해 관리되는 리소스의 간편한 사용에 계속 초점을 맞춥니다.

다음 표에는 Lab Center에서 작업하는 데 사용한 일반적인 활동과 SCVMM 또는 Azure(인프라 관리 활동인 경우)를 통해서나 TFS 및 Team Services(테스트 또는 배포 활동인 경우)를 통해 해당 활동을 수행하는 방법이 요약되어 있습니다.

| 단계 | Lab Center 사용 | Build 또는 Release Management 사용 |
|-------|----------------------|-----------------|
| 환경 템플릿 라이브러리를 관리합니다. | 랩 환경을 만듭니다. 가상 컴퓨터에 필요한 소프트웨어를 설치합니다. 환경을 Sysprep하고 라이브러리의 템플릿으로 저장합니다. | SCVMM 관리 콘솔을 사용하여 직접 가상 컴퓨터 템플릿 또는 서비스 템플릿을 만들고 관리합니다. Azure를 사용할 경우 [Azure Marketplace](https://azure.microsoft.com/marketplace/) 또는 [Azure 빠른 시작 템플릿](https://azure.microsoft.com/documentation/templates/)에서 미리 정의된 [Azure Resource Manager 템플릿](https://azure.microsoft.com/documentation/templates/) 중 하나를 선택합니다. |
| 랩 환경을 만듭니다. | 라이브러리에서 환경 템플릿을 선택하고 배포합니다. 가상 컴퓨터 구성을 사용자 지정하는 데 필요한 매개 변수를 제공합니다. | SCVMM 관리 콘솔을 사용하여 직접 템플릿을 기반으로 VM 또는 서비스 인스턴스를 만듭니다. Azure Portal을 사용하여 직접 리소스를 만듭니다. 또는 환경을 사용하여 릴리스 정의를 만듭니다. Azure 작업 또는 [SCVMM 통합 확장](https://marketplace.visualstudio.com/items?itemname=ms-vscs-rm.scvmmapp)의 작업을 사용하여 새 가상 컴퓨터를 만듭니다. 이 정의의 새 릴리스를 만드는 것은 Lab Center에서 새 환경을 만드는 것과 같습니다. |
| 컴퓨터에 연결합니다. | 환경 뷰어에서 랩 환경을 엽니다. | SCVMM 관리 콘솔을 사용하여 직접 가상 컴퓨터에 연결합니다. 또는 가상 컴퓨터의 IP 주소 또는 DNS 이름을 사용하여 원격 데스크톱 세션을 엽니다. |
| 환경 검사점을 만들거나 환경을 새로운 검사점으로 복원합니다. | 환경 뷰어에서 랩 환경을 엽니다. 검사점을 만들거나 이전 검사점으로 복원하는 옵션을 선택합니다. | SCVMM 관리 콘솔을 사용하여 컴퓨터에서 이러한 작업을 수행합니다. 또는 더 큰 자동화의 일부로 이러한 단계를 수행하려면 [SCVMM 통합 확장](https://marketplace.visualstudio.com/items?itemname=ms-vscs-rm.scvmmapp)의 검사점 작업을 환경의 일부로 릴리스 정의에 포함합니다. |

<a name="isolatedenvir"></a>
## <a name="self-service-creation-of-network-isolated-environments"></a>네트워크 격리 환경의 셀프 서비스 만들기

네트워크 격리 랩 환경은 네트워크 충돌 없이 안전하게 복제할 수 있는 SCVMM 가상 컴퓨터 그룹입니다. 이 작업은 네트워크 인터페이스 집합을 사용하여 개인 네트워크에서 가상 컴퓨터를 구성하고 또 다른 네트워크 인터페이스 카드 집합을 사용하여 공용 네트워크에서 가상 컴퓨터를 구성한 일련의 명령을 사용하여 MTM에서 수행되었습니다.

[Microsoft Azure](https://azure.microsoft.com/) 및 [Microsoft Azure Stack](https://azure.microsoft.com/overview/azure-stack/)과 같은 다양한 공용 및 사설 클라우드 관리 시스템이 발전하면서 사용자가 직접 비슷한 기능을 위해 클라우드 관리 도구를 더 많이 사용할 수 있습니다. Build 및 Release Management에는 이 목표를 달성할 수 있는 방법이 없습니다.

네트워크 격리가 필요한 경우 다음 대체 방법을 고려하는 것이 좋습니다.

* 네트워크 격리의 한 가지 목적은 여러 복제본의 구성을 간소화하는 것이었습니다. 각 복제본이 원본의 정확한 복제본이므로 컴퓨터 이름 및 구성 설정이 있는 그대로 보존되고, 이에 따라 새 환경을 쉽게 설정할 수 있습니다. 그러나 응용 프로그램이 최종적으로 배포되는 방법이 동일하지 않기 때문에 수명 주기에서 나중에 동일한 이점으로 인해 문제가 발생합니다. **대신에** 프로덕션을 설정하는 것과 같은 방법으로 새 환경을 설정해 보고 네트워크 격리 사용을 피하세요.

* 테스트에 필요한 경우 [Microsoft Azure](https://azure.microsoft.com/)와 같은 공용 클라우드 인프라를 사용합니다. 간편하게 [Azure Marketplace](https://azure.microsoft.com/marketplace/) 또는 [Azure 빠른 시작 템플릿](https://azure.microsoft.com/documentation/templates/)의 [Azure Resource Manager 템플릿](https://azure.microsoft.com/documentation/templates/)을 사용하여 개인 네트워크를 통해 연결되고 프록시 또는 ‘jumpbox’를 사용하여 공용 네트워크에만 표시되는 가상 컴퓨터 그룹을 설정할 수 있습니다.

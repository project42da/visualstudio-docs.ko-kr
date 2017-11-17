---
title: "배포를 다른 사용자에 대 한 ClickOnce 응용 프로그램 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- preserved branding information
- useManifestForTrust element
- customer deployments [ClickOnce]
- multiple ClickOnce deployment and branding
- ClickOnce applications, previous .NET Framework versions
- application manifests [ClickOnce]
- <useManifestForTrust> element
- manifests [ClickOnce]
- trust applications, ClickOnce
- ClickOnce applications, deployed by others
- ClickOnce applications, previous .NET Framework
ms.assetid: d20766c7-4ef3-45ab-8aa0-3f15b61eccaa
caps.latest.revision: "10"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 0ca5bb824cbe4e37db241aba956f9f6bf91d18cd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="creating-clickonce-applications-for-others-to-deploy"></a>다른 사용자가 배포할 수 있는 ClickOnce 응용 프로그램 만들기
ClickOnce 배포를 만들고 있는 일부 개발자는 자체 응용 프로그램을 배포 하도록 계획 합니다. 그 중 대부분 방금 ClickOnce를 사용 하 여 해당 응용 프로그램을 패키지 하 대기업 등의 고객에 게 파일 전달 합니다. 고객 워크시트가 네트워크에서 응용 프로그램을 호스트 하는 일을 담당 합니다. 이 항목에서는 버전의.NET Framework 버전 3.5 이전에서는 이러한 배포의 문제 중 일부에 대해 설명 합니다. .NET Framework 3.5의 새로운 "매니페스트 사용 하 여 신뢰에 대 한" 기능을 사용 하 여 제공 하는 새 솔루션에 설명 합니다. 마지막으로, 이전 버전의.NET Framework를 계속 사용 하는 고객에 대 한 ClickOnce 배포를 만들기 위한 권장된 사항을 문으로 끝납니다.  
  
## <a name="issues-involved-in-creating-deployments-for-customers"></a>고객에 대 한 배포 만들기에 관련 된 문제  
 몇 가지 문제는 계획 배포를 고객에 게 제공 하는 경우 발생 합니다. 첫 번째 문제는 관련 된 코드 서명입니다. 네트워크에서 배포 하려면 배포 매니페스트 및 응용 프로그램 매니페스트는 ClickOnce 배포의 둘 다 서명 되어야 합니다는 디지털 인증서로. 이 매니페스트에 서명 하는 경우 개발자 인증서 또는 고객의 인증서를 사용할 것인지에 대 한 문제를 발생 시킵니다.  
  
 ClickOnce 응용 프로그램의 id는 배포 매니페스트의 디지털 서명을 기준으로 인증서를 사용 하 여 질문은 매우 중요 합니다. 배포 매니페스트에 서명 하는 개발자, 하는 경우 고객은 큰 회사는 회사의 여러 부서 응용 프로그램의 사용자 지정된 된 버전을 배포 하는 경우 충돌이 발생할 수 있습니다.  
  
 예를 들어, Adventure Works에는 재무 부서와 인사 관리 부서의 합니다. 두 부서에는 SQL 데이터베이스에 저장 된 데이터에서 보고서를 생성 하는 Microsoft Corporation에서 ClickOnce 응용 프로그램을 라이선스입니다. Microsoft에서 해당 데이터에 대 한 사용자 지정 된 응용 프로그램의 버전과 각 부서를 제공 합니다. 응용 프로그램은 같은 Authenticode 인증서로 서명 되어 사용자가 두 응용 프로그램을 사용 하려고 하면 오류가 발생, ClickOnce 첫 번째와 동일한 것으로 두 번째 응용 프로그램에 대 한 것 처럼 합니다. 이 경우 고객이 예기치 않은 결과가 응용 프로그램에 의해 로컬에 저장 된 모든 데이터의 손실 되는 발생할 수 있습니다.  
  
 : 코드 서명 하는 또 다른 문제는 관련 된 `deploymentProvider` 배포 매니페스트에서 ClickOnce 응용 프로그램 업데이트를 검색 하는 위치를 알려 주는 요소입니다. 이 요소에 서명 하기 전에 배포 매니페스트에 추가할 수 있습니다. 이 요소는 나중에 추가 되 면 배포 매니페스트에 다시 서명 해야 합니다.  
  
### <a name="requiring-the-customer-to-sign-the-deployment-manifest"></a>배포 매니페스트에 서명 하는 고객 요구  
 개발자 기호 응용 프로그램 매니페스트를이 오류를 고유 하지 않은 배포의이 문제를 해결 하 고 고객 배포 매니페스트에 서명 합니다. 이 방법은 작동 하는 동안에 다른 문제가 소개 합니다. Authenticode 인증서 보호 되는 자산을 유지 해야 하는 이후 고객 배포에 서명 하려면 개발자에 게 인증서를 방금 제공할 수 없습니다. 고객 배포 매니페스트 직접.NET Framework SDK와 함께 자유롭게 사용할 수 있는 도구를 사용 하 여를 서명 하는 동안이 하거나 처리할 수 있도록 수 있는 고객은 기술적 지식이 해야 합니다. 이 경우 일반적으로 개발자 응용 프로그램, 웹 사이트 또는 다른 메커니즘 고객은 서명을 위해 응용 프로그램의 버전을 제출할 수를 만듭니다.  
  
### <a name="the-impact-of-customer-signing-on-clickonce-application-security"></a>ClickOnce 응용 프로그램 보안에 서명 하는 고객의 영향  
 개발자와 고객 고객이 응용 프로그램 매니페스트를 서명 해야 동의 하는 경우에이 신뢰할 수 있는 응용 프로그램 배포에 적용 될 때에 특히 응용 프로그램의 id를 둘러싸고 있는 다른 문제가 발생 합니다. (이 기능에 대 한 자세한 내용은 참조 [신뢰할 수 있는 응용 프로그램 배포 개요](../deployment/trusted-application-deployment-overview.md).) 예를 들어 Adventure Works Microsoft Corporation가 제공 하는 모든 응용 프로그램 완전 신뢰로 실행 되도록 해당 클라이언트 컴퓨터를 구성 하려고 합니다. 가 배포 매니페스트에 서명 하는 Adventure Works, ClickOnce 응용 프로그램의 신뢰 수준을 확인 하려면 Adventure 작업 보안 서명을 사용 합니다.  
  
## <a name="creating-customer-deployments-by-using-application-manifest-for-trust"></a>신뢰에 대 한 응용 프로그램 매니페스트를 사용 하 여 고객 배포 만들기  
 .NET Framework 3.5에서 ClickOnce 매니페스트를 서명 해야 하는 방법의 시나리오에 개발자와 고객이 새 솔루션을 제공 하는 새로운 기능을 포함 합니다. ClickOnce 응용 프로그램 매니페스트 라는 새로운 요소를 지원 `<useManifestForTrust>` 수 있도록 하는 개발자 응용 프로그램 매니페스트의 디지털 서명을 어떤를 신뢰 결정을 만드는 데 사용 해야 합니다. 개발자 ClickOnce 패키징 도구를 사용 하 여-Visual Studio, Mage.exe 및 MageUI.exe 등-응용 프로그램 매니페스트에서이 요소를 포함 하도록으로 매니페스트에 게시자 이름 및 응용 프로그램의 이름을 모두 포함 합니다.  
  
 사용 하는 경우 `<useManifestForTrust>`, 배포 매니페스트는 인증 기관에서 발급 된 Authenticode 인증서로 서명할 필요가 없습니다. 대신,으로 자체 서명 된 인증서로 서명할 수 있습니다. 자체 서명 된 인증서 표준.NET Framework SDK 도구를 사용 하 여 고객 또는 개발자 중 하나에서 생성 되며 그런 다음 표준 ClickOnce 배포 도구를 사용 하 여 배포 매니페스트에 적용 합니다. 자세한 내용은 참조 [MakeCert](https://msdn.microsoft.com/library/windows/desktop/aa386968.aspx)합니다.  
  
 배포 매니페스트에 대 한 자체 서명 된 인증서를 사용 하 여 다양 한 이점이 있습니다. 자신의 Authenticode 인증서를 만들거나 가져와야 하는 고객에 대 한 필요성을 제거 하 여 `<useManifestForTrust>` 개발자가 응용 프로그램에 고유한 브랜드 id를 유지 관리할 수 있도록 허용 하면서 고객에 대 한 배포를 간소화 합니다. 결과 서명 된 배포를 더 안전 하 고 고유한 응용 프로그램 id의 집합입니다. 이렇게 하면 여러 고객에 게 동일한 응용 프로그램 배포에서 발생할 수 있는 충돌을 가능성이 없습니다.  
  
 ClickOnce 배포를 만드는 방법에 대 한 단계별 정보 `<useManifestForTrust>` 참조 활성화 [연습: ClickOnce 응용 프로그램 해당 않습니다 하지 필요한 항목을 수동으로 배포 하 고 해당 유지 브랜딩 정보](../deployment/walkthrough-manually-deploying-a-clickonce-application-that-does-not-require-re-signing-and-that-preserves-branding-information.md).  
  
### <a name="how-application-manifest-for-trust-works-at-runtime"></a>런타임 시 신뢰 작동에 대 한 응용 프로그램 매니페스트  
 런타임에 응용 프로그램 매니페스트를 사용 하 여 신뢰에 대 한의 작동 방식을 보다 잘 이해 하려면 다음 예제를 살펴보십시오. .NET Framework 3.5를 대상으로 하는 ClickOnce 응용 프로그램은 Microsoft에서 생성 됩니다. 사용 하 여 응용 프로그램 매니페스트는 `<useManifestForTrust>` 요소 Microsoft에서 서명 됩니다. Adventure Works 자체 서명 된 인증서를 사용 하 여 배포 매니페스트에 서명 합니다. Adventure Works 클라이언트는 Microsoft에서 서명 하는 모든 응용 프로그램을 신뢰 하도록 구성 됩니다.  
  
 ClickOnce 배포 매니페스트에 대 한 링크를 클릭할 때 사용자의 컴퓨터에 응용 프로그램을 설치 합니다. 인증서 및 배포 정보를 사용 하는 고유 하 게 클라이언트 컴퓨터에 대 한 ClickOnce 응용 프로그램을 식별 합니다. 사용자가 다른 위치에서 동일한 응용 프로그램을 다시 설치 하려고 ClickOnce이이 id를 사용 하 여 클라이언트에 응용 프로그램이 이미 존재 하는지 확인 수 있습니다.  
  
 다음으로, ClickOnce 권한이 부여 됩니다. ClickOnce 신뢰 수준을 결정 하는 응용 프로그램 매니페스트에 서명 하는 데 사용 되는 인증서를 검사 합니다. Adventure Works가 Microsoft에서 서명 하는 모든 응용 프로그램을 신뢰 하도록 클라이언트를 구성한 후에이 ClickOnce 응용 프로그램 완전 신뢰 권한이 부여 됩니다. 자세한 내용은 [Trusted Application Deployment Overview](../deployment/trusted-application-deployment-overview.md)을 참조하십시오.  
  
## <a name="creating-customer-deployments-for-earlier-versions"></a>이전 버전에 대 한 고객 배포 만들기  
 경우에 어떻게 개발자 고객에 게 이전 버전의.NET Framework를 사용 하는 ClickOnce 응용 프로그램을 구축는 무엇입니까? 다음 섹션에서는 각각의 장단점와 함께 몇 가지 권장된 솔루션을 요약합니다.  
  
### <a name="sign-deployments-on-behalf-of-customer"></a>고객을 대신 하 여 배포에 서명  
 고객의 개인 키를 사용 하 여 고객을 대신 배포를 서명 하는 메커니즘을 만드는 개발자를 위한 한 가지 가능한 배포 전략은 합니다. 이렇게 하면 개발자 개인 키 또는 여러 배포 패키지를 관리 하지 않아도 됩니다. 개발자는 동일한 배포 각 고객에 게 제공 됩니다. 고객은 서명 서비스를 사용 하 여 해당 환경에 대 한 사용자 지정 하는 합니다.  
  
 이 메서드에 한 가지 단점은 시간과 구현 하는 데 필요한 비용입니다. .NET Framework SDK에 제공 하는 도구를 사용 하 여 이러한 서비스를 구축할 수 있습니다 하는 동안 제품 수명 주기를 더 많은 개발 시간이 추가 됩니다.  
  
 이 항목의 앞부분에서 설명 했 듯이 다른 단점은 응용 프로그램의 각 고객의 버전은 때문에 동일한 응용 프로그램 id 충돌이 발생할 수 있습니다. 중요 하지 않은 경우 개발자는 각 응용 프로그램에 고유한 이름을 지정 하 고 배포 매니페스트를 생성할 때 사용 되는 이름 필드를 변경할 수 있습니다. 응용 프로그램의 각 버전에 대 한 별도 id를 만들고 id가 충돌할 가능성이 제거 합니다. 이 필드에 해당 하는 `-Name` Mage.exe에 대 한 및 인수는 **이름** 필드에 **이름** MageUI.exe에서 탭 합니다.  
  
 예를 들어, 개발자가 응용 프로그램 1 이라는 응용 프로그램을 만들고 있습니다. 단일 배포 응용 프로그램 1로 설정 하는 이름 필드를 만드는 대신 개발자는 응용 프로그램 1 CustomerA, 응용 프로그램 1-CustomerB 등이 이름에 사용자 지정 변형 여러 배포를 만들 수 있으며 등.  
  
### <a name="deploy-using-a-setup-package"></a>설치 패키지를 사용 하 여 배포  
 두 번째 가능한 배포 전략 ClickOnce 응용 프로그램의 초기 배포를 수행 하는 Microsoft 설치 프로젝트를 생성 하는 것입니다. 일부의 형식 중 하나에 제공 될 수 있습니다: 설치 실행 파일는 MSI 배포 형태로 (합니다. EXE) 또는 일괄 처리 스크립트와 함께 캐비닛 (.cab) 파일로.  
  
 이 방법을 사용할 경우 개발자가 고객 제공 응용 프로그램 파일, 응용 프로그램 매니페스트 및 템플릿으로 사용 하는 배포 매니페스트를 포함 하는 배포 합니다. 고객은 메시지가 표시 하는 배포 URL (서버 또는 파일 공유 사용자가 ClickOnce 응용 프로그램을 설치 하는 위치)에 대 한 디지털 인증서 설치 프로그램을 실행 됩니다. 설치 응용 프로그램 업데이트 확인 간격 등의 추가 ClickOnce 구성 옵션을 요청 하도록 수도 있습니다. 이 정보를 수집 되 면 설치 프로그램은 실제 배포 매니페스트를 생성, 서명 하 고, 및 ClickOnce 응용 프로그램을 지정 된 서버 위치에 게시 합니다.  
  
 세 가지 방법으로 고객이이 상황에서 배포 매니페스트를 서명할 수 있습니다.  
  
1.  고객은 CA (인증 기관)에서 발급 한 유효한 인증서를 사용할 수 있습니다.  
  
2.  이 방법에 대 한 변형, 고객 자체 서명 된 인증서로 배포 매니페스트에 서명 하도록 선택할 수 있습니다. 이 단점은 응용 프로그램 사용자가 것인지 묻는 메시지가 나타나면 설치 하는 경우 "알 수 없는 게시자" 단어를 표시 하기 않도록입니다. 그러나 이점은을 시간과 인증 기관에서 발급 한 인증서에 필요한 비용을 들이지 않아도 작은 고객 방지할 수입니다.  
  
3.  마지막으로, 개발자가 설치 패키지에 자신의 자체 서명 된 인증서를 포함할 수 있습니다. 이 항목의 앞부분에서 설명한 응용 프로그램 id로 잠재적인 문제에 소개 합니다.  
  
 설치 프로그램 배포 프로젝트 메서드에 단점은 시간이 나 사용자 지정 배포 응용 프로그램을 빌드하는 데 필요한 비용입니다.  
  
### <a name="have-customer-generate-deployment-manifest"></a>고객 배포 매니페스트를 생성 한  
 세 번째 가능한 배포 전략 꺼져 손 응용 프로그램 파일 및 응용 프로그램 매니페스트 고객에 게 있습니다. 이 시나리오에서 고객은.NET Framework SDK를 사용 하 여 생성 하 고 배포 매니페스트에 서명 하는 일을 담당 합니다.  
  
 이 방법의 단점은 고객이.NET Framework SDK 도구를 설치 하 고 개발자 또는 시스템 관리자가 사용 하 여에 능숙 해야 한다는 것입니다. 일부 고객에 게 기술 작업이 거의 또는 전혀 필요 하는 솔루션을 요구할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [테스트를 위해 ClickOnce 응용 프로그램을 배포 및 프로덕션 서버 하지 않음](../deployment/deploying-clickonce-applications-for-testing-and-production-servers-without-resigning.md)   
 [연습: ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)   
 [연습: 다시 서명할 필요가 없고 브랜드 정보가 유지되는 ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application-that-does-not-require-re-signing-and-that-preserves-branding-information.md)
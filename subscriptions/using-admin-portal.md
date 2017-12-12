---
title: "관리자 포털 사용 | Visual Studio Marketplace"
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 10/3/2017
Ms.topic: Get-Started-Article
Description: "관리자 포털을 사용하여 조직의 Visual Studio 구독을 관리하는 방법을 알아봅니다."
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: 71927765ace09f898421935416aa4c7e7110dc04
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
#  <a name="using-the-visual-studio-subscriptions-administrator-portal"></a>Visual Studio 구독 관리자 포털 사용

Visual Studio 구독 관리 포털을 사용하는 경우 다음 사항을 명심하세요.
 
- **Visual Studio 구독에서는 사용자별로 라이선스가 부여됩니다.** 각 구독자는 개발 및 테스트에 필요한 만큼 여러 컴퓨터에서 소프트웨어를 사용할 수 있습니다. 
- 조직에서 구입한 Visual Studio 구독에 해당하는 **각 구독자에 대해 하나의 구독 수준만 할당합니다**. 구독 수준이 둘 이상 할당된 구독자가 있으면 구독 수준이 하나만 있도록 해당 설정을 편집합니다. 
- 구독이 업그레이드되거나("버전 업그레이드" 라이선스 구입 후) 더 낮은 수준으로 갱신되는 경우 **구독자의 구독 수준을 업데이트해야 합니다**. 
- **구독자 간에 구독을 공유하지 않습니다.** 구독 혜택(개발 및 테스트용 소프트웨어, Microsoft Azure, E-Learning 등)의 전부 또는 일부를 사용하는 모든 사용자에게 구독을 할당해야 합니다. 

## <a name="adminstrator-roles"></a>관리자 역할
볼륨 라이선스 고객을 위한 새로운 Visual Studio 구독 관리 포털에는 서로 다른 두 가지 역할이 있습니다. 이러한 역할은 현재 VLSC의 기본/통지 연락처 담당자 역할 및 구독 관리자 역할과 같습니다. 

**슈퍼 관리자:** 조직이 처음 설정되면 기본적으로 기본 또는 통지 연락처 담당자가 슈퍼 관리자가 됩니다. 기본 또는 통지 연락처 담당자는 슈퍼 관리자 또는 관리자를 추가로 할당하도록 선택할 수 있습니다. 슈퍼 관리자는 구독자뿐만 아니라 다른 관리자도 추가하거나 제거할 수 있습니다. 시스템에 둘 이상의 슈퍼 관리자가 있는 경우 슈퍼 관리자는 보안을 위해 마지막 두 개를 제외하고 모두 삭제할 수 있습니다. 

**관리자:** 관리자는 슈퍼 관리자만 설정할 수 있습니다. 관리자는 슈퍼 관리자가 계약에서 할당한 구독자를 관리할 수 있습니다. 

## <a name="getting-started"></a>시작
### <a name="onboarding"></a>온보딩
Visual Studio 구독 관리 포털에 조직을 등록할 준비가 되면 온보딩 프로세스를 완료하도록 초대하는 전자 메일을 기본/통지 연락처 담당자에게 보냅니다. 아래의 자세한 내용은 새 포털에 등록하기 위해 수행해야 하는 단계입니다. 이 프로세스를 단계별로 연습하려면 [관리자 온보딩 비디오](https://channel9.msdn.com/Series/Visual-Studio-Subscriptions-Administration/Onboarding-your-organization-to-the-new-Visual-Studio-Subscription-Administration-Portal-and-setting) 또는 이 [지원 문서](https://support.microsoft.com/help/4013931/visual-studio-subscriptions-administrator-migration-process "Visual Studio 구독 관리자 마이그레이션 프로세스")를 확인하세요.   
1.  **PCN 찾기 및 로그인:**
- 전자 메일에는 고유한 링크 및 해당 PCN(공용 고객 번호)의 마지막 세 자리와 함께 기본/통지 연락처 담당자가 제공됩니다. * 
- 전체 PCN을 얻으려면 기본 연락처 담당자가 VLSC에 로그인해야 합니다(PCN을 찾기 위한 지침은 여기에 있음). 
- PCN을 얻은 후에 로그인하도록 요구하는 메시지가 표시될 고유한 링크를 선택해야 합니다. 조직에 AAD가 없는 경우 회사/학교 계정(AAD에 속한 조직인 경우) 또는 MSA(Microsoft 계정)를 사용하여 로그인할 수 있습니다. 
- 다음으로 PCN을 입력해야 합니다. 
2.  **관리자를 설정합니다.** PCN을 입력한 후에는 새 시스템에 슈퍼 관리자로 등록되며 다른 슈퍼 관리자와 관리자(이전의 구독 관리자)를 추가할 수 있습니다. 액세스 권한을 손실하지 않도록 방지하려면 조직의 마이그레이션 날짜 이전에 완료해야 합니다. 
3.  **새 구독 관리 포털에 액세스합니다.**  조직이 마이그레이션되면 새 포털에 액세스하고 구독 관리를 시작하도록 초대하는 전자 메일을 새로 추가된 슈퍼 관리자와 관리자에게 보냅니다.  

* *참고: 기본 또는 통지 연락처 담당자가 둘 이상의 전자 메일을 받는 경우 이는 둘 이상의 PCN이 있음을 의미합니다. 각 전자 메일에서 참조된 PCN에 대한 고유한 링크를 사용하여 프로세스를 완료해야 합니다.*

새 Visual Studio 구독 관리 포털에 사용자를 추가해야 하는 경우 기본/통지 연락처 담당자가 누구인지 확실하지 않으면 [VLSC](https://www.microsoft.com/Licensing/servicecenter/default.aspx)에 로그인한 후에 이 정보를 찾을 수 있습니다. VLSC에서 기본/통지 연락처 담당자를 찾는 단계는 [이 문서](http://www.visualstudio.com/subscriptions/support/#!articles/962-6707-how-do-i-locate-my-primary-contact "기본 연락처를 어떻게 찾나요?")를 살펴보세요.
이미 관리자로 설정되어 있으면 [Visual Studio 구독 관리 포털](https://manage.visualstudio.com)로 직접 이동할 수 있습니다.

### <a name="understanding-the-subscribers-page"></a>구독자 페이지 이해
구독을 할당하면 [구독자] 탭에서 구독자에 대해 다음과 같은 세부 정보가 제공됩니다.
- 각 구독자의 성과 이름
- 해당 사용자에 대한 이메일 주소
- 할당된 구독 수준
- 구독이 할당된 날짜 
- 해당 구독에 대한 만료 날짜
- 선택적인 텍스트 설명
- 구독자 다운로드 사용 여부의 표시 
- 구독자가 위치한 국가
- 관리 포털에서 할당 통신 전자 메일에 대한 언어 기본 설정
- 통신에 사용되는 로그인 이외의 다른 이메일 주소에 대한 선택적 필드 

이 페이지의 왼쪽에는 조직에서 각 계약에 대해 구입하고, 할당하고, 아직 사용 가능한 구독 라이선스의 수에 대한 추가 정보가 표시될 수 있습니다.
![Visual Studio 구독 관리 포털 구독자 페이지](_img/using-admin-portal/subscribers-page.png)

### <a name="understanding-the-details-page"></a>세부 정보 페이지 이해
확인하려는 계약에 대한 자세한 내용을 보려면 [세부 정보] 탭을 선택합니다. 계약 상태, 구입 계정, 조직 세부 정보, 기본 연락처(VLSC), 슈퍼 관리자(있는 경우) 및 기타 관련 정보가 표시됩니다. 
![Visual Studio 구독 관리 포털 세부 정보 페이지](_img/using-admin-portal/details-page.png)


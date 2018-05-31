---
title: VLSC 관리 마이그레이션 FAQ  | Microsoft Docs
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 03/13/2018
ms.topic: Get-Started-Article
description: 볼륨 라이선스 서비스 센터 관리자 마이그레이션 FAQ
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: e4dda4264ae48903e98166346f9e2569ab1e4da0
ms.sourcegitcommit: 37144589d9f850ff81ec7bfb884429989925a43d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2018
ms.locfileid: "34336128"
---
# <a name="visual-studio-subscriptions-administration-migration"></a>Visual Studio 구독 관리 마이그레이션

향후 몇 개월 동안 Visual Studio 구독(이전 MSDN 구독)의 관리에 변경이 예정되어 있습니다. 현재 볼륨 라이선싱을 통해 Visual Studio 구독을 구매할 수 있으며 구독은 볼륨 라이선스 서비스 센터(VLSC) 포털 내에서 관리됩니다. 새 관리 포털을 만들고 있으며 향후 이 새 포털에서 Visual Studio 구독을 관리하게 됩니다. VLSC에서 제공하는 기존 작업 이외에 새 포털에서는 한도 없는 대량 할당, 구독의 추적 및 필터링, 엑세스 관리를 위한 Azure AD(Azure Active Directory) 사용 기능을 허용합니다. 새 Visual Studio 관리 포털은 [https://manage.visualstudio.com](https://manage.visualstudio.com)에 위치합니다. 

> [!Note] 
> 이 마이그레이션은 MPSA 고객에게 영향을 주지 않습니다. 

## <a name="frequently-asked-questions"></a>질문과 대답

### <a name="why-is-it-changing"></a>이렇게 변경되는 이유는 무엇인가요?
새 포털에서는 Visual Studio 구독 관리의 환경을 최적화하고 구매 방법에 관계없이 Visual Studio 구독을 관리하는 단일 환경을 만듭니다. 새 포털에는 미래를 위해 우리를 배치하고 Azure AD를 사용할 수 있는 새 플랫폼이 있습니다. 또한 보다 쉽게 이동하고 사용할 수 있는 업데이트된 사용자 인터페이스가 있어 관리자 효율성을 향상시킵니다.

### <a name="who-will-be-impacted"></a>영향을 받을 사람은 누구인가요? 
이 변경은 볼륨 라이선싱 계약을 하고 볼륨 라이선스를 통해 Visual Studio 구독을 구매한 모든 고객에게 영향을 미칩니다. 

### <a name="when-is-it-changing"></a>언제 변경되나요?
이는 대대적인 전환으로서 Visual Studio 구독에 대한 활성 볼륨 라이선싱 계약을 맺은 모든 고객이 새 관리 포털로 마이그레이션될 때까지 단계별로 완료됩니다. 이 마이그레이션은 2017년 1분기 중에 시작됐습니다. 볼륨 라이선싱 고객에게는 예약된 해당 마이그레이션 주에 앞서 알림이 전송됩니다.  

### <a name="does-my-organization-need-to-sign-up-for-azure-active-directory-azure-ad"></a>조직에서도 Azure AD(Azure Active Directory)에 등록해야 합니까?
조직은 Azure AD에 등록하지 않아도 되지만 등록은 언제든 가능합니다. Azure AD에 등록을 선택하면 Azure AD에 대한 무료 계층을 사용하여 비용 없이 등록할 수 있습니다. Azure Active Directory를 사용하면 향상된 보안, 제어 및 장기적인 안전성으로 조직을 보호할 수 있습니다. 그러나 Azure AD에 대해 준비가 되지 않은 경우 현재처럼 MSA(Microsoft 계정)를 계속 사용할 수 있습니다. 

### <a name="how-do-i-know-when-my-organization-will-be-migrated"></a>조직이 언제 마이그레이션되는지 어떻게 알 수 있습니까?
조직이 마이그레이션되기 1주일 전에 온보딩 프로세스를 완료하도록 초대하는 이메일이 기본/알림 연락처 담당자에게 전송됩니다. 구독 관리자에게는 당사가 기본/알림 연락처 담당자에게 연락해 성공적인 온보딩을 확인하는 방법에 관한 상세 정보를 제공했음을 알리는 이메일이 전송됩니다. [조직의 기본/알림 연락처 찾기](#How-do-I-find-out-who-my-Primary-or-Notices-Contact-is?) 방법을 알아봅니다. 

### <a name="is-onboarding-different-from-migration"></a>온보딩은 마이그레이션과 다릅니까?
예.  이 프로세스는 두 단계로 구성되어 있습니다. 마이그레이션에 앞서 조직의 설정(또는 온보딩)을 통해 관리자 권한으로 작업에 중단이 없는지 확인합니다. 일단 조직의 정보를 마이그레이션하면 새 포털에서 Visual Studio 구독을 관리할 수 있습니다. 마이그레이션 전에 기본/알림 연락처 담당자가 등록되지 않은 경우 구독 관리자가 차단되고 온보딩 프로세스를 완료할 때까지 구독을 관리할 수 없게 됩니다. 

### <a name="what-is-the-onboarding-process"></a>온보딩 프로세스는 무엇입니까?
온보딩 프로세스를 완료하도록 초대하는 이메일이 기본 및 알림 연락처로 전송됩니다. 프로세스에 대한 지침은 아래를 참조하십시오. 
1.  **PCN 찾기 및 로그인:**

    a.  이메일에서는 고유한 링크 및 해당 PCN(공용 고객 번호)의 마지막 세 자리가 기본/알림 연락처 담당자에게 제공됩니다.* 

    b.  전체 PCN을 얻으려면 기본 연락처 담당자가 VLSC에 로그인해야 합니다(PCN을 찾기 위한 지침은 아래에 있음). 

    c.  PCN을 얻은 후에 로그인하도록 요구하는 메시지가 표시될 고유한 링크를 선택해야 합니다. 조직에 Azure AD가 없는 경우 회사/학교 계정(Azure AD에 속한 조직인 경우) 또는 MSA(Microsoft 계정)를 사용하여 로그인할 수 있습니다. 

    d.  다음으로 PCN을 입력하라는 메시지가 표시됩니다. 

2.  **관리자를 설정합니다.**

    PCN을 입력한 후에는 슈퍼 관리자와 관리자(이전의 구독 관리자)를 추가할 수 있는 페이지로 이동합니다. 이상적으로는 이 절차는 구독을 관리하는 데 중단이 없도록 조직의 마이그레이션 날짜 전에 완료해야 합니다. 

3.  **새 구독 관리 포털에 액세스하기:** 조직이 마이그레이션되면 새 포털에 액세스하고 구독 관리를 시작하도록 초대하는 이메일을 슈퍼 관리자와 관리자에게 보냅니다. 

> [!NOTE] 
> 기본 또는 알림 연락처 담당자가 1 초과 이메일을 받은 경우 이는 1 초과 PCN이 있음을 의미합니다. 각 이메일에서 참조된 PCN에 대한 고유한 링크를 사용하여 프로세스를 완료해야 합니다. 

### <a name="what-is-the-difference-between-a-super-admin-and-an-administrator"></a>슈퍼 관리자와 관리자의 차이는 무엇입니까?
기본/알림 연락처 담당자가 처음으로 로그인한 경우 자동으로 슈퍼 관리자로 설정됩니다. 슈퍼 관리자는 다른 슈퍼 관리자 또는 관리자를 추가/삭제하여 구독에 대한 관리자 액세스를 관리할 수 있으며 또한 구독도 관리할 수 있습니다. 슈퍼 관리자는 자신 외에 다른 슈퍼 관리자를 할당하도록 선택할 수 있습니다.

관리자(이전의 구독 관리자)는 구독을 관리할 수는 있지만 구독 관리에 대한 액세스 권한을 가진 사용자를 제어할 수는 없습니다. 

### <a name="how-will-i-as-an-administrator-onboard-to-the-new-portal"></a>관리자는 어떻게 새 포털에 등록합니까?
조직의 기본 및 알림 연락처 담당자는 Azure AD(Azure Active Directory) 또는 개인 MSA에서 지원하는 회사나 학교 계정 중 하나를 사용하여 로그인하는 페이지로 이동할 수 있는 고유한 링크가 든 이메일을 받습니다. 로그인하면 담당자는 조직의 PCN(공용 고객 번호) 또는 권한 부여 번호를 입력하여 계약을 확인해야 합니다. 담당자는 Visual Studio 구독을 관리하는 다른 관리자를 추가할 수 있는 슈퍼 관리자로 설정됩니다. 

### <a name="where-do-i-manage-subscriptions-if-my-organization-has-been-onboarded-but-hasnt-been-migrated"></a>조직이 등록됐으나 아직 마이그레이션되지 않은 경우 구독을 어디서 관리합니까? 
조직이 마이그레이션되어 새 포털에서 관리할 준비가 됐다는 이메일을 Visual Studio 구독에서 받을 때까지 VLSC를 통해 계속 구독을 관리할 수 있습니다. 

### <a name="where-can-i-locate-my-organizations-public-customer-number-pcn-or-authorization-number"></a>PCN(공용 고객 번호) 또는 권한 부여 번호를 어디서 찾을 수 있습니까?
[VLSC](https://www.microsoft.com/Licensing/servicecenter/default.aspx)에 로그인하여 **구독** > **Visual Studio 구독** 경로로 이동합니다. PCN은 **계약/공용 고객 번호 결과** 아래에 있습니다. 이 [도움말 문서](/find-pcn/)에서 PCN 찾기에 대한 단계별 지침을 가져옵니다. 

### <a name="how-do-i-find-out-who-my-primary-or-notices-contact-is"></a>기본 또는 알림 연락처 담당자는 어떻게 찾습니까?
[VLSC](https://www.microsoft.com/Licensing/servicecenter/default.aspx)에 로그인하여 **라이선스 > 관계 요약** 경로로 이동해 **라이선스 ID > 연락처**를 선택합니다. 이 [도움말 문서](find-primary-contact.md)에서 기본 또는 알림 연락처 담당자를 찾는 방법에 대한 단계별 지침을 가져옵니다. 

### <a name="what-if-my-primary-or-notices-contact-is-gone-no-longer-with-the-company-or-not-available-to-complete-onboarding"></a>기본 또는 알림 연락처 담당자가 사라져 더 이상 회사에 근무하지 않거나 온보딩을 완료할 수 없을 경우는 어떻게 합니까?
[지원에 문의](https://www.visualstudio.com/subscriptions/support/#talktous)하고 구독 관리를 위해 VLSC에서 사용한 이메일을 제공해야 합니다. 확인되면 온보딩 프로세스에 도움이 되는 지원이 가능합니다. 

### <a name="what-will-happen-with-renewing-customers"></a>고객 갱신은 어떻게 합니까? 
갱신 프로세스는 마이그레이션에서 영향을 받지 않기 때문에 고객 갱신은 평소 대로 해당 구독을 계속 갱신해야 합니다. 

### <a name="should-my-organization-wait-to-set-up-a-new-agreement-in-the-new-system-rather-than-renew-an-existing-agreement"></a>조직이 기존 계약을 갱신하지 않고 새 시스템에서 새 계약을 설정하려면 기다려야 합니까? 
아니요.  마이그레이션은 계약의 생성 또는 갱신에 영향을 미치지 않습니다. 

### <a name="what-if-my-organizations-agreement-is-in-the-grace-period-during-the-transition-will-they-also-be-migrated"></a>조직의 계약이 전환 동안 유예 기간에 있는 경우 어떻게 합니까? 조직도 마이그레이션됩니까?
예, 계약이 여전히 활성 상태인 경우 조직이 마이그레이션됩니다. 

### <a name="what-if-my-organization-has-over-claimed-in-the-current-system-will-we-still-be-migrated-to-the-new-system"></a>조직이 현재 시스템에서 과도한 클레임을 한 경우 어떻게 합니까? 그래도 조직이 새 시스템으로 마이그레이션됩니까? 
예, 그래도 조직이 새 시스템으로 마이그레이션됩니다. 새 시스템에는 과도한 클레임을 하는 기능(이 기능을 허용 하는 계약 형식)이 존재합니다. 

### <a name="what-if-my-organization-has-more-than-one-subscription-assigned-to-a-single-useremail-address"></a>조직에 단일 사용자/이메일 주소에 할당된 1 초과 구독이 있는 경우 어떻게 합니까?
그래도 조직이 마이그레이션됩니다.  그러나 동일한 수준의 모든 추가 구독(예: Enterprise, Professional 등)을 해당 사용자/이메일 주소로 할당할 수는 없습니다. 마이그레이션 시 동일한 이메일 주소가 있는 동일한 수준의 구독은 여전히 표시되지만 관리자는 이메일 주소를 변경해 고유한 것으로 만들어야 합니다. 새 포털에서는 동일한 수준의 여러 구독을 단일 사용자/이메일 주소에 할당할 수 없습니다.

### <a name="where-can-i-find-the-most-up-to-date-information-about-the-migration"></a>마이그레이션에 대한 최신 정보는 어디에 있습니까? 
이 마이그레이션에 대한 최신 정보는 Visual Studio 구독 관리자 [웹 페이지](https://aka.ms/vs-admin)를 참조합니다. 지원이 필요한 경우 자가 지원 정보 및 지원 연락처 정보가 포함된 Visual Studio 구독 [지원 페이지](http://www.visualstudio.com/subscriptions/support/#!collections/962-subscriptions)를 확인합니다. 향후 몇 개월 동안 이 전환을 쉽게 할 수 있도록 이메일을 통해 그리고 관리자 웹 페이지에서 업데이트를 계속 제공할 예정입니다. 

## <a name="resources-and-support-information"></a>리소스 및 지원 정보
- [관리자 웹 페이지](https://www.visualstudio.com/subscriptions-administration/)

- Visual Studio 구독 및 관리 [지원](https://www.visualstudio.com/subscriptions/support/) 

- [PCN 찾는 방법](find-pcn.md)

- [기본 또는 알림 연락처 찾는 방법](find-primary-contact.md) 

- 관리자 관리 및 조직 온보딩을 위한 [비디오](https://www.youtube.com/watch?v=ZmnywYGSFMg&list=PLReL099Y5nRfDyvvwzNDBaZe7qTxmuM2T&index=1&t=0s) 

---
title: CSP에 대한 Visual Studio 클라우드 구독 구매
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 3/15/2018
Ms.topic: Get-Started-Article
Description: Information for Cloud Solution Providers on how to buy and manage Visual Studio cloud subscriptions for your customers.
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: e6bbaa7e84da44b53bc7cea0d0b0746e4680caf2
ms.sourcegitcommit: 67374acb6d24019a434d96bf705efdab99d335ee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="buy-and-manage-visual-studio-cloud-subscriptions-for-your-customers"></a>고객에 대한 Visual Studio 클라우드 구독 구입 및 관리

[CSP(클라우드 솔루션 공급자)](https://partner.microsoft.com/en-US/cloud-solution-provider) 프로그램의 파트너는 고객에 대한 Visual Studio Enterprise 및 Visual Studio Professional 클라우드 구독을 구매할 수 있습니다. 

[클라우드 구독 옵션 비교](https://www.visualstudio.com/vs/pricing)

## <a name="prerequisites"></a>전제 조건
먼저 파트너 센터에서 고객 테넌트를 설정하고 이 테넌트에 대한 Azure 구독을 만들어야 합니다. 
[자세히](https://docs.microsoft.com/vsts/billing/csp/set-up-csp-customer)

## <a name="how-to-buy"></a>구매 방법

<iframe src="//channel9.msdn.com/Shows/Visual-Studio-for-CSP-Partners/CSP-How-to-buy-Visual-Studio-Subscriptions/player" width="600" height="315" allowFullScreen="true" frameBorder="0"></iframe>

0. [Microsoft 파트너 센터](https://partnercenter.microsoft.com)에 로그인합니다.
0. **고객**을 선택하고 구입할 고객을 선택합니다.
0. **서비스 관리**를 선택합니다.
0. **Visual Studio Marketplace**를 선택합니다.
0. 고객의 이름이 오른쪽 상단 모서리에 있는지 확인합니다.
0. **구독**을 선택합니다.
0. Enterprise 또는 Professional을 선택하고 Visual Studio에 대한 월간 또는 연간 구독을 선택합니다.
0. **구입**을 선택합니다.
0. 구매에 대해 청구할 Azure 구독을 선택합니다.
0. 고객에게 필요한 사용자 수를 입력합니다.
0. 순서를 검토하고 **확인**합니다.

>[!NOTE]
> Visual Studio 구독을 CSP로서 구매할 때마다 이러한 단계를 수행해야 합니다. 이 때 구매 자동화에 대한 API는 없습니다.

구매를 확인하면 **관리**를 선택해 고객의 최종 사용자에게 구독을 할당할 수 있습니다.  **서비스 관리**를 선택하여 파트너 센터에서 구독 관리 포털에 액세스할 수도 있습니다.  여기에서 아래의 단계 또는 비디오를 참조하십시오.

## <a name="how-to-manage-visual-studio-cloud-subscriptions-for-your-customer"></a>고객에 대한 Visual Studio 클라우드 구독 관리 방법

<iframe src="//channel9.msdn.com/Shows/Visual-Studio-for-CSP-Partners/CSP-How-to-manage-Visual-Studio-Subscriptions/player" width="600" height="315" allowFullScreen="true" frameBorder="0"></iframe>

0. [Microsoft 파트너 센터](https://partnercenter.microsoft.com)에 로그인합니다.
0. **고객** 및 고객의 이름을 선택합니다.
0. **서비스 관리**를 선택합니다.
0. **Visual Studio 구독 관리**를 선택합니다.

이 고객에 대해 1 초과 Azure 구독이 있는 경우 드롭 다운 메뉴를 사용하여 구매한 구독을 통해 Azure 구독을 선택합니다.  **라이선스 요약**은 할당된 구독 수 및 각 Visual Studio 클라우드 구독 옵션에 대해 사용할 수 있는 구독 수를 표시합니다.  또한 요약을 사용하면 추가로 구독을 구매하거나 구독 수를 줄일 수 있습니다.

**추가**를 선택하여 새 사용자에게 구독을 할당합니다.  표시된 개수를 업데이트하면 최종 사용자가 이메일 알림을 받습니다. 그런 다음, 최종 사용자는 [Visual Studio 구독자 포털](https://my.visualstudio.com?wt.mc_id=o~msft~docs)에서 Visual Studio 구독을 활성화하기 위해 제공된 이메일 주소를 사용하여 로그인할 수 있습니다.

Visual Studio 구독을 다른 사용자에게 다시 할당하려면 현재 구독자를 지우고 새 구독자를 추가할 수 있습니다. 

구독자가 Visual Studio 구독을 활성화하지 않았다면 초대 이메일을 누락했을 수 있습니다.  Visual Studio 관리자 포털 내에서 사용자에게 활성화 초대를 다시 전송하도록 요청할 수 있습니다.

## <a name="view-visual-studio-pricing-for-csp-partners"></a>CSP 파트너에 대한 Visual Studio 가격 책정 보기

CSP 파트너에 대한 Visual Studio 가격 책정을 보려면 [파트너 센터](https://partnercenter.microsoft.com)에 로그인합니다.  왼쪽 탐색 창에서 **가격 책정 및 제품**을 선택합니다.  오른쪽 상단의 **사용량 기반 서비스**에서 현재 달 가격 책정 파일을 선택합니다. Excel 스프레드시트를 다운로드한 후 **Azure 가격 목록** 시트로 이동하여 **미터 범주** 열을 **Visual Studio**로 필터링합니다.

이 스프레드시트에 나타나는 것을 해석하는 방법은 다음과 같습니다.
| 미터 범주    |   name                 |  단위                                |           뭐냐 하면                          |
|-------------------|------------------------|---------------------------------------|-------------------------------------------------|
| Visual Studio     | 엔터프라이즈             |  구독                         | Visual Studio Enterprise 월간 구독   |
| Visual Studio     | Enterprise(연간)    |  연간 구독                 | Visual Studio Enterprise 연간 구독    |
| Visual Studio     | 2차원 형식           |  구독                         | Visual Studio Professional 월간 구독 |
| Visual Studio     | Professional(연간)  |  연간 구독                 | Visual Studio Professional 연간 구독  |

매월 각 Visual Studio 구독을 구입하는(지정된 고객에 대해) 6번째 단위에 5% 할인을 제공합니다. 이러한 이유로 각 구독 옵션에 대해 두 개의 행이 표시됩니다. 한 행은 단위 1-5까지 기본 가격으로 해석해야 하는 “최소 값” 0을 표시합니다. 두 번째 행은 단위 6 이상에 적용되는 5% 할인 가격인 "최소 값" 5를 표시합니다.


## <a name="faq"></a>FAQ
### <a name="q-how-are-monthly-cloud-subscription-charges-processed"></a>질문: **월간** 클라우드 구독 요금은 어떻게 처리됩니까?
답변: 첫 번째 구매에 현재 달의 남은 날짜를 포함하기 위해 비례 배분된 수량을 청구합니다. 예를 들어, 10개 Visual Studio Professional 월간 클라우드 구독을 4월 15일에 구매했다면 한 달 30일 중 15일, 즉 50%가 남았으므로 단위 5를 청구하게 되며 청구 단위는 50%로 비례 배분합니다. 5월 1일에 그리고 그 이후 취소할 때까지 매월 전체 10단위 요금이 청구됩니다.

나중에 유료 수량이 증가할 경우 현재 달의 남은 날짜를 포함하려면 증가된 단위를 비례 배분합니다. 따라서 1 초과 Visual Studio Professional 월간 클라우드 구독을 5월 10일에 구입했다면 대략 0.677단위(한 달 31일 중 남은 21일)를 청구하게 됩니다. 

### <a name="q-how-are-annual-cloud-subscription-charges-processed"></a>질문: **연간** 클라우드 구독 요금은 어떻게 처리됩니까?
답변: 각 구매 시 즉시 구매한 전체 수량 요금을 청구합니다. 요금은 일년에 걸쳐 분배하지 않으며 비례 배분은 없습니다. 현재 연도의 다른 시기에 연간 클라우드 구독을 구입하는 경우 다른 달 내에 구독을 갱신하게 됩니다. 일반적으로 Microsoft 볼륨 라이선스 계약 구매에서 그런 것처럼 고객의 연간 클라우드 구독 모두를 동일하게 취급하지 않습니다.

### <a name="q-how-do-cancelations-work"></a>질문: 취소는 어떻게 합니까?
답변: Visual Studio 클라우드 구독을 취소할 경우 자동 갱신을 취소합니다. 구독은 기본 갱신일까지 단순히 계속되다가 만료됩니다. 만료 시 Visual Studio 구독자는 Visual Studio나 구독으로 인한 기타 모든 혜택을 더 이상 사용할 수 없습니다.

월간 클라우드 구독의 경우 취소는 다음 달의 첫째 날에 효력을 발휘합니다. 고객의 월간 클라우드 구독의 일부만 취소하는 경우 올바른 사용자가 활성화된 구독을 계속 할당받을 수 있도록 다음 달의 첫째 날에 취소한 사용자를 제거해야 합니다.

연간 클라우드 구독의 경우 취소는 원래 구매에서 12개월 또는 지난 연간 갱신 요금 청구로부터 12개월 다음 달의 첫째 날에 효력을 발휘합니다. 예를 들어 2018년 1월 3일에 Visual Studio Enterprise 연간 클라우드 구독을 구입한 경우 다음 해로 자동 갱신되는 2019년 2월 1일까지는 활성화를 유지합니다. 구입 당시와 2020년 2월 1일 사이에 언제든 취소하는 경우 해당 구독은 2020년 2월 1일에 만료됩니다. 연간 클라우드 구독의 경우 구독 한 해 동안 일부 취소에 대한 환불은 없습니다.

### <a name="q-what-kind-of-volume-discounts-are-available-for-visual-studio-subscriptions"></a>질문: Visual Studio 구독에 대해 어떤 종류의 수량 할인이 가능합니까?

답변: 구독의 *각 유형 내에서* 6번째 및 이후의 모든 구독에 대해 5% 할인됩니다.

* Visual Studio Professional 월간
* Visual Studio Professional 연간
* Visual Studio Enterprise 월간
* Visual Studio Enterprise 연간

예를 들어 6개 Visual Studio Professional 월간 구독 및 5개 Visual Studio Enterprise 월간 구독을 구입하는 경우 5개 professional에 대해 일반 가격을 지불하고 6번째 professional은 5% 할인을 받고 모든 5개 엔터프라이즈 구독에 대해서는 일반 가격을 지불합니다.

할인은 지정된 월간 청구 기간에 청구된 요금에 대해서만 적용됩니다. 따라서 한 달에 5개 Visual Studio Professional 연간 구독을 구입하고 다음 달에 5개를 더 구입하는 경우 10개 구독 모두 일반 가격을 지불합니다.

이러한 할인 정책은 [파트너 센터](https://partnercenter.microsoft.com) 내의 가격 책정 데이터에 반영됩니다. 

### <a name="q-are-there-renewal-discounts"></a>질문: 갱신 할인이 있습니까?

답변: 없습니다. Visual Studio 구독에 대한 가격은 균일합니다. 새 구독 및 계속 구독에 대해 동일한 가격이 적용됩니다.

### <a name="q-are-there-azure-devtest-pricing-options-for-csps"></a>질문: CSP에 대한 Azure 개발/테스트 가격 책정 옵션이 있습니까?

답변: 현재는 없습니다. 고객은 [Azure 개발/테스트 가격 책정](http://aka.ms/azuredevtestpricing)을 이용할 수 있지만 특히 CSP에 대해서는 아무 것도 없습니다.
---
title: Visual Studio 구독자용 ID
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 3/15/2018
Ms.topic: Get-Started-Article
Description: How to add an alternate identity for your Visual Studio subscription, to use for VSTS and Azure.
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: 70bfd305ec35b562fb722fb853016c3df4240ff8
ms.sourcegitcommit: 67374acb6d24019a434d96bf705efdab99d335ee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="identities-for-visual-studio-subscribers"></a>Visual Studio 구독자용 ID

Visual Studio 구독을 활성화하면 Visual Studio 구독을 사용하여 활성화하는 동안 사용했던 ID(또는 로그인)을 연결합니다. 이러한 방식으로 [Visual Studio 구독자 포털](https://my.visualstudio.com?wt.mc_id=o~msft~docs), VSTS 및 Azure에서 사용자를 인식할 수 있습니다.

VSTS에서는 로그인할 때마다 Visual Studio 구독 상태를 확인하고 구성원인 사용자의 각 계정 내에서 자동으로 사용자에게 기능을 부여합니다. 이러한 기능이 구독자 혜택에 포함되어 있으므로 Visual Studio 구독에 연결된 ID를 사용하는 경우 모든 VSTS 계정의 구성원으로 사용자를 무료로 추가합니다.

Azure에서 구독자 혜택인 [월간 Azure 크레딧](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/)을 활성화하는 경우 Visual Studio 구독 상태를 확인합니다.

[Visual Studio 구독자 포털](https://my.visualstudio.com?wt.mc_id=o~msft~docs) 내에서 활성화 동안 사용했던 ID 외에도 **대체 ID**를 추가할 수 있습니다. 오늘 구독을 활성화하기 위해 Microsoft 계정을 사용하는 경우 대체 ID를 추가할 수 있습니다. 이 방식으로 회사 또는 학교 계정(Visual Studio, Office 365 또는 회사 또는 학교 네트워크에 로그인할 때 사용하는)을 추가할 수 있으며, 사용자의 개인 계정과 회사 또는 학교 계정 모두를 사용하여 VSTS에 액세스할 수도 있습니다.

## <a name="how-to-add-an-alternate-identity-to-your-visual-studio-subscription"></a>Visual Studio 구독에 대체 ID를 추가하는 방법

1. [Visual Studio 구독자 포털](https://my.visualstudio.com?wt.mc_id=o~msft~docs)에 로그인합니다.

  > "개인 계정" 또는 "회사 또는 학교 계정"을 선택하도록 요구받는 경우 "개인 계정"(사용자의 Microsoft 계정)을 선택합니다.
  >
  > 경우에 따라 Microsoft 계정 및 회사 또는 학교 계정이 동일한 이메일 주소를 공유 하기 때문에 선택해야 합니다. 두 ID는 동일한 이메일 주소를 사용한다고 해도 여전히 다른 프로필, 보안 설정 및 사용 권한이 있는 별도 ID입니다.
  >
  > 2018년 3월 30일부터 더 이상 Azure Active Directory에서 관리되는 도메인을 사용하는 이메일을 통해 Microsoft 계정을 만들 수 없습니다. 이 이메일을 회사 계정으로 사용하여 여전히 로그인할 수는 있습니다.

2. **구독** 탭으로 이동합니다.

  ![구독 선택](_img/vs-alternate-identity/choose-subscriptions-my-visual-studio-com-portal.png)

3. **관련 링크** 아래에서 **대체 계정 추가**로 이동합니다.

  ![관련 링크 아래에서 대체 계정 추가로 이동](_img/vs-alternate-identity/add-alternate-account-my-visual-studio-com-portal.png)

4. 회사 또는 학교 계정을 입력하고 **추가**를 선택합니다.

  ![회사 또는 학교 계정 입력](_img/vs-alternate-identity/enter-alternate-account-my-visual-studio-com-portal.png)

5. 회사 또는 학교 계정을 사용하여 VSTS 계정(```https://{youraccount}.visualstudio.com```)에 로그인합니다. 정보를 전파하는 데 약간의 지연이 있을 수 있으므로 15분 뒤에 다시 확인하세요. 

## <a name="faq"></a>FAQ

### <a name="q--why-doesnt-vsts-recognize-me-as-a-visual-studio-subscriber"></a>질문: 왜 VSTS에서 나를 Visual Studio 구독자로서 인식하지 못합니까?
대답: 기본 또는 대체 ID를 사용하여 로그인할 때 VSTS는 사용자의 구독을 자동으로 인식해야 합니다. 그렇지 않다면 몇 가지를 시도해볼 수 있습니다.

* [VSTS를 혜택으로 포함](vs-vsts.md)하는 활성화된 Visual Studio 구독이 있는지 확인합니다.

* 사용하는 로그인/ID가 Visual Studio 구독을 위한 기본 또는 대체 ID인지 확인합니다.

* VSTS에 로그인하기 전에 한 번 이상 [Visual Studio 구독자 포털](https://my.visualstudio.com?wt.mc_id=o~msft~docs)을 방문하십시오.

그래도 VSTS가 여전히 사용자의 구독을 인식하지 못하는 경우 [지원 문의](https://www.visualstudio.com/team-services/support/)


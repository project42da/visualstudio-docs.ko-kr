---
title: Visual Studio 구독자용 ID
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 04/10/2018
ms.topic: conceptual
description: VSTS 및 Azure를 사용하기 위해 Visual Studio 구독에 대체 ID를 추가하는 방법
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: vs subscription
ms.openlocfilehash: 9a83f78f35b9533c554c81cecd181c00eca05568
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="identities-for-visual-studio-subscribers"></a>Visual Studio 구독자용 ID

Visual Studio 구독을 활성화하면 Visual Studio 구독을 사용하여 활성화하는 동안 사용했던 ID(또는 로그인)을 연결합니다. 이러한 방식으로 [Visual Studio 구독자 포털](https://my.visualstudio.com?wt.mc_id=o~msft~docs), VSTS(Visual Studio Team Services) 및 Azure에서 사용자를 인식할 수 있습니다.

VSTS에서는 로그인할 때마다 Visual Studio 구독 상태를 확인하고 구성원인 사용자의 각 계정 내에서 자동으로 사용자에게 기능을 부여합니다.
이러한 기능이 구독자 혜택에 포함되어 있으므로 Visual Studio 구독에 연결된 ID를 사용하는 경우 모든 VSTS 계정의 구성원으로 사용자를 무료로 추가합니다.

Azure에서 구독자 혜택인 [월간 Azure 크레딧](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/)을 활성화하는 경우 Visual Studio 구독 상태를 확인합니다.

[Visual Studio 구독자 포털](https://my.visualstudio.com?wt.mc_id=o~msft~docs) 내에서 활성화 동안 사용했던 ID 외에도 **대체 ID**를 추가할 수 있습니다. 오늘 구독을 활성화하기 위해 Microsoft 계정을 사용하는 경우 대체 ID를 추가할 수 있습니다. 이 방식으로 회사 또는 학교 계정(Visual Studio, Office 365 또는 회사 또는 학교 네트워크에 로그인할 때 사용하는)을 추가할 수 있으며, 사용자의 개인 계정과 회사 또는 학교 계정 모두를 사용하여 VSTS에 액세스할 수도 있습니다.

## <a name="add-an-alternate-account-to-your-visual-studio-subscription"></a>Visual Studio 구독에 대체 ID 추가

대체 계정을 Visual Studio 구독에 추가하면 구독이 할당된 ID 외에 다른 ID로 VSTS(Visual Studio Team Services) 및 Azure 같은 구독 혜택에 액세스할 수 있습니다. 이전에 이 기능은 VS(Visual Studio) 구독이 MSA(Microsoft 계정)에 할당된 경우에만 사용할 수 있었습니다. Azure AD(Azure Active Directory)에서 회사 또는 학교 계정에 대해 이 기능을 확장했습니다.

이 기능은 다른 계정에 구독의 복사본을 제공하지 않습니다. 다만 대체 계정으로 두 가지 혜택에 액세스하는 기능만 제공합니다.

모든 구독에 대해 "회사 또는 학교 계정"을 추가할 수 있으므로 로그인이 필요한 혜택(VS IDE, VSTS 및 Azure)으로 해당 계정을 사용할 수 있습니다.

### <a name="prerequisites"></a>전제 조건

* [VSTS 프로젝트 컬렉션 관리자 또는 계정 소유자 권한](https://docs.microsoft.com/en-us/vsts/accounts/faq-add-delete-users#find-owner).

* 대체 계정을 사용하려면 계정과 연결된 구독에 Visual Studio Team Services 또는 Microsoft Azure가 포함되어 있어야 합니다.

> [!Note]
> 대체 ID로 구독 혜택을 계속 사용할 수 있지만 구독은 여전히 원래 계정과 연결되어 있습니다.

### <a name="add-the-alternate-account"></a>대체 계정 추가

1. Microsoft 계정 (https://{youraccount}.visualstudio.com)으로 Visual Studio에 로그인합니다.

2. **구독**으로 이동합니다.

  ![대체 계정 추가 - VS에서 구독으로 이동](_img/vs-alternate-identity/my-vs-subscriptions.png)

3. **대체 계정 추가**를 선택합니다.

  ![대체 계정 추가 선택 ](_img/vs-alternate-identity/choose-add-alternate-account.png)

4. 회사 또는 학교 계정을 추가합니다.

  ![회사 또는 학교 계정 추가](_img/vs-alternate-identity/enter-alternate-account-my-visual-studio-com-portal.png)

5. 회사 또는 학교 계정을 사용하여 Visual Studio(https://{youraccount}.visualstudio.com)에 로그인합니다.

  ![회사 또는 학교 계정 사용](_img/vs-alternate-identity/sign-in-with-alternate-account.png)

  대체 계정이 Visual Studio 구독에 추가되어 두 ID가 대체 계정으로 로그인 해야 하는 구독의 혜택(IDE, VSTS 및 Azure)을 활용할 수 있습니다.

대체 계정 추가에 대한 자세한 내용은 [내 Visual Studio FAQ](https://www.visualstudio.com/my/myvsfaq#alternate) 페이지를 참조합니다.

## <a name="faq"></a>FAQ

### <a name="q--why-doesnt-vsts-recognize-me-as-a-visual-studio-subscriber"></a>질문: 왜 VSTS에서 나를 Visual Studio 구독자로서 인식하지 못합니까?
대답: 기본 또는 대체 ID를 사용하여 로그인할 때 VSTS는 사용자의 구독을 자동으로 인식해야 합니다. 그렇지 않다면 몇 가지를 시도해볼 수 있습니다.

* [VSTS를 혜택으로 포함](vs-vsts.md)하는 활성화된 Visual Studio 구독이 있는지 확인합니다.

* 사용하는 로그인/ID가 Visual Studio 구독을 위한 기본 또는 대체 ID인지 확인합니다.

* VSTS에 로그인하기 전에 한 번 이상 [Visual Studio 구독자 포털](https://my.visualstudio.com?wt.mc_id=o~msft~docs)을 방문하십시오.

그래도 VSTS가 여전히 사용자의 구독을 인식하지 못하는 경우 [지원 문의](https://www.visualstudio.com/team-services/support/)

---
title: MPSA(Microsoft 제품 및 서비스 계약)에서 Visual Studio 구독 | Microsoft Docs
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 03/14/2018
ms.topic: Get-Started-Article
description: MPSA(Microsoft 제품 및 서비스 계약)에서 Visual Studio 구독
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: a18565a97c0cd85ce42109961592a57c490d92a1
ms.sourcegitcommit: 3724338a5da5a6d75ba00452b0a607388b93ed0c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2018
---
# <a name="visual-studio-subscriptions-in-a-microsoft-products-and-services-agreement-mpsa"></a>MPSA(Microsoft 제품 및 서비스 계약)에서 Visual Studio 구독

MPSA 프로그램을 통해 Visual Studio 구독을 구매한 경우 Visual Studio 구독 관리자가 되어 구독을 다른 사용자에게 할당하기 전에 기억해야 할 몇 가지가 있습니다. 이미 관리자로 설정되어 있으면 Visual Studio 구독 [관리 포털](https://manage.visualstudio.com/)로 직접 이동할 수 있습니다. 

MPSA 고객으로서 MPSA을 통해 구매한 자산을 관리할 수 있는 포털을 소개합니다. 이 새 포털은 [비즈니스 센터](https://businessaccount.microsoft.com/)라고 하며 VLSC(볼륨 라이선스 서비스 센터)와 동일하고 새로운 기능의 일부를 지원합니다. 이러한 기능에는 라이선스 요약, 주문, 다운로드, 키, 사용자 등의 보기가 포함됩니다. 그러나 MPSA에서 Visual Studio 구독은 마치 클라우드 서비스처럼 동작합니다. 또한 비즈니스 센터는 Microsoft 계정 대신 회사 계정을 사용하여 로그인합니다. 조직이 Office 365 또는 Azure Active Directory 같은 클라우드 서비스를 사용하고 사용자 이메일이 이러한 두 서비스에 속한 경우 이는 이미 회사 계정입니다. 이 계정을 사용하면 조직이 사용자에게 할당한 기존 암호를 사용하여 비즈니스 센터에 등록할 수 있습니다. 조직에서 클라우드 서비스를 사용하지 않고 이메일도 회사 계정이 아닌 경우라도 기존 암호를 사용해 비즈니스 센터에 등록할 수 있으므로 걱정하지 않아도 됩니다.

또한 Visual Studio 구독 [관리 포털](https://manage.visualstudio.com/)에서는 일단 Visual Studio 관리자가 되면 구독을 구독자에게 할당할 수 있습니다. MPSA에서 Visual Studio 구독자는 Visual Studio 구독 관리 포털인 해당 관리 포털에 프로비전해야 합니다. 이렇게 하려면 테넌트(예: contoso.onmicrosoft.com)에 구매 계정을 연결해야 합니다. 

테넌트에는 두 가지 유형(관리되는 테넌트 및 관리되지 않는 테넌트)이 있습니다. 관리되는 테넌트는 관리자로서 조직에서 이미 관리하고 있는 테넌트를 가리킵니다. 

관리되지 않는 테넌트는 관리자 없는 테넌트로서 Office 365 같은 온라인 서비스에는 사용할 수 없습니다. 또한 관리되지 않는 테넌트는 회사 계정이 아닌 이메일을 사용하여 비즈니스 센터에 등록할 때 만들어집니다. 비즈니스 센터에 등록할 때 암호를 만들도록 요청받는 경우 이는 이메일이 회사 계정이 아니며 관리되지 않는 테넌트를 만들었다는 의미입니다.

테넌트 연결을 완료하기 전에 Visual Studio 구독 관리자가 되는 데 필요한 몇 가지 요구 사항/단계가 있습니다.

## <a name="pre-tenant-association-managed-tenant"></a>사전 테넌트 연결(관리되는 테넌트)
-   비즈니스 센터에 등록된 사용자여야 합니다.
-   사용자는 자신이 속한 테넌트 내에서 사용자 관리자(최소한) 또는 전역 관리자여야 합니다. (회사가 이미 클라우드 서비스를 사용하는 경우 해당됩니다). Visual Studio 구독 관리자가 되려면 두 역할 중 하나가 필요합니다.
-   사용자는 자신의 테넌트에 구매 계정을 연결할 수 있으려면 자신이 속한 테넌트의 전역 관리자여야 합니다.
-   비즈니스 센터에서 사용자는 계정 관리자여야 합니다.
-   [Azure](https://portal.azure.com/)의 사용자 프로필(및 다른 모든 사용자)에서 "국가 또는 지역" 필드는 해당 지역(예: 미국, 캐나다 등)에 따라 적절하게 채워야 합니다. 

> [!NOTE]
> Visual Studio 구독 관리자로 만들려는 사용자 모두는 2단계 및 5단계의 조건을 충족하는 데 필요하므로 비즈니스 센터의 사용자가 될 것을 요구받지 않습니다.

위의 다섯 단계의 조건을 모두 충족하면 아래 단계에 따라 사용자는 자신의 테넌트에 구매 계정을 연결할 수 있습니다.
1.  [비즈니스 센터](https://businessaccount.microsoft.com/)에 로그인합니다.
2.  **계정** 탭을 클릭하고 **도메인 연결**을 선택합니다.
3.  **구매 계정**(1 초과 구매 계정이 있는 경우)을 선택합니다.
4.  **테넌트**(예: contoso.onmicrosoft.com)를 선택합니다.
5.  **도메인 연결**을 클릭합니다.

연결 시 필요한 조건을 충족한 모든 사용자는 일반적으로 몇 분 이내에 Visual Studio 구독 관리자로서 프로비젼됩니다. 그러나 때로는 최대 24시간이 걸릴 수도 있습니다. 프로비전되면 Visual Studio 구독 관리 포털에 액세스할 수 있게 됩니다. 24시간 보다 오래 걸릴 경우 MPSA 고객 지원 팀에 문의하세요.

> [!NOTE]
> (연결 후에) 2단계 및 5단계 조건을 충족하는 새 사용자가 있는 경우 MPSA 고객 지원 팀에 문의해야 합니다. MPSA 고객 지원 팀은 새 Visual Studio 구독 관리자를 프로비전하기 위한 지원을 제공합니다.

## <a name="tenant-association-unmanaged"></a>테넌트 연결(관리되지 않는)

위의 다섯 번째 단락에서 설명한 것처럼 회사 계정이 아닌("Azure AD"(Azure Active Directory)에 등록되지 않은) 이메일을 사용하여 비즈니스 센터에 등록한 경우 테넌트 연결이 약간 달라집니다. 이른 바 “도메인 인수”를 수행해야 합니다. 이 프로세스 동안 사용자 스스로 전역 관리자가 되어 관리되지 않는 테넌트에서 관리되는 테넌트로 변경해야 합니다.

이 프로세스에 대한 자세한 내용은 [빠른 시작 안내](https://www.microsoft.com/en-us/Licensing/existing-customer/business-center-training-and-resources.aspx)를 참조합니다. 도메인 인수 과정을 안내해 줄 *"온라인 서비스 설치 및 사용"*이라는 가이드를 다운로드합니다. 이 작업이 완료되면 사용자의 구매 계정이 테넌트에 연결됩니다.

> [!NOTE]
> 도메인 인수 과정을 완료한 후 사용자는 사전 테넌트 연결(관리되는)에 대한 섹션에서 다섯 단계의 모든 조건을 준수해야 합니다. 이러한 조건이 충족되면 추가 Visual Studio 구독 관리자를 프로비전하기 위해 MPSA 고객 지원 팀에 문의해야 합니다.

도움이 필요하거나 질문이 있는 경우 전화나 이메일로 고객 지원 팀에 문의할 수 있습니다.

MPSA 고객 지원 팀: **1-866-200-9611**, 월요일-금요일 오전 5시 30분에서 오후 5시 30분까지(태평양 표준시) 문의 가능

이메일: ngvlsup@microsoft.com

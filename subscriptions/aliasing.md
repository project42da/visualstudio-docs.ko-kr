---
title: "별칭을 사용하여 Visual Studio 구독에 로그인하지 못할 수 있음 | Microsoft Docs"
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 1/2/2018
Ms.topic: Get-Started-Article
Description: Sign-in may fail if aliases or friendly names are used.
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: 8c07bc8d3cf674d86c2152ff80f20e4fac003fc3
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2018
---
# <a name="signing-in-to-visual-studio-subscriptions-may-fail-with-aliases"></a>별칭을 사용하여 Visual Studio 구독에 로그인하지 못할 수 있음

로그인에 사용되는 계정 유형에 따라 [https://my.visualstudio.com](https://my.visualstudio.com?wt.mc_id=o~msft~docs)에 로그인할 때 사용 가능한 구독이 제대로 표시되지 않을 수 있습니다. 한 가지 원인은 구독이 할당된 로그인 ID 대신 “별칭” 또는 “이름”을 사용하기 때문일 수 있습니다. 이것을 “별칭 지정”이라고 합니다. 

## <a name="what-is-aliasing"></a>별칭 지정이란 무엇인가요?

“별칭 지정”이라는 용어는 사용자가 Windows(또는 Active Directory)에 로그인하고 전자 메일에 액세스하기 위해 서로 다른 ID를 사용하는 것을 나타냅니다.

회사에 디렉터리 로그인용 Microsoft Online Service가 있지만(예: JohnD@contoso.com) 사용자가 별칭 또는 이름(예: John.Doe@contoso.com)을 사용하여 전자 메일 계정에 액세스할 경우 별칭 지정이 수행됩니다.  VLSC(볼륨 라이선스 서비스 센터)를 통해 구독을 관리하는 많은 고객의 경우 제공된 전자 메일 주소(John.Doe@contoso.com)가 “회사 또는 학교 계정” 옵션을 통해 인증에 성공하는 데 필요한 디렉터리 주소(JohnD@contoso.com)와 일치하지 않을 때 이 별칭 지정으로 인해 로그인에 실패할 수 있습니다.

## <a name="as-an-administrator-what-options-do-i-have"></a>관리자로서 어떤 옵션이 있나요?

관리자는 구독자가 [https://my.visualstudio.com](https://my.visualstudio.com?wt.mc_id=o~msft~docs)에 성공적으로 로그인했는지 확인하는 두 가지 옵션이 있습니다. 
1. 첫 번째 옵션(권장)은 VLSC(볼륨 라이선스 서비스 센터)에서 디렉터리 계정을 할당된 주소로 활용하는 것입니다. 자세한 내용은 이 문서의 [디렉터리 계정에 구독자 할당](#assigning-subscribers-to-a-directory-account) 섹션을 참조하세요.
2. 두 번째 옵션(보안 수준 낮음)은 구독자가 “회사 또는 학교” 전자 메일 주소를 “개인” 계정(즉 Microsoft 계정 또는 MSA)에 연결하도록 허용하는 것입니다. 자세한 내용은 [회사 또는 학교 계정을 개인 계정으로 정의 ](#defining-a-work-or-school-account-as-a-personal-account ) 섹션을 참조하세요.

> [!NOTE]
> 회사가 새 Visual Studio 구독 [관리 포털](https://manage.visualstudio.com)로 마이그레이션되면 구독자 프로필의 일부로 디렉터리 및 전자 메일 주소를 제공할 수 있는 새 관리 환경을 활용할 수 있습니다.  [마이그레이션](https://support.microsoft.com/help/4013930/visual-studio-subscriptions-administrator-migration-details)에 대해 자세히 알아보세요.

## <a name="as-a-subscriber-what-options-do-i-have"></a>구독자로서 어떤 옵션이 있나요?

구독자 관점에서 먼저 관리자와 함께 회사의 ID 구성을 이해하는 것이 중요합니다.  필요한 경우 관리자가 관리 포털에서 계정 설정을 업데이트해야 할 수 있습니다. 또는 사용자가 회사 전자 메일 주소를 사용하여 Microsoft 계정(MSA)을 만들어야 할 수 있습니다.  MSA를 만드는 단계를 수행하기 전에 이 작업 수행과 관련된 정책 또는 문제에 대해 관리자와 이야기를 나눕니다.  자세한 내용은 [회사 또는 학교 계정을 개인 계정으로 정의 ](#defining-a-work-or-school-account-as-a-personal-account ) 섹션을 참조하세요.  

## <a name="assigning-subscribers-to-a-directory-account"></a>디렉터리 계정에 구독자 할당 

모든 경우에 VLSC(볼륨 라이선스 서비스 센터) 내의 구독 관리자는 새 구독자의 디렉터리 주소를 사용하거나 “기존” 구독자의 전자 메일 주소를 업데이트해야 합니다.  디렉터리 주소를 사용하면 모든 새 구독자가 시작 전자 메일을 수신하지 않으므로 관리자가 구독이 할당되었음을 구독자에게 알려야 함을 의미합니다.  아래 단계를 수행한 후에는 부담 없이 전자 메일 [템플릿](#notifying-your-subscribers-with-directory-addresses)을 사용하여 구독자에게 알리고 로그인 프로세스를 통해 구독자를 도울 수 있습니다.

### <a name="adding-new-subscribers"></a>새 구독자 추가
다음 단계에 따라 디렉터리 계정으로 새 구독자를 추가합니다.

1. VLSC([볼륨 라이선스 서비스 센터](https://www.microsoft.com/Licensing/servicecenter/default.aspx))를 방문하여 로그인합니다.
2. VLSC 관리 페이지에서 **구독**, **Visual Studio 구독**을 차례로 클릭합니다.

    ![구독 메뉴](_img//vlsc/vlsc-subscriptions.png)

3. Visual Studio 구독에 연결된 **계약 번호**를 클릭합니다.

    ![계약 선택](_img/vlsc/vlsc-agreement.png)

4. **구독 할당**을 클릭합니다.

    ![구독 할당](_img/vlsc/vlsc-assign.png)

5. 원하는 **구독 수준**을 선택합니다.

    ![구독 수준](_img/vlsc/vlsc-subscription-level.png)
    
6. 할당할 수 있는 구독이 있는지 확인하고 **다음**을 클릭합니다.
7.  [전자 메일 주소] 필드에 구독자 세부 정보 및 디렉터리 주소를 입력하고 **다음**을 클릭합니다.

    ![전자 메일 주소](_img/vlsc/vlsc-email-address.png)
    
8. 구독자 정보를 확인하고 **마침**을 클릭합니다.

9. 아래 [템플릿](#notifying-your-subscribers-with-directory-addresses)을 사용하여 해당 구독이 프로비전되었음을 구독자에게 알립니다.

### <a name="updating-an-existing-subscriber"></a>기존 구독자 업데이트
아래 단계에 따라 디렉터리 계정으로 기존 구독자를 업데이트하세요.

1. VLSC([볼륨 라이선스 서비스 센터](https://www.microsoft.com/Licensing/servicecenter/default.aspx))를 방문하여 로그인합니다.

2. VLSC 관리 페이지에서 **구독**, **Visual Studio 구독**을 차례로 클릭합니다.

3. Visual Studio 구독에 연결된 **계약 번호**를 클릭합니다.

4. 검색 창에서 **아래쪽 화살표**를 클릭합니다.

5. “전자 메일 주소” 필드를 사용하여 구독자를 검색합니다.

6. 결과 목록에서 구독자의 **성**을 클릭합니다.

7. 
              **편집**을 클릭합니다.

8. [전자 메일 주소] 필드를 원하는 디렉터리 주소로 변경하고 **저장**을 클릭합니다.

9. 아래 전자 메일 템플릿을 사용하여 구독이 프로비전되었음을 구독자에게 알립니다.

### <a name="notifying-your-subscribers-with-directory-addresses"></a>디렉터리 주소로 구독자에게 알림
시작 전자 메일이 구독자에 성공적으로 도달하지 않으므로 아래 메시지를 복사하여 전자 메일에 붙여넣고 구독자에게 보냅니다. %WORD%를 각 구독자에 대한 적절한 정보로 바꿉니다.

----------- 아래 복사(Ctrl+C) -----------

안녕하세요 %SUBSCRIBER NAME% 님,

Visual Studio 구독이 할당되었습니다.  https://my.visualstudio.com을 방문하고 %DIRECTORY ADDRESS% 주소로 로그인하여 구독을 활성화하고 액세스하세요. 

문제가 있는 경우 지원 팀 (https://www.visualstudio.com/subscriptions/support/)에 문의해 주세요.

페이지 아래쪽에서 다음을 선택합니다.
   - 계정, 구독 및 청구 지원
   - 문제에서 구독 로그인 지원 선택
   - 적절한 국가 선택
   - 원하는 보조 지원 옵션 선택

----------- 복사 끝 -----------



## <a name="defining-a-work-or-school-account-as-a-personal-account"></a>회사 또는 학교 계정을 개인 계정으로 정의 
[디렉터리 계정에 구독자 할당](#assigning-subscribers-to-a-directory-account) 섹션에 설명된 지침을 활용하여 새 사용자를 추가하거나 VLSC(볼륨 라이선스 서비스 센터) 내에서 사용자의 전자 메일 주소를 업데이트하세요.  전자 메일 주소가 디렉터리에서 인식되지 않는 경우 사용자는 새 계정을 만들어 전자 메일 주소를 개인 계정으로 정의하는 프로세스 단계를 수행해야 합니다.  짧은 기간 동안 Visual Studio 구독 팀은 아래 정의된 ID 정책에서 예외를 확보했지만 이제 이 정책을 제거하는 데 필요한 기능에 투자하고 있습니다.

> [!WARNING]
> Microsoft는 “회사 또는 학교” ID를 “개인” ID와 결합하는 것을 권장하지 않습니다.  이 작업으로 인해 조직은 계정의 소유권 및 제어를 상실하고 직원은 회사를 떠난 후에도 특정 제품 또는 서비스에 계속 액세스할 수 있습니다.  자세한 내용은 Microsoft Identity 팀에서 제공하는 이 블로그 [게시물](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/15/cleaning-up-the-azure-ad-and-microsoft-account-overlap/)을 참조하세요.

### <a name="defining-an-email-address-as-a-personal-account"></a>전자 메일 주소를 개인 계정으로 정의
구독자에게 구독이 할당된 후 구독 혜택을 활용하기 위해 https://my.visualstudio.com을 방문하도록 요청하는 전자 메일이 제공됩니다.  로그인을 시도할 때 Visual Studio 구독 로그인에 실패하고 계정이 인식되지 않음을 나타내는 오류가 표시됩니다.  https://my.visualstudio.com 환경에 로그인하기 전에 구독자에게 이러한 지침을 따르도록 요청하세요.  필요한 경우 구독을 할당한 후 이 [템플릿](#notifying-your-subscribers-using-personal-accounts)을 사용하여 구독자에게 알릴 수 있습니다.

1. https://my.visualstudio.com으로 이동하여 **새 Microsoft 계정 만들기**를 클릭합니다.

2. 필드를 완료합니다.
    - Someone@example.com 상자에 시작 전자 메일을 받은 전자 메일 주소를 입력합니다.
    - 암호를 만듭니다.
    - 프로모션 설정을 선택합니다.
    - **다음**을 클릭합니다.

3. 유효성 검사 단계를 완료하고 **다음**을 클릭합니다.

4. 새 사용자가 Visual Studio 프로필을 완료해야 할 수 있습니다.

5. 이제 구독 및 혜택이 표시됩니다.

### <a name="notifying-your-subscribers-using-personal-accounts"></a>개인 계정을 사용하여 구독자에게 알림

위에 설명된 시나리오에서 구독자는 “시작 전자 메일”을 받지만 별칭 지정으로 인해 로그인할 수 없습니다.  아래 텍스트를 사용하여 위 단계에 대해 구독자에게 알리고 필요한 경우 지원 옵션을 권장할 수 있습니다.  %WORD%를 각 구독자에 대한 적절한 정보로 바꿉니다.

----------- 아래 복사(Ctrl+C) -----------

안녕하세요 %SUBSCRIBER NAME% 님,

Visual Studio 구독이 할당되었고 시작 전자 메일을 기반으로 https://my.visualstudio.com에 로그인하도록 지시되었을 수 있습니다.  이는 혜택을 이용하기 위한 올바른 웹 사이트이지만 조직에서는 사이트에 액세스하기 전에 몇 가지 추가 단계를 수행해야 합니다.  회사 전자 메일 주소에 연결된 “Microsoft 계정”을 만드는 데 도움이 되는 아래 지침을 따르세요.  이러한 단계가 완료되면 전자 메일 주소를 사용하여 구독 혜택에 액세스합니다.
1. https://my.visualstudio.com을 방문합니다.

2. 오른쪽에서 [새 Microsoft 계정 만들기]를 클릭합니다.

3. 폼을 완료합니다. 
    - someone@example.com 상자에서 회사 전자 메일 주소를 사용합니다.
    - 암호를 입력합니다.
    - 프로모션 기본 설정을 선택합니다.
    - 다음을 클릭합니다.

4. 계정 유효성 검사 단계를 완료합니다.

5. 필요한 경우 Visual Studio 프로필을 완료합니다.

6. 이제 혜택을 확인해야 합니다.

참고: 나중에 https://my.visualstudio.com을 방문하면 사용할 계정을 선택하라는 메시지가 표시될 수 있습니다(예: “회사 또는 학교 계정” 또는 “개인 계정”).  위의 단계를 수행한 후 “개인 계정” 옵션을 활용해야 합니다.

문제가 있는 경우 지원 팀 (https://www.visualstudio.com/subscriptions/support/)에 문의해 주세요.

페이지 아래쪽에서 다음을 선택합니다.
   - 계정, 구독 및 청구 지원
   - 문제에서 구독 로그인 지원 선택
   - 적절한 국가 선택
   - 원하는 보조 지원 옵션 선택

----------- 복사 끝 -----------
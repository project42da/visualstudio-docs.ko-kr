---
title: Visual Studio 구독 관리자 포털에서 관리자 권한 관리
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 1/19/2018
Ms.topic: Get-Started-Article
Description: Learn how manage admins & super admins in the Visual Studio Subscriptions Administrator Portal.
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: 83bf27d5aaa99c2095ad8a1fafd7541df90f316b
ms.sourcegitcommit: a0a49cceb0fdc1465ddf76d131c6575018b628b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2018
---
# <a name="managing-administrator-rights-in-the-visual-studio-subscriptions-administrator-portal"></a>Visual Studio 구독 관리자 포털에서 관리자 권한 관리

## <a name="overview"></a>개요 
Visual Studio 구독 관리자 포털(https://manage.visualstudio.com))에는 두 개의 관리 역할이 있습니다.

**슈퍼 관리자:** 조직이 처음 설정되면 기본적으로 기본 또는 통지 연락처 담당자가 슈퍼 관리자가 됩니다. 기본 또는 통지 연락처 담당자는 슈퍼 관리자 또는 관리자를 추가로 할당하도록 선택할 수 있습니다. 슈퍼 관리자는 개별 구독자의 구독을 관리하는 것 외에도 다른 관리자 및 슈퍼 관리자를 추가하고 제거할 수 있습니다. 시스템에 둘 이상의 슈퍼 관리자가 있는 경우 슈퍼 관리자는 보안을 위해 마지막 두 개를 제외하고 모두 삭제할 수 있습니다. 

**관리자:** 관리자는 슈퍼 관리자가 계약에서 할당한 구독자를 관리할 수 있습니다.  개인에게 구독을 할당하고, 구독을 편집하고, 구독을 재할당 또는 제거할 수 있습니다.   (관리자는 슈퍼 관리자에 의해 지명됩니다.)  

## <a name="adding-an-administrator-with-super-admin-rights"></a>슈퍼 관리자 권한이 **있는** 관리자 추가:

1. 이미 슈퍼 관리자 권한이 있는 계정을 사용하여 Visual Studio 구독 [관리자 포털](https://manage.visualstudio.com)에 로그인합니다.

2. 페이지 위쪽에서 **관리자 관리** 탭을 클릭합니다. (슈퍼 관리자만 이 탭에 액세스할 수 있습니다.  슈퍼 관리자 권한이 없는 관리자는 **구독자 관리** 탭을 사용하여 개별 구독자를 관리할 수 있습니다.)

3. **추가**를 클릭하여 새 관리자를 만듭니다. 

4. [관리자 추가] 팝업 창에서 요청된 모든 세부 정보를 입력합니다.
  - 조직이 이미 AAD(Azure Active Directory)에 등록된 경우 먼저 **이름** 필드에 이름을 입력하고 드롭다운 목록에서 올바른 항목을 선택합니다. 새 사용자를 사용하여 전체 이름을 입력하고 *ID를 찾을 수 없음* 알림을 무시합니다.
  - 올바른 사용자가 식별되면 로그인 전자 메일 주소 필드가 자동으로 채워집니다. 새 관리자의 전자 메일 주소를 입력합니다(아직 제공되지 않은 경우).

5. **계약** 아래의 드롭다운 목록을 클릭하여 새 관리자가 관리하게 할 **PCN**을 선택합니다. 온보딩 중인 PCN 아래에 둘 이상의 계약이 있는 경우 모든 계약에 대한 액세스 권한을 관리자에게 제공할 수 있습니다. 

**계약에 대한 추가 정보**: 사용 가능한 계약이 하나만 있는 경우 계약 아래의 드롭다운 기능을 사용할 수 없습니다.  구성 중인 사용자에게 슈퍼 관리자 권한이 부여되면 모든 계약이 자동으로 선택됩니다.

6. **슈퍼 관리자** 상자를 클릭하여 이 관리자에 대한 슈퍼 관리자 권한을 사용하도록 설정합니다.  

7. 이 관리자 추가를 완료하려면 **추가**를 클릭합니다.

**관리자를 추가하는 동안 수신된 잠재적 오류**: 관리자를 추가할 때 일부 사용자에게 오류 메시지가 표시될 수 있습니다. 이 오류는 추가되는 슈퍼 관리자의 전자 메일 주소가 회사 AAD에 나열되어 있지 않은 경우 발생할 수 있습니다. 새 관리자 추가를 완료하려면 오류를 무시하고 **다시 추가**를 클릭합니다. 

8. 슈퍼 관리자가 생성되면 관리자 목록에 슈퍼 관리자가 표시되고 해당 계정에는 슈퍼 관리자 상태를 나타내는 녹색 선택 표시가 표시됩니다. 

### <a name="optional--add-a-different-notification-email"></a>선택 사항: 다른 알림 전자 메일을 추가합니다.
조직에 전자 메일을 받을 수 있는 다른 주소/계정이 있는 경우 이제 “커뮤니케이션” 주소를 입력할 수 있는 옵션을 사용할 수 있습니다. **커뮤니케이션 수신을 위한 다른 알림 전자 메일 추가**를 선택합니다. 

*예:* Rene는 회사 자격 증명을 사용하여 로그인할 때 rene@contoso.com을 사용합니다.  그러나 Rene의 회사는 디렉터리 액세스를 관리하는 데 해당 주소만 사용합니다.  전자 메일을 보내고 받을 때 Rene가 rene.collado@contoso.com을 사용하므로 슈퍼 관리자는 시작 메일을 받을 수 있도록 두 번째 주소를 입력했습니다.  회사가 이런 방식으로 구성되지 않은 경우에는 로그인 전자 메일 주소를 입력하는 것만으로 충분해야 합니다.

## <a name="adding-an-administrator-without-super-admin-rights"></a>슈퍼 관리자 권한 **없이** 관리자 추가:

슈퍼 관리자 권한 없이 관리자를 추가하려면 위에서 설명한 것과 동일한 프로세스를 수행해야 하지만 다음 측면을 고려하세요.
-  슈퍼 관리자 권한 없이 관리자를 추가하면 추가 전자 메일 주소를 추가할 필요가 없으며 슈퍼 관리자 확인란이 비어 있습니다.
-  슈퍼 관리자 권한이 없는 사용자는 “관리자 관리” 아래의 프로필 구성 항목에 녹색 확인 아이콘이 표시되지 않습니다.

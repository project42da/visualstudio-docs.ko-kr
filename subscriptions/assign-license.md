---
Title: Assign licenses to Visual Studio Subscriptions
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 10/3/2017
Ms.topic: Get-Started-Article
Description: Learn how administrators can assign licenses to subscribers
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: d9d26c9519ec5cca1f7127f93d9d1ab60378ad3f
ms.sourcegitcommit: b7d3b90d0be597c9d01879338dd2678c881087ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2017
---
# <a name="assigning-licenses-in-the-visual-studio-subscriptions-administrator-portal"></a>Visual Studio 구독 관리자 포털에서 라이선스 할당
## <a name="assigning-a-single-user"></a>단일 사용자 할당
Visual Studio 구독에 사용 가능한 라이선스가 있는 경우 해당 구독 혜택에 액세스할 수 있도록 새 사용자에게 이러한 라이선스를 할당할 수 있습니다. 
1.  단일 Visual Studio 구독자를 할당하려면 테이블 위쪽에서 **추가**를 클릭합니다.

    ![구독자 추가](_img\assign-license-add\assign-license-add.png)

2.  새 구독자에 대한 정보를 양식 필드에 입력합니다. 조직에서 Azure Active Directory를 사용하는 경우 이 필드는 검색 결과에서 올바른 사용자를 선택할 수 있도록 현재 디렉터리에 있는 사람을 찾는 검색 기능 역할을 합니다. 해당 사용자를 선택하면 아래와 같이 사용자의 이름, 로그인 전자 메일 및 알림 전자 메일이 자동으로 채워집니다. 

조직에서 로그인하는 데 사용하는 전자 메일과 다른 전자 메일을 수신하는 데 사용하는 경우 여기에 입력할 수 있는 옵션이 있습니다. "통신에 로그인 전자 메일과 다른 전자 메일을 사용하십니까?"를 나타내는 하이퍼링크를 선택합니다. 

구독자가 [Visual Studio 구독 포털](https:/my.visualstudio.com)에 로그인할 때 소프트웨어 다운로드에 액세스할 수 있도록 하도록 하려면 [다운로드] 상자를 선택한 상태로 두세요. 이 확인란을 선택 취소하면 사용자는 소프트웨어 다운로드에 액세스할 수 없지만 구독에 포함된 다른 모든 혜택에는 계속 액세스할 수 있습니다. 완료되면 **추가**를 클릭합니다.

  ![구독자 정보 입력](_img\assign-license-add\add-subscriber-1.png)

  ![구독자 정보 입력](_img\assign-license-add\add-subscriber-2.png)

3.  구독자가 추가되면 새 구독자에게 추가 지침이 있는 할당 전자 메일을 자동으로 보냅니다. 구독자를 선택하고 위쪽 메뉴의 **다시 보내기** 단추를 클릭하여 할당 전자 메일을 다시 보낼 수 있습니다.

    ![추가된 구독자](_img\assign-license-add\add-subscriber-complete.png)

## <a name="bulk-assignments"></a>대량 할당
1.  여러 구독자를 한 번에 추가하려면 [구독자] 탭으로 이동합니다. 맨 위에 있는 리본에서 **대량 추가**를 클릭합니다. 

    ![대량 추가](_img\assign-license-add\bulk-assign-add.png)

2. 대량 할당은 Microsoft Excel 템플릿을 사용하여 구독자를 업로드합니다. [여러 구독자 업로드] 대화 상자에서 **다운로드**를 클릭하여 템플릿을 다운로드합니다. 항상 이 템플릿의 최신 버전을 다운로드합니다. 이전 버전을 사용하는 경우 대량 업로드가 실패할 수 있습니다.

![여러 구독자 업로드](_img\assign-license-add\bulk-assign-upload.png)

3.  Excel 스프레드시트에서 구독을 할당하려는 개인에 대한 정보로 필드를 채웁니다. 참조는 선택적 필드입니다. 템플릿의 일부를 잘못 채운 경우 문제를 설명하는 오류 메시지가 표시됩니다. 완료되면 하드 드라이브에 파일을 저장합니다.
**원활한 업로드를 보장하기 위해 다음 모범 사례를 준수합니다.**
    - 양식 필드에 쉼표가 없는지 확인합니다.
    - 사용자 이름과 같은 양식 필드 앞뒤의 공백을 제거합니다.
    - 두 부분으로 이루어진 사용자 이름에서 첫 번째 이름과 마지막 이름 사이에 여분의 공백이 포함되지 않아야 합니다(예: 시스템에서 여분의 공백을 제거하지 않으므로 "Maggie May"와 같이 두 부분으로 이루어진 이름은 "Maggie  May"로 입력하면 안 됨)

    ![대량 추가 템플릿](_img\assign-license-add\bulk-template.png)

4.  Visual Studio 구독 관리 포털로 돌아가고, [여러 구독자 업로드] 대화 상자에서 **찾아보기**를 클릭합니다. 저장한 Excel 파일로 이동하고 **확인**을 클릭합니다. 업로드 진행률이 화면에 표시됩니다. 

    ![대량 추가 업로드](_img\assign-license-add\bulk-assign-upload-2.png)

템플릿에 오류가 있는 경우 업로드가 실패합니다. 그러면 템플릿을 수정하고 대량 업로드를 다시 시도할 수 있도록 오류 메시지가 표시됩니다.

   ![업로드 실패](_img\assign-license-add\bulk-assign-upload-fail.png)

업로드가 성공적으로 완료되면 구독자 목록과 확인 메시지가 표시됩니다.

   ![업로드 완료](_img\assign-license-add\bulk-assign-upload-complete.png)
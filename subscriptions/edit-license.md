---
title: "관리자 포털에서 구독 편집 | Visual Studio Marketplace"
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 10/3/2017
Ms.topic: Get-Started-Article
Description: Learn how administrators can edit subscription assignments.
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: c561e7a56f2e70cae1addd32902f68a582b49a02
ms.sourcegitcommit: b7d3b90d0be597c9d01879338dd2678c881087ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2017
---
# <a name="editing-visual-studio-subscription-assignments"></a>Visual Studio 구독 할당 편집

## <a name="making-changes-to-subscriber-information"></a>구독자 정보 변경
구독자 정보를 편집하여 오류를 수정하거나 정보를 업데이트할 수 있습니다. 
**구독자의 이메일 주소를 편집하면 기존 혜택이 다시 설정됩니다.**

구독자를 편집하려면 마우스로 위를 가리킬 때 구독자의 이메일 주소 옆에 나타나는 줄임표(...)를 선택합니다. 드롭다운이 표시됩니다.  **편집**을 선택하여 구독자 세부 정보를 수정합니다. 또한 그리드에서 구독자의 행을 두 번 클릭하여 편집 창을 열 수도 있습니다.

   ![편집할 구독자 선택](_img\edit-license\select-subscriber.png)

구독자의 성, 이름, 국가, 언어 및 다운로드를 업데이트할 수 있습니다. 구독자 정보를 편집한 다음 **저장**을 클릭합니다.

   ![구독자 세부 정보 편집](_img\edit-license\edit-subscriber.png)

참고: 구독자의 구독 수준을 변경해야 하는 경우 포털에서 해당 사용자를 삭제하고 다시 추가해야 합니다. 구독 수준은 편집할 수 없습니다.

## <a name="editing-multiple-subscribers-by-using-bulk-edit"></a>대량 편집을 사용하여 여러 구독자 수정

대량 편집 프로세스를 사용하여 여러 구독자를 한 번에 수정할 수 있습니다. 이 기능은 주로 회사 이메일 주소 변경을 수행하는 조직에서 사용되거나 조직에서 다운로드에 대한 액세스를 제한하도록 결정한 경우에 사용됩니다. 

**중요:** 구독 수준(예: Enterprise, Professional 등) 및 구독 GUID는 변경할 수 없습니다.  이러한 항목이 변경된 상태에서 업로드를 시도하면 업로드가 실패합니다.  

1.  여러 구독자를 한 번에 수정하려면 [구독자] 탭으로 이동합니다. 맨 위에 있는 리본에서 **대량 편집**을 클릭합니다. 

    ![라이선스 편집 - 대량 편집](_img\edit-license\edit-license-bulk-edit.png)

2.  대량 편집은 Excel 템플릿을 사용하여 구독자 정보를 편집합니다. [대량 편집] 상자에서 **이 Excel 내보내기**를 클릭하여 모든 정보가 포함된 현재 구독자 목록을 다운로드합니다. 

    ![라이선스 편집 - 대량 편집 목록 내보내기](_img\edit-license\edit-license-bulk-edit-export.png)

3.  다음으로 파일을 쉽게 찾을 수 있고 업로드하기 전에 필요한 변경을 수행할 수 있도록 해당 파일을 로컬로 저장합니다. 업로드를 성공적으로 수행하려면 **구독 수준 또는 구독 GUID**를 편집하지 마세요. 그렇지 않으면 업로드가 실패하게 됩니다. 

4.  Visual Studio 구독 관리 포털로 돌아가고, [대량 편집] 대화 상자에서 **찾아보기**를 클릭합니다. 저장한 Excel 파일을 선택하고 **확인**을 클릭합니다. 업로드 진행률이 화면에 표시됩니다.

    ![라이선스 편집 - 대량 편집 파일 업로드](_img\edit-license\edit-license-bulk-file-upload1.png)

5.  파일이 업로드되면 성공했음을 알려주는 알림이 표시됩니다. 

    ![라이선스 편집 - 대량 편집 업로드 완료](_img\edit-license\edit-license-bulk-upload-complete.png)



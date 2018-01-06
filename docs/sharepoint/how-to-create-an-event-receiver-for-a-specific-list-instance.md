---
title: "방법: 특정 목록 인스턴스에 대 한 이벤트 수신기 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, event receivers
- event receivers [SharePoint development in Visual Studio]
ms.assetid: 4b4b3564-161a-4327-8963-50896c084ac2
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: a820bc1a29db10fa5f65f1781c30218c62c2ee08
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-an-event-receiver-for-a-specific-list-instance"></a>방법: 특정 목록 인스턴스에 대한 이벤트 수신기 만들기
  목록 인스턴스 이벤트 수신자 목록 정의의 모든 인스턴스에서 발생 하는 이벤트에 응답 합니다. 이벤트 수신기 서식 파일의 특정 목록 인스턴스에 대상으로 사용 하지 않는, 있지만 특정 목록 인스턴스에의 이벤트에 응답 하는 목록 정의 범위 지정 된 이벤트 수신기를 수정할 수 있습니다.  
  
 이벤트 수신기에 대 한 Elements.xml의 특정 목록 인스턴스를 대상으로 하려면 대체 `ListTemplateId` 와 `ListUrl` 목록 인스턴스의 URL을 추가 합니다.  
  
## <a name="creating-a-list-instance-event-receiver"></a>목록 인스턴스 이벤트 수신기 만들기  
 다음 단계에는 사용자 지정 알림 목록을 인스턴스에서 발생 하는 이벤트에만 응답 하도록 목록 항목 이벤트 수신기를 수정 하는 방법을 보여 줍니다.  
  
#### <a name="to-modify-an-event-receiver-to-respond-to-a-specific-list-instance"></a>특정 목록 인스턴스에 응답 하는 이벤트 수신기를 수정 하려면  
  
1.  브라우저에서 SharePoint 사이트를 엽니다.  
  
2.  탐색 창에서 **나열** 링크 합니다.  
  
3.  에 **모든 사이트 콘텐츠** 페이지에서 선택 된 **만들기** 링크 합니다.  
  
4.  에 **만들기** 대화 상자에서 선택 하는 **공지** 입력, 발표 이름을 **TestAnnouncements**, 선택한 후는 **만들기**단추입니다.  
  
5.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], 이벤트 수신기 프로젝트를 만듭니다.  
  
6.  에 **이벤트 수신기 유형을 하나요?** 목록에서 선택 **목록 항목 이벤트**합니다.  
  
    > [!NOTE]  
    >  다른 모든 종류의 예를 들어 목록 정의로 범위를 지정 하는 이벤트 수신기를 선택할 수도 있습니다 **목록 전자 메일 이벤트** 또는 **목록 워크플로 이벤트**합니다.  
  
7.  에 **이벤트 소스를 사용할 항목을?** 목록에서 선택 **공지**합니다.  
  
8.  에 **다음 이벤트를 처리할** 목록에서는 **항목이 추가 되 고** 확인란을 선택한 후는 **완료** 단추입니다.  
  
9. **솔루션 탐색기**, EventReceiver1 아래에서 Elements.xml을 엽니다.  
  
     이벤트 수신기가 다음 코드 줄을 사용하여 알림 목록 정의를 현재 참조합니다.  
  
    ```  
    <Receivers ListTemplateId="104">  
    ```  
  
     이 줄을 다음 텍스트로 변경합니다.  
  
    ```  
    <Receivers ListUrl="Lists/TestAnnouncements">  
    ```  
  
     이렇게 하면 새에서 발생 하는 이벤트에만 응답 하는 이벤트 수신기 **TestAnnouncements** 방금 만든 공지 사항 목록입니다. 변경할 수는 `ListURL` SharePoint 서버의 모든 목록 인스턴스를 참조 하는 특성입니다.  
  
10. 이벤트 수신기에 대 한 코드 파일을 열고 ItemAdding 메서드에서 중단점을 설정 합니다.  
  
11. F5 키를 선택하여 솔루션을 빌드하고 실행합니다.  
  
12. Sharepoint에서 선택 된 **TestAnnouncements** 탐색 창에서 링크 합니다.  
  
13. 선택 된 **새 알림 추가** 링크 합니다.  
  
14. 알림의 제목을 입력 한 다음 선택에서 **저장** 단추입니다.  
  
     사용자 지정 알림 목록에 새 항목을 추가할 때 중단점이 적중 될 것을 확인 합니다.  
  
15. F5 키를 선택하여 다시 시작합니다.  
  
16. 탐색 창에서 선택 된 **나열** 링크를 선택한 다음 선택는 **공지** 링크 합니다.  
  
17. 새 공지를 추가 합니다.  
  
     이벤트 수신기를 트리거하지 않습니다 새 알림에서 수신기에서 사용자 지정 알림 목록 인스턴스 이벤트에만 응답 하도록 구성 되어 있으므로 사라졌는지 **TestAnnouncements**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 이벤트 수신기 만들기](../sharepoint/how-to-create-an-event-receiver.md)   
 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)  
  
  
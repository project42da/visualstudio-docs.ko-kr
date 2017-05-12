---
title: "방법: 특정 목록 인스턴스에 대한 이벤트 수신기 만들기"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "이벤트 수신자[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 이벤트 수신자"
ms.assetid: 4b4b3564-161a-4327-8963-50896c084ac2
caps.latest.revision: 13
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 12
---
# 방법: 특정 목록 인스턴스에 대한 이벤트 수신기 만들기
  목록 인스턴스 이벤트 수신자는 목록 정의의 인스턴스에서 발생하는 이벤트에 응답합니다.  이벤트 수신자 템플릿이 특정 목록 인스턴스의 대상 지정을 사용하도록 설정하지는 않지만 특정 목록 인스턴스의 이벤트에 응답하도록 목록 정의로 범위가 제한된 이벤트 수신자를 수정할 수 있습니다.  
  
 특정 목록 인스턴스를 대상으로 지정하려면 이벤트 수신자의 Elements.xml에서 `ListTemplateId`를 `ListUrl`로 바꾸고 목록 인스턴스의 URL을 추가합니다.  
  
## 목록 인스턴스 이벤트 수신자 만들기  
 다음 단계에서는 사용자 지정 알림 목록 인스턴스에서 발생하는 이벤트에만 응답하도록 목록 항목 이벤트 수신자를 수정하는 방법을 보여 줍니다.  
  
#### 특정 목록 인스턴스에 응답하도록 이벤트 수신자를 수정하려면  
  
1.  브라우저에서 SharePoint 사이트를 엽니다.  
  
2.  탐색 창에서 **리스트** 링크입니다.  
  
3.  **모든 사이트 콘텐츠** 페이지에서 **만들기** 링크를 선택합니다.  
  
4.  **만들기** 대화 상자에서 **알림** 형식을 선택하고 알림의 이름을 TestAnnouncements로 지정한 다음 **만들기** 버튼을 선택합니다.  
  
5.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 이벤트 수신자 프로젝트를 만듭니다.  
  
6.  **원하는 이벤트 수신자 유형을 선택하십시오.** 목록에서 **목록 항목 이벤트**를 선택합니다.  
  
    > [!NOTE]  
    >  목록 정의로 범위가 제한되는 다른 종류의 이벤트 수신자\(예: **목록 전자 메일 이벤트** 또는 **목록 워크플로 이벤트**\)를 선택할 수도 있습니다.  
  
7.  **이벤트 소스에 대한 항목을 지정하십시오.** 목록에서 **공지** 를 선택합니다.  
  
8.  **다음 이벤트를 처리** 목록에서 **항목이 추가되었습니다** 확인란을 선택한 다음 **완료** 버튼을 선택합니다.  
  
9. **솔루션 탐색기**의 EventReceiver1 아래에서 Elements.xml을 엽니다.  
  
     이벤트 수신자가 다음 줄을 사용하여 알림 목록 정의를 현재 참조합니다.  
  
    ```  
    <Receivers ListTemplateId="104">  
    ```  
  
     이 줄을 다음 텍스트로 변경 합니다.  
  
    ```  
    <Receivers ListUrl="Lists/TestAnnouncements">  
    ```  
  
     이렇게 하면 이벤트 수신자가 방금 만든 새 **TestAnnouncements** 알림 목록에서 발생하는 이벤트에만 응답합니다.  `ListURL` 특성을 변경하여 SharePoint 서버의 어떠한 목록 인스턴스라도 참조할 수 있습니다.  
  
10. 이벤트 수신자의 코드 파일을 열고 ItemAdding 메서드에 중단점을 삽입합니다.  
  
11. 솔루션을 빌드하고 실행하려면 F5 키를 선택합니다.  
  
12. SharePoint의 탐색 창에서 **TestAnnouncements** 링크를 선택합니다.  
  
13. **새 알림 추가** 링크를 선택합니다.  
  
14. 공지의 제목을 입력 한 다음 **저장** 버튼을 선택합니다.  
  
     새 항목이 사용자 지정 알림 목록에 추가될 때 중단점이 적중됩니다.  
  
15. F5 키를 선택하여 계속 합니다.  
  
16. 탐색 창에서 **리스트** 링크를 선택한 다음 **공지** 링크를 선택합니다.  
  
17. 새 알림을 추가합니다.  
  
     이벤트 수신자가 사용자 지정 알림 목록 인스턴스, **TestAnnouncements**의 이벤트에만 응답하도록 구성되었기 때문에 이벤트 수신자가 새 알림에서 트리거되지 않습니다.  
  
## 참고 항목  
 [방법: 이벤트 수신자 만들기](../sharepoint/how-to-create-an-event-receiver.md)   
 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)  
  
  
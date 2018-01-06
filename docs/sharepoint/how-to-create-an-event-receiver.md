---
title: "방법: 이벤트 수신기 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.SharePointTools.SPE.EventReceiver
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, event receivers
- event receivers [SharePoint development in Visual Studio]
ms.assetid: 6f90cb48-eb8f-43c2-a3f7-ed4ce81aedf2
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 519c6907bb5779a3819419144905ca68e5cce939
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-an-event-receiver"></a>방법: 이벤트 수신자 만들기
  만들어 *이벤트 수신기*, 목록 등의 SharePoint 항목 또는 목록 항목이와 상호 작용할 때 응답할 수 있습니다. 예를 들어 사용자가 일정을 변경 하거나 연락처 목록에서 이름을 삭제 하는 경우 이벤트 수신기에서 코드를 트리거할 수 있습니다. 이 항목에 따라 목록 인스턴스에 이벤트 수신기를 추가 하는 방법을 배울 수 있습니다.  
  
 이러한 단계를 완료 하려면 설치 해야 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 지원 되는 Windows 및 SharePoint의 버전입니다. 자세한 내용은 참조 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다. 이 예제에서는 SharePoint 프로젝트를 필요로 하므로 완료 해야 항목의 절차 [연습: 사이트 열, 콘텐츠 형식 및 SharePoint에 대 한 목록 만들기](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md)합니다.  
  
## <a name="adding-an-event-receiver"></a>이벤트 수신기 추가  
 만든 프로젝트 [연습: SharePoint 용 사이트 열, 콘텐츠 형식 및 목록 만들기](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md) 사용자 지정 사이트 열, 사용자 지정 목록 및 콘텐츠 형식을 포함 합니다. 다음 절차에서는 SharePoint 항목 목록 등에서 발생 하는 이벤트를 처리 하는 방법을 보여 주는 목록 인스턴스에 (이벤트 수신기)는 단순 이벤트 처리기를 추가 하 여이 프로젝트를 확장할 수 있습니다.  
  
#### <a name="to-add-an-event-receiver-to-the-list-instance"></a>이벤트 수신자 목록 인스턴스를 추가 하려면  
  
1.  만든 프로젝트를 열고 [연습: 사이트 열, 콘텐츠 형식 및 SharePoint에 대 한 목록 만들기](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md)합니다.  
  
2.  **솔루션 탐색기**를 이름으로 지정 된 SharePoint 프로젝트 노드를 선택 **Clinic**합니다.  
  
3.  메뉴 모음에서 **프로젝트**, **새 항목 추가**합니다.  
  
4.  아래에서 **Visual C#** 또는 **Visual Basic**를 확장 하 고는 **SharePoint** 노드를 선택한 후는 **2010** 항목입니다.  
  
5.  에 **템플릿** 창에서 선택 **이벤트 수신기**, 이름을 **TestEventReceiver1**, 선택한 후는 **확인** 단추입니다.  
  
     **SharePoint 사용자 지정 마법사** 나타납니다.  
  
6.  에 **이벤트 수신기 유형을 하나요?** 목록에서 선택 **목록 항목 이벤트**합니다.  
  
7.  에 **이벤트 소스를 사용할 항목을?** 목록에서 선택 **환자 (Clinic\Patients)**합니다.  
  
8.  에 **다음 이벤트를 처리할** 목록 옆에 확인란을 선택 합니다 **항목이 추가 되었습니다**, 선택한 후는 **마침** 단추입니다.  
  
     새 이벤트 수신기에 대 한 코드 파일 라는 단일 메서드가 들어 `ItemAdded`합니다. 다음 단계에서는이 메서드를 코드를 추가 합니다 하므로 모든 연락처 이름이 Scott Brown 기본적으로 지정 됩니다.  
  
9. 기존 항목 바꾸기 `ItemAdded` 메서드를 다음 코드를 복사해 F5 키를 선택 합니다.  
  
     [!code-csharp[SP_EventReceiver#1](../sharepoint/codesnippet/CSharp/CustomField1/TestEventReceiver1/TestEventReceiver1.cs#1)]
     [!code-vb[SP_EventReceiver#1](../sharepoint/codesnippet/VisualBasic/CustomField1_VB/EventReceiver1/EventReceiver1.vb#1)]  
  
     코드 실행 및 SharePoint 사이트는 웹 브라우저에 표시 됩니다.  
  
10. 빠른 실행 모음에서 선택 된 **환자** 링크를 선택한 다음 선택는 **새 항목 추가** 링크 합니다.  
  
     새 항목에 대 한 항목 양식이 열립니다.  
  
11. 데이터 필드에 입력 한 다음 선택에서 **저장** 단추입니다.  
  
     선택한 후는 **저장** 단추는 **환자 이름** Scott Brown 이름으로 열을 자동으로 업데이트 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)  
  
  
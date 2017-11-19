---
title: "방법: 기본 제공 탭 사용자 지정 | Microsoft Docs"
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
- Ribbon [Office development in Visual Studio], tabs
- built-in tabs [Office development in Visual Studio]
ms.assetid: 197a7aaa-a51d-496c-b904-b9421849fad9
caps.latest.revision: "28"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1161af5501ebd0df8137293b137600697af91516
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-customize-a-built-in-tab"></a>방법: 기본 제공 탭 사용자 지정
  기본 제공 탭에 그룹과 컨트롤을 추가할 수 있습니다. 기본 제공 탭은 Microsoft Office 응용 프로그램의 리본 메뉴에 이미 있는 탭입니다. 예를 들어는 **데이터** 탭은 Excel의 기본 제공 탭입니다. 사용자 지정 그룹을 만드는 경우 탭에서 마지막에 표시되지만 탭의 아무곳으로나 그룹을 이동할 수 있습니다.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
> [!NOTE]  
>  기본 제공 탭에 그룹을 추가할 수 있지만 기본 제공 탭에서 기본 제공 그룹을 제거할 수는 없습니다.  
  
### <a name="to-add-groups-to-a-built-in-tab"></a>기본 제공 탭에 그룹을 추가하려면  
  
1.  리본 코드 파일을 마우스 오른쪽 단추로 클릭 **솔루션 탐색기**, 클릭 하 고 **뷰 디자이너**합니다.  
  
    > [!NOTE]  
    >  리본 코드 파일에 표시 되지 않으면 **솔루션 탐색기**를 추가 해야 합니다는 **리본 항목** 프로젝트에 있습니다. 참조 [하는 방법: 리본 메뉴 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)합니다.  
  
2.  리본 디자이너에서 탭을 마우스 오른쪽 단추로 누른 **속성**합니다.  
  
3.  에 **속성** 창 확장는 **ControlId** 속성을 선택한 다음 설정의 **ControlIdType** 속성을 **Office**합니다.  
  
4.  설정의 **OfficeId** 속성을는 *컨트롤 ID* 사용자 지정 하려면 기본 제공 탭입니다.  
  
     컨트롤 ID는 Microsoft Office 응용 프로그램에 기본 제공된 탭, 그룹 및 컨트롤을 고유하게 식별하는 이름입니다.  
  
     컨트롤 Id 목록은 참조 [Office 2010 도움말 파일: Office Fluent 사용자 인터페이스 컨트롤 식별자](http://go.microsoft.com/fwlink/?LinkID=181052)합니다.  
  
5.  **Office 리본 컨트롤** 탭은 **도구 상자**, 탭 그룹으로 끌어 합니다.  
  
    > [!NOTE]  
    >  기본 제공 그룹은 디자이너에 표시되지 않습니다. 기본 제공 탭을 사용 하 고 있는지 여부를 확인 하는 유일한 방법은 검사 하는 따라서는 **ControlId** 해당 탭의 속성입니다.  
  
### <a name="to-position-groups-on-a-built-in-tab"></a>기본 제공 탭에 그룹을 배치하려면  
  
1.  리본 디자이너에서 사용자 지정 그룹을 선택합니다.  
  
2.  에 **속성** 창 확장는 **위치** 속성입니다.  
  
3.  설정의 **PositionType** 속성을 적절 한 값:  
  
    -   **BeforeOfficeId** 지정 된 기본 제공 그룹 앞에 그룹을 배치 합니다.  
  
    -   **AfterOfficeId** 지정 된 기본 제공 그룹 뒤에 그룹을 배치 합니다.  
  
4.  설정의 **OfficeId** 속성을 기본 제공 그룹의 컨트롤 ID입니다.  
  
     컨트롤 Id 목록은 참조 [Office 2010 도움말 파일: Office Fluent 사용자 인터페이스 컨트롤 식별자](http://go.microsoft.com/fwlink/?LinkID=181052)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [리본 개요](../vsto/ribbon-overview.md)   
 [리본 디자이너](../vsto/ribbon-designer.md)   
 [리본 XML](../vsto/ribbon-xml.md)   
 [연습: 리본 디자이너를 사용 하 여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [연습: 리본 XML을 사용 하 여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)   
 [방법: 리본 메뉴 사용자 지정 시작](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [방법: 리본의 탭 위치 변경](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md)   
 [방법: Backstage 보기에 컨트롤 추가](../vsto/how-to-add-controls-to-the-backstage-view.md)   
 [방법: 추가 기능 사용자 인터페이스 오류 표시](../vsto/how-to-show-add-in-user-interface-errors.md).  
  
  
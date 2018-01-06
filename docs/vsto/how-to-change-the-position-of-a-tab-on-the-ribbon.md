---
title: "방법: 리본의 탭 위치 변경 | Microsoft Docs"
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
helpviewer_keywords: Ribbon [Office development in Visual Studio], tabs
ms.assetid: 3f0906e3-9708-4136-ac49-986bc4c92ea4
caps.latest.revision: "26"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 196b16ba28ee5fa590c54dee89dcd65978f2ecd2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-position-of-a-tab-on-the-ribbon"></a>방법: 리본의 탭 위치 변경
  사용 하 여 리본 메뉴 사용자 지정 탭의 순서를 변경할 수는 **탭 컬렉션 편집기**합니다. 리본의 기본 제공 탭 앞 이나 뒤에 사용자 지정 탭을 배치할 수 있습니다. 기본 제공 탭은 Microsoft Office 응용 프로그램의 리본 메뉴에 이미 있는 탭입니다. 예를 들어는 **데이터** 탭은 Excel의 기본 제공 탭입니다.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### <a name="to-change-the-order-of-tabs-on-the-ribbon"></a>리본 메뉴의 탭 순서를 변경 하려면  
  
1.  리본 코드 파일 (.vb 또는.cs 파일)을 선택 **솔루션 탐색기**합니다.  
  
2.  에 **보기** 메뉴를 클릭 하 여 **디자이너**합니다.  
  
3.  리본 디자이너를 마우스 오른쪽 단추로 누른 **속성**합니다.  
  
4.  에 **속성** 창에서는 **탭** 속성을 다음 줄임표 단추를 클릭 하 고 (![ASP.NET 모바일 디자이너 줄임표](../sharepoint/media/mwellipsis.gif "ASP.NET 모바일 디자이너 줄임표")).  
  
     **탭 컬렉션 편집기** 나타납니다.  
  
5.  에 **탭 컬렉션 편집기**에 **멤버** 목록에서 이동 하 고 위쪽 또는 아래쪽 화살표를 탭 순서를 변경 하려면 탭을 선택 합니다.  
  
### <a name="to-position-a-tab-before-or-after-a-built-in-tab-on-the-ribbon"></a>리본의 기본 제공 탭 앞 이나 뒤에 탭 배치 하려면  
  
1.  리본 디자이너에서 사용자 지정 탭을 선택 합니다.  
  
2.  에 **속성** 창 확장는 **ControlId** 속성을 다음 되어 있는지 확인의 값은 **ControlIdType** 속성이로 설정 되어 **사용자지정**.  
  
3.  에 **속성** 창 확장는 **위치** 속성입니다.  
  
4.  설정의 **PositionType** 속성을 적절 한 값:  
  
    -   **BeforeOfficeId** 전에 지정된 된 기본 제공 탭에 그룹을 배치 합니다.  
  
    -   **AfterOfficeId** 후 지정된 된 기본 제공 탭에 그룹을 배치 합니다.  
  
5.  설정의 **OfficeId** 속성을 기본 제공 탭의 컨트롤 ID입니다.  
  
     컨트롤 Id 목록은 참조 [Office 2010 도움말 파일: Office Fluent 사용자 인터페이스 컨트롤 식별자](http://go.microsoft.com/fwlink/?LinkID=181052)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [리본 개요](../vsto/ribbon-overview.md)   
 [리본 디자이너](../vsto/ribbon-designer.md)   
 [리본 XML](../vsto/ribbon-xml.md)   
 [연습: 리본 디자이너를 사용 하 여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [연습: 리본 XML을 사용하여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)  
  
  
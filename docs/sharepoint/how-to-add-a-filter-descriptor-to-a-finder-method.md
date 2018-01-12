---
title: "방법: Finder 메서드에 필터 설명자 추가 | Microsoft Docs"
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
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], filter descriptors
- Business Data Connectivity service [SharePoint development in Visual Studio], add a filter
- BDC [SharePoint development in Visual Studio], add a filter
- BDC [SharePoint development in Visual Studio], filter descriptors
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 06dcea1c8e6d8220461c201de443a26162a608e3
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-a-filter-descriptor-to-a-finder-method"></a>방법: Finder 메서드에 필터 설명자 추가
  필터 설명자 실행 되기 전에를 메서드에 값을 전달 하는 모델의 소비자를 사용 합니다. 자세한 내용은 참조 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)합니다.  
  
 한 가지 일반적인 시나리오는 SharePoint에서 사용자가 원하는 기준과 일치 하는 외부 콘텐츠 형식의 인스턴스를 검색 합니다. Finder 메서드에 필터 설명자 추가 하 여이 시나리오를 지원할 수 있습니다.  
  
### <a name="to-add-a-filter-descriptor-to-a-finder-method"></a>Finder 메서드에 필터 설명자 추가 하려면  
  
1.  에 **BDC 메서드 세부 정보** 창 Finder 메서드 노드를 확장의 **매개 변수** 노드를 추가한 다음 입력된 매개 변수를 추가 합니다. 자세한 내용은 참조 [하는 방법: 메서드에 매개 변수를 추가](../sharepoint/how-to-add-a-parameter-to-a-method.md)합니다.  
  
2.  에 **메서드 세부 정보** 창에서 매개 변수의 형식 설명자를 선택 합니다.  
  
3.  메뉴 모음에서 **보기**, **속성 창**합니다.  
  
4.  에 **속성** 창의 설정는 **유형 이름** 필터에 대 한 적절 한 데이터 형식에는 속성입니다.  
  
     예를 들어 필터 메서드에서 반환 되는 판매 주문 수를 제한 하려면 주문 날짜를 사용할 수 있습니다. 해당 필터를 지원 하기 위해는 **유형 이름** 형식 설명자의 속성으로 설정 되어 있어야 **System.DateTime**합니다.  
  
5.  에 **메서드 세부 정보** 창을 확장 하 고는 **필터 설명자** 노드.  
  
6.  **필터 설명자 추가** 목록에서 선택 **필터 설명자 만들기**합니다.  
  
     아래에 새 필터 설명자 표시는 **필터 설명자** 노드.  
  
7.  메뉴 모음에서 **보기**, **속성 창**합니다.  
  
8.  에 **속성** 창, 선택는 **형식** 속성입니다.  
  
9. 에 대 한 표시 되는 목록에는 **형식** 속성을 원하는 필터링 패턴을 선택 합니다.  
  
     예를 들어 Finder 메서드를 반환 하 고 판매 주문의 수를 제한 하는 주문 날짜를 사용 하는 필터를 만들려면 선택 **비교**합니다. 비교 필터는 finder 메서드가 반환 하는 특정 조건을 충족 하는 인스턴스만 보장 합니다. 필터링 각 패턴에 대 한 자세한 내용은 참조 [종류의 필터에서 지 원하는 BDC](http://go.microsoft.com/fwlink/?LinkId=169287)합니다.  
  
10. 에 **속성** 창, 선택는 **연결 된 Typedescriptor** 속성입니다.  
  
11. 에 대 한 표시 되는 목록에는 **연결 된 Typedescriptor** 속성을이 절차의 앞부분에서 만든 형식 설명자를 선택 합니다. 이 필터는 Finder 메서드의 입력된 매개 변수 관련이 있습니다.  
  
12. 데이터를 반환 하는 Finder 메서드에 코드를 추가 합니다. 입력된 매개 변수는 선택 쿼리에 조건으로 사용할 수 있습니다.  
  
     다음 예에서는 지정 된 주문 날짜를 가진 판매 주문을 반환 합니다.  
  
    > [!NOTE]  
    >  값을 바꿉니다는 `ServerName` 필드와 사용자 서버의 이름입니다.  
  
     [!code-csharp[SP_BDC#11](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/salesorderservice.cs#11)]
     [!code-vb[SP_BDC#11](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/salesorderservice.vb#11)]  
  
## <a name="see-also"></a>참고 항목  
 [방법: Finder 메서드 추가](../sharepoint/how-to-add-a-finder-method.md)   
 [방법: 특정 Finder 메서드 추가](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [방법: 메서드에 매개 변수를 추가 합니다.](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [방법: 매개 변수의 형식 설명자를 정의 합니다.](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)   
 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [SharePoint에 비즈니스 데이터 통합](../sharepoint/integrating-business-data-into-sharepoint.md)  
  
  
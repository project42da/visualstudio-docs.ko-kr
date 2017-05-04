---
title: "방법: Finder 메서드에 필터 설명자 추가 | Microsoft Docs"
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
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "BDC[Visual Studio에서 SharePoint 개발], 필터 추가"
  - "BDC[Visual Studio에서 SharePoint 개발], 필터 설명자"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 필터 추가"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 필터 설명자"
ms.assetid: 228a6190-8cb8-4182-b6d9-d4c656f4a164
caps.latest.revision: 14
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 14
---
# 방법: Finder 메서드에 필터 설명자 추가
  필터 설명자를 사용하면 모델 소비자가 메서드가 실행되기 전에 메서드에 값을 전달할 수 있습니다.  자세한 내용은 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)을 참조하십시오.  
  
 한 가지 일반적인 시나리오는 SharePoint의 사용자가 일부 조건과 일치하는 외부 콘텐츠 형식의 인스턴스를 검색하려는 경우입니다.  필터 설명자를 Finder 메서드에 추가하여 이 시나리오를 지원할 수 있습니다.  
  
### 필터 설명자를 Finder 메서드에 추가하려면  
  
1.  **BDC 메서드 세부 정보** 창에서 Finder 메서드의 노드를 확장하고 **매개 변수** 노드를 확장한 다음 입력 매개 변수를 추가합니다.  자세한 내용은 [방법: 메서드에 매개 변수 추가](../sharepoint/how-to-add-a-parameter-to-a-method.md)을 참조하십시오.  
  
2.  **메서드 세부 정보** 창에서 매개 변수의 형식 설명자를 선택합니다.  
  
3.  메뉴 모음에서 **보기**, **속성 창**을 선택합니다.  
  
4.  **속성** 창에서 **형식 이름** 속성을 필터에 적합한 데이터 형식으로 설정합니다.  
  
     예를 들어, 필터에서 주문 날짜를 사용하여 메서드에서 반환하는 판매 주문의 수를 제한할 수 있습니다.  이 필터를 지원하려면 형식 설명자의 **형식 이름** 속성을 **System.DateTime**으로 설정해야 합니다.  
  
5.  **메서드 세부 정보** 창에서 **FilterDescriptor** 노드를 확장합니다.  
  
6.  **필터 설명자 추가** 목록에서 **필터 설명자 만들기** 를 선택합니다.  
  
     새로운 필터 설명자가 **FilterDescriptor** 노드 아래에 표시됩니다.  
  
7.  메뉴 모음에서 **보기**, **속성 창**을 선택합니다.  
  
8.  **속성** 창에서 **형식** 속성을 선택합니다.  
  
9. **형식** 속성에 대해 표시되는 목록에서, 원하는 필터링 패턴을 선택합니다.  
  
     예를 들어, 주문 날짜를 사용하여 Finder 메서드에서 반환하는 판매 주문의 수를 제한하는 필터를 만들려면 **비교**를 선택합니다.  비교 필터는 finder 메서드에서 특정 조건을 만족 하는 인스턴스만 반환할 것을 보장해 줍니다.  각 필터링 패턴에 대한 자세한 내용은 [BDC에 의해 지원되는 필터의 유형](http://go.microsoft.com/fwlink/?LinkId=169287) 을 참조하십시오.  
  
10. **속성** 창에서 **연결된 TypeDescriptor** 속성을 선택합니다.  
  
11. **연결된 TypeDescriptor** 속성에 대해 표시되는 목록에서 이 절차의 앞부분에서 만든 형식 설명자를 선택합니다.  이렇게 하면 필터가 Finder 메서드의 입력 매개 변수와 관련됩니다.  
  
12. 데이터를 반환하는 Finder 메서드에 코드를 추가합니다.  입력 매개 변수를 선택 쿼리에서 조건으로 사용할 수 있습니다.  
  
     다음 예제에서는 지정된 주문 날짜가 있는 판매 주문을 반환합니다.  
  
    > [!NOTE]  
    >  `ServerName` 필드의 값을 서버 이름으로 바꿉니다.  
  
     [!code-csharp[SP_BDC#11](../snippets/csharp/VS_Snippets_OfficeSP/sp_bdc/CS/bdcmodel1/salesorderservice.cs#11)]
     [!code-vb[SP_BDC#11](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_bdc/VB/bdcmodel1/salesorderservice.vb#11)]  
  
## 참고 항목  
 [방법: Finder 메서드 추가](../sharepoint/how-to-add-a-finder-method.md)   
 [방법: SpecificFinder 메서드 추가](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [방법: 메서드에 매개 변수 추가](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [How to: Define the Type Descriptor of a Parameter](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)   
 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [SharePoint에 비즈니스 데이터 통합](../sharepoint/integrating-business-data-into-sharepoint.md)  
  
  
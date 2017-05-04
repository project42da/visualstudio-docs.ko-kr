---
title: "엔터티 간 연결 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.SharePointTools.BDC.Association_Dialog"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "BDC[Visual Studio에서 SharePoint 개발], 외부 콘텐츠 형식 연결"
  - "BDC[Visual Studio에서 SharePoint 개발], 엔터티 간 연결"
  - "BDC[Visual Studio에서 SharePoint 개발], 연결 만들기"
  - "BDC[Visual Studio에서 SharePoint 개발], 엔터티 연결"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 외부 콘텐츠 형식 연결"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 엔터티 간 연결"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 연결 만들기"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 엔터티 연결"
ms.assetid: c908448c-13d3-4d2f-89ad-8d709b2958fb
caps.latest.revision: 15
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 14
---
# 엔터티 간 연결 만들기
  BDC\(비즈니스 데이터 연결\) 모델에서 연결을 만들어 엔터티 간에 관계를 정의할 수 있습니다.  Visual Studio에서는 모델 사용자에게 각 연결에 대한 정보를 제공하는 메서드를 생성합니다.  이러한 메서드는 SharePoint 웹 파트, 목록 또는 사용자 지정 응용 프로그램에서 사용되어 UI\(사용자 인터페이스\)에 데이터 간 관계를 표시할 수 있습니다.  
  
## 연결 만들기  
 Visual Studio **도구 상자** 에서 **연결** 컨트롤을 선택하고 첫 번째 엔터티\(소스 엔터티\)를 선택한 다음 두 번째 엔터티\(대상 엔터티\)를 선택하여 연결을 만듭니다.  **연결 편집기**에서 연결 정보를 정의할 수 있습니다.  자세한 내용은 [방법: 엔터티 간 연결 만들기](../sharepoint/how-to-create-an-association-between-entities.md)을 참조하십시오.  
  
## 연결 메서드  
 SharePoint 비즈니스 데이터 웹 파트와 같은 응용 프로그램에서는 엔터티의 서비스 클래스에 있는 메서드를 호출하여 연결을 사용합니다.  **연결 편집기**에서 메서드를 선택하여 엔터티의 서비스 클래스에 메서드를 추가할 수 있습니다.  
  
 기본적으로 **연결 편집기**에서는 소스 및 대상 엔터티에 AssociationNavigator 메서드를 추가합니다.  사용자는 소스 엔터티의 AssociationNavigator 메서드를 사용하여 대상 엔터티의 목록을 검색하고,  대상 엔터티의 AssociationNavigator 메서드를 사용하여 대상 엔터티와 관련이 있는 소스 엔터티를 검색할 수 있습니다.  
  
 적절한 정보를 반환하려면 이러한  메서드 각각에 코드를 추가해야 합니다.  보다 고급 시나리오를 지원하기 위해 다른 형식의 메서드를 추가할 수도 있습니다.  각 메서드에 대한 자세한 내용은 [지원되는 작업](http://go.microsoft.com/fwlink/?LinkId=169286) 을 참조하십시오.  
  
## 연결 형식  
 BDC 디자이너에서 외래 키 기반 연결과 외래 키가 없는 연결이라는 두 가지 형식의 연결을 만들 수 있습니다.  
  
### 외래 키 기반 연결  
 소스 엔터티의 식별자를 대상 엔터티에 정의된 형식 설명자에 연결하여 외래 키 기반 연결을 만들 수 있습니다.  모델 사용자는 이 관계를 사용하여 사용자에게 향상된 UI를 제공할 수 있습니다.  예를 들어 Outlook의 양식에서 사용자가 드롭다운 목록에 고객을 표시하는 판매 주문을 만들 수 있게 해 주고 SharePoint의 판매 주문 목록에서 사용자가 고객의 프로필 페이지를 열 수 있게 해 줍니다.  
  
 외래 키 기반 연결을 만들려면 동일한 이름과 형식을 공유하는 식별자와 형식 설명자를 연결합니다.  예를 들어 `Contact` 엔터티와 `SalesOrder` 엔터티 간에 외래 키 기반 연결을 만들 수 있습니다.  `SalesOrder` 엔터티는 Finder 또는 SpecificFinder 메서드의 반환 매개 변수의 일부로 `ContactID` 형식 설명자를 반환합니다.  두 형식 설명자 모두 **연결 편집기**에 표시됩니다.  `Contact` 엔터티와 `SalesOrder` 엔터티 간에 외래 키 기반 관계를 만들려면 이러한 각 필드 옆에 있는 `ContactID` 식별자를 선택합니다.  
  
 대상 엔터티의 컬렉션을 반환하는 코드를 소스 엔터티의 Association Navigator 메서드에 추가합니다.  다음 예제에서는 연락처의 판매 주문을 반환합니다.  
  
 [!code-csharp[SP_BDC#7](../snippets/csharp/VS_Snippets_OfficeSP/sp_bdc/CS/bdcmodel1/contactservice.cs#7)]
 [!code-vb[SP_BDC#7](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_bdc/VB/bdcmodel1/contactservice.vb#7)]  
  
 소스 엔터티를 반환하는 코드를 대상 엔터티의 Association Navigator 메서드에 추가합니다.  다음 예제에서는 판매 주문과 관련된 연락처를 반환합니다.  
  
 [!code-csharp[SP_BDC#8](../snippets/csharp/VS_Snippets_OfficeSP/sp_bdc/CS/bdcmodel1/salesorderservice.cs#8)]
 [!code-vb[SP_BDC#8](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_bdc/VB/bdcmodel1/salesorderservice.vb#8)]  
  
### 외래 키가 없는 연결  
 필드 형식 설명자에 식별자를 매핑하지 않아도 연결을 만들 수 있습니다.  소스 엔터티와 대상 엔터티 간에 직접적인 관계가 없는 경우 이 같은 연결을 만들면 좋습니다.  예를 들어 `SalesOrderDetail` 테이블에는 `Contact` 테이블의 기본 키에 매핑되는 외래 키가 없습니다.  
  
 `Contact`와 관련된 정보를 `SalesOrderDetail` 테이블에 표시하려면 `Contact` 엔터티와 `SalesOrderDetail` 엔터티 간에 외래 키가 없는 연결을 만들면 됩니다.  
  
 `Contact` 엔터티의 AssociationNavigator 메서드에서 테이블을 조인하거나 저장 프로시저를 호출하여 `SalesOrderDetail` 엔터티를 반환합니다.  
  
 다음 예제에서는 테이블을 조인하여 모든 판매 주문에 대한 상세 정보를 반환합니다.  
  
 [!code-csharp[SP_BDC#9](../snippets/csharp/VS_Snippets_OfficeSP/sp_bdc/CS/bdcmodel1/contactservice.cs#9)]
 [!code-vb[SP_BDC#9](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_bdc/VB/bdcmodel1/contactservice.vb#9)]  
  
 `SalesOrderDetail` 엔터티의 AssociationNavigator 메서드에서 관련 `Contact`를 반환합니다.  다음 예제에서는 이 작업을 보여 줍니다.  
  
 [!code-csharp[SP_BDC#10](../snippets/csharp/VS_Snippets_OfficeSP/sp_bdc/CS/bdcmodel1/salesorderdetailservice.cs#10)]
 [!code-vb[SP_BDC#10](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_bdc/VB/bdcmodel1/salesorderdetailservice.vb#10)]  
  
## 참고 항목  
 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [방법: 엔터티 간 연결 만들기](../sharepoint/how-to-create-an-association-between-entities.md)  
  
  
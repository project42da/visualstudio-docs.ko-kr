---
title: "방법: 엔터티 간 연결 만들기"
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
  - "AssociationGroupTool"
dev_langs: 
  - "VB"
  - "CSharp"
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
ms.assetid: 0c095df8-1f40-4c4d-9fed-e125a8429724
caps.latest.revision: 17
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 16
---
# 방법: 엔터티 간 연결 만들기
  BDC\(비즈니스 데이터 연결\) 모델에서 연결을 만들어 엔터티 간에 관계를 정의할 수 있습니다.  Visual Studio에서는 모델 사용자에게 각 연결에 대한 정보를 제공하는 메서드를 생성합니다.  이러한 메서드는 SharePoint 웹 파트, 목록 또는 사용자 지정 응용 프로그램에서 사용되어 UI\(사용자 인터페이스\)에 데이터 간 관계를 표시할 수 있습니다.  
  
 BDC 디자이너에서 외래 키 기반 연결과 외래 키가 없는 연결이라는 두 가지 형식의 연결을 만들 수 있습니다.  자세한 내용은 [엔터티 간 연결 만들기](../sharepoint/creating-an-association-between-entities.md)을 참조하십시오.  
  
### 엔터티 간 연결을 만들려면  
  
1.  **도구 상자** 의 **BusinessDataConnectivity** 탭에서 **연결** 을 선택합니다.  
  
2.  BDC 디자이너에서 소스 엔터티를 선택한 다음 대상 엔터티를 선택합니다.  
  
     **연결 편집기**가 나타납니다.  
  
3.  외래 키 기반 연결을 만들려면 **외래 키 연결** 확인란을 선택합니다.  
  
    1.  **식별자 매핑** 테이블의 **소스 ID** 열에서 **필드** 열에 표시되는 일치하는 각 형식 설명자 옆에 있는 ID를 선택합니다.  
  
         예를 들어 **소스 ID** 열에서 `ReadList.salesOrderList.SalesOrderList.SalesOrder.ContactID` 형식 설명자 및 `ReadItem.salesOrder.SalesOrder.ContactID` 형식 설명자 옆에 있는 `ContactID`를 선택합니다.  
  
4.  외래 키가 없는 연결을 만들려면 **외래 키 연결** 확인란의 선택을 취소합니다.  
  
5.  **확인** 단추를 선택합니다.  
  
6.  BDC 디자이너에서 소스 엔터티와 대상 엔터티 사이에 연결을 나타내는 선이 나타납니다.  
  
     대상 엔터티의 서비스 클래스와 소스 엔터티의 서비스 클래스에 AssociationNavigator 메서드가 추가됩니다.  연결 탐색 방법에 대한 자세한 내용은 [Supported Operations](http://go.microsoft.com/fwlink/?LinkId=169286) 을 참조하십시오.  
  
7.  소스 엔터티의 AssociationNavigator 메서드에서 대상 엔터티의 컬렉션을 반환하는 코드를 추가합니다.  
  
8.  대상 엔터티의 AssociationNavigator 메서드에서 관련 소스 엔터티를 반환하는 코드를 추가합니다.  
  
     AssociationNavigator 메서드의 예를 보려면 [엔터티 간 연결 만들기](../sharepoint/creating-an-association-between-entities.md)를 참조하십시오.  
  
## 참고 항목  
 [엔터티 간 연결 만들기](../sharepoint/creating-an-association-between-entities.md)   
 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [방법: Finder 메서드 추가](../sharepoint/how-to-add-a-finder-method.md)   
 [방법: SpecificFinder 메서드 추가](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [방법: Creator 메서드 추가](../sharepoint/how-to-add-a-creator-method.md)   
 [방법: Deleter 메서드 추가](../sharepoint/how-to-add-a-deleter-method.md)   
 [방법: Updater 메서드 추가](../sharepoint/how-to-add-an-updater-method.md)   
 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)   
 [방법: 메서드에 매개 변수 추가](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [방법: 메서드 인스턴스 정의](../sharepoint/how-to-define-a-method-instance.md)   
 [How to: Define the Type Descriptor of a Parameter](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)   
 [연습: 비즈니스 데이터를 사용하여 SharePoint에 외부 목록 만들기](../sharepoint/walkthrough-creating-an-external-list-in-sharepoint-by-using-business-data.md)  
  
  
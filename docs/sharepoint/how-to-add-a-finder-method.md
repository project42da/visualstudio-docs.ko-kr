---
title: "방법: Finder 메서드 추가 | Microsoft Docs"
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
  - "BDC[Visual Studio에서 SharePoint 개발], Finder 메서드"
  - "BDC[Visual Studio에서 SharePoint 개발], 엔터티 가져오기"
  - "BDC[Visual Studio에서 SharePoint 개발], 엔터티 반환"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], Finder 메서드"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 엔터티 가져오기"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 엔터티 반환"
ms.assetid: 5de2cae3-d1f7-4a68-aac0-458967aca692
caps.latest.revision: 25
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 25
---
# 방법: Finder 메서드 추가
  비즈니스 데이터 연결 서비스에서 웹 파트나 목록에 엔터티 목록을 표시할 수 있도록 하려면 *Finder* 메서드를 만들어야 합니다.  Finder 메서드는 엔터티 인스턴스의 컬렉션을 반환하는 특수한 메서드입니다.  자세한 내용은 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)을 참조하십시오.  
  
### Finder 메서드를 만들려면  
  
1.  BDC 디자이너에서 엔터티를 선택합니다.  
  
     자세한 내용은 [방법: 모델에 엔터티 추가](../sharepoint/how-to-add-an-entity-to-a-model.md)을 참조하십시오.  
  
2.  선택 메뉴 모음에서  **보기**,  **기타 창**,  **BDC 메서드 세부 정보** 을 선택합니다.  
  
     **BDC 메서드 세부 정보** 창이 열립니다.  **BDC 메서드 세부 정보** 창에 대한 자세한 내용은 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)를 참조하십시오.  
  
3.  **메서드 추가** 목록에서 **Finder 메서드 만들기** 를 선택합니다.  
  
     메서드, 반환 매개 변수 및 형식 설명자가 추가됩니다.  
  
4.  형식 설명자를 엔터티 컬렉션 형식 설명자로 구성합니다.  엔터티 컬렉션 형식 설명자를 만드는 방법에 대한 자세한 내용은 [How to: Define the Type Descriptor of a Parameter](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)를 참조하십시오.  
  
    > [!NOTE]  
    >  엔터티에 SpecificFinder 메서드를 추가한 경우 SpecificFinder 메서드에 정의한 형식 설명자가 사용되므로  이 단계를 수행할 필요가 없습니다.  
  
5.  **솔루션 탐색기**에서 엔터티에 대해 생성된 서비스 코드 파일의 바로가기를 연 다음 **코드 보기**를 선택합니다.  서비스 코드 파일에 대한 자세한 내용은 [비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)를 참조하십시오.  
  
6.  Finder 메서드에 코드를 추가합니다.  이 코드는 다음 작업을 수행합니다.  
  
    -   데이터 소스에서 데이터를 검색합니다.  
  
    -   BDC 서비스에 엔터티 목록을 반환합니다.  
  
     다음 예제에서는 SQL Server의 AdventureWorks 샘플 데이터베이스에 있는 데이터를 사용하여 `Contact` 엔터티의 컬렉션을 반환합니다.  
  
    > [!NOTE]  
    >  `ServerName` 필드의 값을 서버 이름으로 바꿉니다.  
  
     [!code-csharp[SP_BDC#2](../snippets/csharp/VS_Snippets_OfficeSP/sp_bdc/CS/bdcmodel1/contactservice.cs#2)]
     [!code-vb[SP_BDC#2](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_bdc/VB/bdcmodel1/contactservice.vb#2)]  
  
## 참고 항목  
 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)   
 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [방법: SpecificFinder 메서드 추가](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [방법: Creator 메서드 추가](../sharepoint/how-to-add-a-creator-method.md)   
 [방법: Deleter 메서드 추가](../sharepoint/how-to-add-a-deleter-method.md)   
 [방법: Updater 메서드 추가](../sharepoint/how-to-add-an-updater-method.md)   
 [방법: 메서드에 매개 변수 추가](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [방법: 메서드 인스턴스 정의](../sharepoint/how-to-define-a-method-instance.md)  
  
  
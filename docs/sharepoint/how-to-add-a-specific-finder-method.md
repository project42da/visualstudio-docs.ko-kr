---
title: "방법: SpecificFinder 메서드 추가"
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
  - "BDC[Visual Studio에서 SharePoint 개발], 엔터티 가져오기"
  - "BDC[Visual Studio에서 SharePoint 개발], 엔터티 반환"
  - "BDC[Visual Studio에서 SharePoint 개발], SpecificFinder"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 엔터티 가져오기"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 엔터티 반환"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], SpecificFinder"
ms.assetid: 7bbc5986-2828-4755-96fa-9f1dc0f8dc75
caps.latest.revision: 30
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 29
---
# 방법: SpecificFinder 메서드 추가
  *SpecificFinder* 메서드를 만들어 단일 엔터티 인스턴스를 반환할 수 있습니다.  사용자가 비즈니스 데이터 웹 파트 또는 외부 목록에서 엔터티를 선택하면 BDC\(비즈니스 데이터 연결\) 서비스에서 SpecificFinder 메서드를 실행합니다.  자세한 내용은 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)을 참조하십시오.  
  
### SpecificFinder 메서드를 만들려면  
  
1.  BDC 디자이너에서 엔터티를 선택합니다.  
  
     Visual Studio에서 BDC 디자이너에 엔터티를 추가하는 방법에 대한 자세한 내용은 [방법: 모델에 엔터티 추가](../sharepoint/how-to-add-an-entity-to-a-model.md) 을 참조하십시오.  
  
2.  선택 메뉴 모음에서 **보기**, **기타 창**, **BDC 메서드 세부 정보** 을 선택합니다.  
  
     **BDC 메서드 세부 정보** 창이 열립니다.  이 창에 대한 자세한 내용은 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)를 참조하십시오.  
  
3.  **메서드 추가** 목록에서 **Specific Finder 메서드 만들기** 를 선택합니다.  
  
     모델에 다음 요소가 추가됩니다.  이러한 요소는 **BDC 메서드 세부 정보** 창에 표시됩니다.  
  
    -   메서드  
  
    -   메서드의 입력 매개 변수  
  
    -   메서드의 반환 매개 변수  
  
    -   각 매개 변수에 대한 형식 설명자  
  
    -   메서드의 메서드 인스턴스  
  
     자세한 내용은 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)을 참조하십시오.  
  
4.  Visual Studio **속성** 창을 엽니다.  
  
5.  반환 매개 변수의 형식 설명자를 엔터티 형식 설명자로 구성합니다.  엔터티 형식 설명자를 만드는 방법에 대한 자세한 내용은 [How to: Define the Type Descriptor of a Parameter](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)를 참조하십시오.  
  
    > [!NOTE]  
    >  엔터티에 Finder 메서드를 추가한 경우 이 단계를 수행할 필요가 없습니다.  이 단계를 수행할 필요가 없습니다.  
  
    > [!NOTE]  
    >  엔터티 형식의 식별자 필드가 데이터베이스 테이블에서 자동으로 생성되는 필드에 해당할 경우 식별자 필드의 **읽기 전용** 속성을 **True**로 설정합니다.  
  
6.  **메서드 세부 정보** 창에서 메서드의 메서드 인스턴스를 선택합니다.  
  
7.  **속성 창**에서 **반환 매개 변수 이름** 속성을 메서드의 반환 매개 변수 이름으로 설정합니다.  메서드 인스턴스의 속성에 대한 자세한 내용은 [MethodInstance](http://go.microsoft.com/fwlink/?LinkID=169282) 을 참조하십시오.  
  
8.  **솔루션 탐색기**에서 엔터티에 대해 생성된 서비스 코드 파일의 바로가기를 연 다음 **코드 보기**를 선택합니다.  
  
     코드 편집기에서 엔터티 서비스 코드 파일이 열립니다.  엔터티 서비스 코드 파일에 대한 자세한 내용은 [비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)를 참조하십시오.  
  
9. SpecificFinder 메서드에 코드를 추가합니다.  이 코드는 다음 작업을 수행합니다.  
  
    -   데이터 소스에서 레코드를 검색합니다.  
  
    -   BDC 서비스에 엔터티를 반환합니다.  
  
     다음 예제에서는 SQL Server의 AdventureWorks 샘플 데이터베이스에서 연락처를 반환합니다.  
  
    > [!NOTE]  
    >  `ServerName` 필드의 값을 서버 이름으로 바꿉니다.  
  
     [!code-csharp[SP_BDC#3](../snippets/csharp/VS_Snippets_OfficeSP/sp_bdc/CS/bdcmodel1/contactservice.cs#3)]
     [!code-vb[SP_BDC#3](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_bdc/VB/bdcmodel1/contactservice.vb#3)]  
  
## 참고 항목  
 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [방법: Finder 메서드 추가](../sharepoint/how-to-add-a-finder-method.md)   
 [방법: Creator 메서드 추가](../sharepoint/how-to-add-a-creator-method.md)   
 [방법: Deleter 메서드 추가](../sharepoint/how-to-add-a-deleter-method.md)   
 [방법: Updater 메서드 추가](../sharepoint/how-to-add-an-updater-method.md)   
 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)   
 [방법: 메서드에 매개 변수 추가](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [방법: 메서드 인스턴스 정의](../sharepoint/how-to-define-a-method-instance.md)  
  
  
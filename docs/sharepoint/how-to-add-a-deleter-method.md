---
title: "방법: Deleter 메서드 추가 | Microsoft Docs"
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
  - "BDC[Visual Studio에서 SharePoint 개발], Deleter"
  - "BDC[Visual Studio에서 SharePoint 개발], 데이터 삭제"
  - "BDC[Visual Studio에서 SharePoint 개발], 엔터티 인스턴스 삭제"
  - "BDC[Visual Studio에서 SharePoint 개발], 데이터 제거"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], Deleter"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 데이터 삭제"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 엔터티 인스턴스 삭제"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 데이터 제거"
ms.assetid: 3362eaf4-5dc7-4450-9009-b296308ae61f
caps.latest.revision: 21
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 21
---
# 방법: Deleter 메서드 추가
  모델에 *Deleter* 메서드를 추가하여 최종 사용자가 SharePoint 사이트의 외부 목록에서 데이터 레코드를 삭제하도록 할 수 있습니다.  자세한 내용은 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)을 참조하십시오.  
  
### Deleter 메서드를 만들려면  
  
1.  BDC 디자이너에서 엔터티를 선택합니다.  
  
2.  선택 메뉴 모음에서 **보기**, **기타 창**, **BDC 메서드 세부 정보** 을 선택합니다.  
  
     **BDC 메서드 세부 정보** 창이 열립니다.  이 창에 대한 자세한 내용은 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)를 참조하십시오.  
  
3.  **메서드 추가** 목록에서 **Deleter 메서드 만들기** 를 선택합니다.  
  
     모델에 다음 요소가 추가됩니다.  이러한 요소는 **BDC 메서드 세부 정보** 창에 표시됩니다.  
  
    -   **Delete** 메서드  
  
    -   메서드의 입력 매개 변수  
  
    -   매개 변수에 대한 형식 설명자  
  
    -   메서드의 메서드 인스턴스  
  
     자세한 내용은 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)을 참조하십시오.  
  
4.  **솔루션 탐색기**에서 엔터티에 대해 생성된 서비스 코드 파일의 바로가기를 연 다음 **코드 보기**를 선택합니다.  
  
     코드 편집기에서 엔터티 서비스 코드 파일이 열립니다.  엔터티 서비스 코드 파일에 대한 자세한 내용은 [비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)를 참조하십시오.  
  
5.  레코드를 삭제하는 코드를 Deleter 메서드에 추가합니다.  다음 예제에서는 SQL Server의 AdventureWorks 샘플 데이터베이스를 사용하여 판매 주문에서 품목을 삭제합니다.  
  
    > [!NOTE]  
    >  이 예제의  메서드는 두 개의 입력 매개 변수를 사용합니다.  
  
    > [!NOTE]  
    >  `ServerName` 필드의 값을 서버 이름으로 바꿉니다.  
  
     [!code-csharp[SP_BDC#6](../snippets/csharp/VS_Snippets_OfficeSP/sp_bdc/CS/bdcmodel1/salesorderdetailservice.cs#6)]
     [!code-vb[SP_BDC#6](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_bdc/VB/bdcmodel1/salesorderdetailservice.vb#6)]  
  
## 참고 항목  
 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [방법: Finder 메서드 추가](../sharepoint/how-to-add-a-finder-method.md)   
 [방법: SpecificFinder 메서드 추가](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [방법: Creator 메서드 추가](../sharepoint/how-to-add-a-creator-method.md)   
 [방법: Updater 메서드 추가](../sharepoint/how-to-add-an-updater-method.md)   
 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)   
 [방법: 메서드에 매개 변수 추가](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [방법: 메서드 인스턴스 정의](../sharepoint/how-to-define-a-method-instance.md)  
  
  